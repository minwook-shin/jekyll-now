---
layout: post
title: Ubuntu 18.04에서 .NET Core 설치하고 hello world 실행하기
---

오늘은 우분투 18.04로 닷넷 코어를 설치하는 방법을 포스팅해보려고 합니다.

## Microsoft key and feed

우선 마이크로소프트의 gpg키와 피드를 내려받습니다.

SDK와 런타임을 받을 때에 공동으로 사용됩니다.

아래 설명은 우분투 18.04를 기준으로 설명된 명령어입니다.

```bash
wget -qO- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.asc.gpg
sudo mv microsoft.asc.gpg /etc/apt/trusted.gpg.d/
wget -q https://packages.microsoft.com/config/ubuntu/18.04/prod.list 
sudo mv prod.list /etc/apt/sources.list.d/microsoft-prod.list
```

## .NET Core SDK

닷넷 코어 파일들을 빌드할 SDK를 내려받습니다.

```
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install dotnet-sdk-2.1.105
```

## .NET Core Runtime

빌드된 닷넷 코어 파일들을 실행할 런타임을 내려받습니다.

```
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install dotnet-runtime-2.0.7
```

## 생성

프로젝트 폴더에서 ```dotnet new console```을 실행해서 콘솔 기본 템플릿과 csproj 파일들을 생성합니다.

## 실행

생성된 cs파일을 살펴보면 아래와 같이 기본 틀이 형성됩니다.

```c#
using System;

namespace dotnet_core_test
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Hello World!");
        }
    }
}
```

```dotnet run```을 실행하여 컴파일되면서 hello world가 출력됩니다.