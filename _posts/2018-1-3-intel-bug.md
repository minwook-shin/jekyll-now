---
layout: post
title: 인텔 멜트다운 버그
---

안녕하세요. 오늘은 원래 딴 주제로 포스팅을 하려고 했으나, 갑자기 인텔 버그 이슈가 터져서 정리 포스팅을 해보려 합니다.

## 해외 게시물 인용

레딧의 [Intel bug incoming](https://amp.reddit.com/r/sysadmin/comments/7nl8r0/intel_bug_incoming/?__twitter_impression=true)라는 이름으로 게시된 글을 참고했습니다.


우선 레딧 발 게시물을 그대로 인용해보자면,

```
There is evidence of a massive Intel CPU hardware bug (currently under embargo) that directly affects big cloud providers like Amazon and Google. The fix will introduce notable performance penalties on Intel machines (30-35%).

PTI affects a core low-level feature (virtual memory) and has severe performance penalties: 29% for an i7-6700 and 34% for an i7-3770S, according to Brad Spengler from grsecurity.
```
입니다.

간단히 번역해서 보면,
```
대량의 Intel CPU 하드웨어 버그가 있습니다. 이 수정 사항은 Intel 시스템 (30-35 %)에서 현저한 성능 저하를 초래할 것입니다. 
PTI는 핵심 저수준 기능(가상 메모리)에 영향을 미치며 심한 성능 저하가 있습니다. i7-6700의 경우 29 %, i7-3770S의 경우 34 %의 성능 저하가 있다고 Brad Spengler는 말합니다. 
```
이라고 합니다.

## 용어 정리

아마 위에서 보시면 생소한 용어가 있으실 겁니다. 여기서 PTI는 Page Table Isolation 이라고 하며, 페이지 테이블에 전체 커널 메모리를 매핑하는 기술입니다.

이전에는 KAISER라고 불리는 기술이었으나 같은 뜻이며, KPTI(Kernel page-table isolation)라고도 씁니다.

또한, 페이지 테이블은 프로세스의 페이지 정보를 저장하고 있는 테이블로서, 페이징 기법 자료구조입니다.

즉, 정리해보면 KAISER와 KPTI와 KPTI는 같으며, KPTI는 커널에서 프로세스의 페이지 정보를 저장하고 있는 테이블를 격리하는 기술입니다.

## 사건 개요

이번에 발생한 인텔 cpu 버그는 적어도 10년 전의 모든 인텔 프로세서에 영향을 미친다고 추정이 되는 버그라고 합니다.

인텔에서 운영체제가 하나의 페이지 테이블로 커널 메모리, 사용자 메모리로 나누어서 사용하며 무작위로 배치하는 KASLR이라는 기능을 썼고, 최근 버그 때문에 사용자 영역에서 KASLR이 적용된 커널 메모리를 훔쳐보는 것이 가능해졌습니다.

그래서 인텔측에서는 커널 메모리 영역과 사용자 메모리 영역의 페이지 테이블을 분리하는 버그 패치를 감행했고, 
결국 응용 프로그램 단계에서 커널 기능을 사용할 순간 다른 페이지 테이블을 참조하기 때문에 심각한 성능 저하가 발생한다고 합니다.

## 적용 범위

확인해본 결과, 현재 리눅스 4.15-rc6 릴리즈의 메인 라인과 윈도우10 RS4에 패치가 적용되었습니다.

## 그나마 다행(..?)

불생중 다행이라고 해야될지 모르나, PCID 기능이 적용된 신형 인텔 CPU에서는 해당 버그의 커널패치로 인한 성능저하가 완화되는 것으로 밝혀졌습니다

- [원문 출처](https://www.phoronix.com/scan.php?page=article&item=linux-415-x86pti&num=1) 인용

```
Newer Intel CPUs with PCID should also help in ensuring less of a performance impact.
```

## 국내 사례 

직접 문제를 겪어 본 [국내 커뮤니티](http://www.hwbattle.com/bbs/board.php?bo_table=cpumbram&wr_id=96704)에 따르면 대략적으로 파일 입출력은 반토막나고, DB 는 15% 성능 감소했으며 컴파일러 벤치마크 일부 항목이 감소된다고 합니다.
하지만, 커널 컴파일, 인코딩, 게임에서는 영향이 없다고합니다.

## 추가 사항

추가로 AMD의 AMD RYZEN 시리즈에는 문제가 발견되지 않았으나, 버그 수정코드에 이를 반영하지 않고 AMD CPU까지 적용하는 바람에 같이 성능하락을 당하고 있다고 합니다. 아마도 곧 수정 될 듯합니다. 

> 2018.01.09 : 인텔 버그명을 멜트다운으로 정정하였습니다.