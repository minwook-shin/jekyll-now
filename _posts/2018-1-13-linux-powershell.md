---
layout: post
title: 파워셀 6.0 리눅스에 설치해보기
---

예전에 닷넷코어가 오픈소스화되었다는 소식만 듣고 있다가, PowerShell Core 6.0(첫 정식버전)이 나왔다고 하길래 직접 써보았습니다.

[PowerShell Team Blog](https://blogs.msdn.microsoft.com/powershell/2018/01/10/powershell-core-6-0-generally-available-ga-and-supported/)에 따르면 1월 10일에 PowerShell Core 6.0이 발표되었습니다.

기존에 베타 버전이 있었지만, 이번에 정식 버전이 나왔으니 한번 체험해보았습니다.

## 다운로드 

윈도우 : https://aka.ms/getps6-windows

리눅스 : https://aka.ms/getps6-linux

* 만약 베타가 설치되있으면 : 

```bash
sudo apt remove powershell && sudo apt-get install powershell
```

이전 베타버전은 지우고 다시 설치해야 된다고 합니다.

## Windows PowerShell과 차이점

기존 존재했던 Windows PowerShell은 Windows에서 기본 제공 구성 요소로 사용할 수 있고 .NET Framework 런타임에 의존했지만, PowerShell Core는 .NET 코어의 크로스 플랫폼 특성 덕분에 .NET Core 런타임을 사용하며 Windows, macOS 및 Linux에서 사용할 수 있습니다.

## 지원 운영체제

공식 지원

* Windows 7, 8.1, and 10
* Windows Server 2008 R2, 2012 R2, 2016
* Windows Server Semi-Annual Channel
* Ubuntu 14.04, 16.04, and 17.04
* Debian 8.7+, and 9
* CentOS 7
* Red Hat Enterprise Linux 7
* OpenSUSE 42.2
* Fedora 25, 26
* macOS 10.12+

비공식 지원

* Arch Linux
* Kali Linux
* AppImage (works on multiple Linux platforms)

시험적 릴리즈

* Windows on ARM32/ARM64
* Raspbian (Stretch)

## 작동하는 모듈 

* CimCmdlets
* Microsoft.PowerShell.Archive
* Microsoft.PowerShell.Diagnostics
* Microsoft.PowerShell.Host
* Microsoft.PowerShell.Management
* Microsoft.PowerShell.Security
* Microsoft.PowerShell.Utility
* Microsoft.WSMan.Management
* PackageManagement
* PowerShellGet
* PSDesiredStateConfiguration
* PSDiagnostics
* PSReadLine

## 직접 해보니...

뭔가 정보만 기록하기에는 아쉬워서 [파워셀 명령어에 대한 짧은 글](http://radar.oreilly.com/2013/06/powershell-command-line-introduction.html)을 읽어보고 리눅스에서 직접 테스트해보았습니다.

설치 과정은 [깃허브](https://github.com/PowerShell/PowerShell/blob/master/docs/installation/linux.md#ubuntu-1604)에서 참고했습니다.

루분투 16.04에서 설치시 52.2mmb 정도 용량이 소요되었습니다.

설치가 완료된 뒤, pwsh이라고 입력하면
```PowerShell
PowerShell v6.0.0

http://aka.ms/pscore6-docs
Type 'help' to get help.

PS /home/[사용자 계정명]>
```

라고 출력되면서 시작됩니다.

우선 당연히도 윈도우에 내장된 ipconfig와 같은 프로그램은 실행이 불가했고, tap키를 이용한 Autocomplete 기능으로 bash와 다르게 대소문자는 알아서 변환되었습니다.

예시로 get-co 까지 치고 tab하면 Get-Co로 변환되며 아래에 전체 명령어들을 보여줍니다.

* command

Get-Command와 Get-Content가 작동됩니다.

예시로 Get-Content ./hello.cpp는 cat ./hello.cpp와 동일하게 작동합니다.

* 배열

그리고 닷넷에 기반되어 있으므로 자체적으로 변수에 할당한 배열을 ```.```을 이용하여

```powerShell
$list = 1..5
1
2
3
4
5
```

```PowerShell
$list.GetType()
```

이처럼 사용할 수 있습니다.

* Hash Tables

해쉬 테이블도 됩니다.

```PowerShell
$hash = @{} # init
```

```PowerShell
$hash = @{a=10;b=20}
```

```PowerShell
$hash
```

* Process

또한 Get-Process도 가능하여 리눅스 시스템상의 프로세스를 볼 수 있습니다.

* Functions

함수와 Array Comprehensions도 마찬가지로 됩니다.

```PowerShell
function sum ($x) {$x+$x}
```

sum이란 함수를 만들고 인자를 x로 두고 x+x로 구성합니다.

```PowerShell
sum 2
```
sum 함수와 2를 인자로 넣습니다.

```PowerShell
$result = $list | foreach {sum $_}
```

foreach문으로 이전에 만든 list를 활용합니다.

```PowerShell
$result
```

* C#

또한, 닷넷 Framework를 이용하여 System.Math를 파워쉘에서 Pow에 접근할 수 있습니다.

```PowerShell
[Math]::Pow(5,5)
3125
```

* azure

(사실상 리눅스에서 파워셀을 쓸 이유인) azure powershell도 됩니다.

```PowerShell
Install-Module AzureRM.NetCore
```

Install-Module로 .NET Core용 Azure PowerShell을 설치할 수 있습니다.