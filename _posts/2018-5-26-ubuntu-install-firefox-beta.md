---
layout: post
title: ubuntu에서 파이어폭스 베타 설치하기
---

오늘은 우분투에서 파이어폭스 베타버전을 설치하는 방법을 알아보고자 합니다.

베타 버전은 버그가 많이 존재할 수 있으므로, 주의를 요합니다.

안정버전은 우분투에 기본으로 탑재되어 있으므로 그대로 즐기시면 됩니다.

## 베타

최신 파이어폭스 베타 빌드를 설치하고 업데이트할 수 있는 ppa가 있습니다.

베타 버전은 지금 설치되어 있는 파이어폭스의 버전을 변경시킵니다.

```
sudo add-apt-repository ppa:mozillateam/firefox-next
sudo apt update
sudo apt install firefox
```

이 ppa는 우분투 14.04와 16.04 그리고 18.04를 지원한다고 합니다.

## nightly

하루에 여러번 업데이트되는 버전으로서 안전을 보증해주지 않습니다.

이 버전은 지금 설치된 파이어폭스를 대체하지않고, 따로 설치됩니다.

```
sudo add-apt-repository ppa:ubuntu-mozilla-daily/ppa
sudo apt update
sudo apt install firefox-trunk
```

소식에 따르면 이 버전은 정식 버전의 파이어폭스와 다른 프로파일을 이용하여 기존 환경에 영향을 끼치지 않는다고 합니다.