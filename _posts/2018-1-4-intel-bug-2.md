---
layout: post
title: 인텔 Page Table Isolation (PTI) 버그 후속편
---

인텔 Page Table Isolation (PTI) 버그에 대한 글은 어제 자(1월 3일)로 최초 작성했지만, 오늘 포스팅은 그 이후 벌어진 이야기와 슬슬 나오고 있는 업계의 대응과 결론을 적어보려 합니다.

## 인텔 CEO의 주식 매각

일단, 어제는 약간 루머 같아서 제외한 이야기인데, 인텔 CEO가 다수의 주식을 팔았다고 합니다.

https://www.fool.com/investing/2017/12/19/intels-ceo-just-sold-a-lot-of-stock.aspx


다만, 인텔 CEO 관련 의혹 내용들은 Official이 아니므로, 독자 여러분의 주의를 필요로 합니다.

## 인텔 공식 입장

https://newsroom.intel.com/news/intel-responds-to-security-research-findings/

인텔의 공식 입장이 나왔습니다.
(후속 포스팅을 하게 된 계기)

```
Intel and other technology companies have been made aware of new security research describing software analysis methods that, when used for malicious purposes, have the potential to improperly gather sensitive data from computing devices that are operating as designed. Intel believes these exploits do not have the potential to corrupt, modify or delete data.

Recent reports that these exploits are caused by a “bug” or a “flaw” and are unique to Intel products are incorrect. Based on the analysis to date, many types of computing devices — with many different vendors’ processors and operating systems — are susceptible to these exploits.

Intel is committed to product and customer security and is working closely with many other technology companies, including AMD, ARM Holdings and several operating system vendors, to develop an industry-wide approach to resolve this issue promptly and constructively. Intel has begun providing software and firmware updates to mitigate these exploits. Contrary to some reports, any performance impacts are workload-dependent, and, for the average computer user, should not be significant and will be mitigated over time.

Intel is committed to the industry best practice of responsible disclosure of potential security issues, which is why Intel and other vendors had planned to disclose this issue next week when more software and firmware updates will be available. However, Intel is making this statement today because of the current inaccurate media reports.

Check with your operating system vendor or system manufacturer and apply any available updates as soon as they are available. Following good security practices that protect against malware in general will also help protect against possible exploitation until updates can be applied.

Intel believes its products are the most secure in the world and that, with the support of its partners, the current solutions to this issue provide the best possible security for its customers.
```

위는 인텔 입장의 전문이며,

제가 따로 정리해보자면,
```
취약점을 인지하고 있으며 데이터 손상, 수정/삭제의 가능성은 없다.

그리고 인텔 제품에서만 나오는 문제점이 아니고 
다양한 유형의 컴퓨터에서 취약하다.

다른 기업과 긴밀히 협력중이고, 펌웨어 업데이트를 제공하기 시작했다.

성능에 미치는 영향은 일반적인 컴퓨터 사용자의 경우 중요하지 않다.

원래 이 이슈를 곧 공개할 계획이였지만, 
부정확 언론 보도로 인해 오늘 성명을 발표하게 되었다.

만약 운영체제에 업데이트가 제공되면 즉시 적용해주시기 바란다.
```

따로 사담은 싣지 않겠지만, (제가 보기에는) 딱히 명쾌한 해답은 아니라고 봅니다.

## 오픈소스 업계들의 보고서

### Redhat

[레드햇 보안 보고서](https://access.redhat.com/security/vulnerabilities/speculativeexecution)에 따르면,
Impact가 Important라고 표기되며, 3가지 variant을 포함한다고 합니다.

이번 보고는 Google Project Zero에서 도움을 주었다고 합니다.

* 영향을 받는 레드햇 제품군

```
Red Hat Enterprise Linux 5
Red Hat Enterprise Linux 6
Red Hat Enterprise Linux 7
Red Hat Atomic Host
Red Hat Enterprise MRG 2
Red Hat OpenShift Online v2
Red Hat OpenShift Online v3
Red Hat Virtualization (RHEV-H/RHV-H)
Red Hat OpenStack (OSP) 6
Red Hat OpenStack (OSP) 7
Red Hat OpenStack (OSP) 8
Red Hat OpenStack (OSP) 9
Red Hat OpenStack (OSP) 10
Red Hat OpenStack (OSP) 11
Red Hat OpenStack (OSP) 12
```

[이곳](https://access.redhat.com/security/vulnerabilities/speculativeexecution)에서 업데이트를 받는 제품군을 알아볼 수 있습니다.

### Ubuntu

[우분투 보안 보고서](https://people.canonical.com/~ubuntu-security/cve/2017/CVE-2017-5754.html)에 따르면, 캐노니컬 측에서는 Priority가 Critical급이라고 보고 있으며, AMD cpu에는 영향을 미치지 않는다고 명확히 언급하고 있습니다.

```
This flaw only affects Intel processors. 
AMD reports that their processors are not affected.
```

* 영향을 받는 우분투 버전

end-of-life(지원 중단)된 버전을 제외하면 대부분 DNE(do not exist)인 상태입니다.


## 결론

아직 대부분의 일반 사용자의 업데이트 적용이 이뤄지지 않았기 때문에 속단하기 이르지만, 만약 업데이트가 적용되고 체감된다면... 좋지 못한 결말을 예견할 수 있을 듯합니다.

앞으로 어떻게 또 이야기가 진행될지 모르겠지만, 인텔의 공식 입장도 나온 만큼 이제 더는  후속 포스팅은 내놓지 않을 예정입니다.
이틀 동안 같은 주제인데도 오늘 블로그를 봐주셔서 감사합니다.