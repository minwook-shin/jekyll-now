---
layout: post
title: 혼자 만든 python 프로그램
---

이번 포스트에서는 지난 1년간 파이썬을 어떻게 배웠는지 간략하게 쓰고, 혼자 처음 만들어본 ```ubuntu-ko-irc-in-python ```에 대해 짧은 기술 설명을 풀어 써보려고합니다.

## 파이썬 생각보다 어렵다

학교에서 관련 과목을 수강했을 때 느꼈습니다.

```양의 탈을 쓴 늑대```와 같다는 사실을요.

어디까지나 기초가 쉬워 보였던 겁니다.

처음에는,

```python
print("hello world") # 예시입니다.
```

처럼 간단하길래, 쉽다고 생각하고 쭉 배웠습니다.

근데 어느순간 딕셔너리를 나가고, 계속 학습 진행을 나가면서

```python
dic = {'one':'1_val', 'two':'2_val', 'three': '3_val'}
```

모듈까지 차례대로 나가더니...

```python
def __init__(self):
```

class 파트부터 갑자기 난이도 급상승하더군요.

*(최근에 객체지향 프로그래밍을 수강하니까 대략 객체가 뭔지는 알겠습니다.)*

그래서 다시 2학기 개강 전, 예전에 사둔 책인 [점프 투 파이썬](https://wikidocs.net/book/1)을 다시 읽어보고 구글링도 해서 제 개인 프로젝트를 만들어 개발(이라 하기도 민망한)을 해보았습니다.

이름은 [ubuntu-ko-irc-in-python](https://github.com/minwook-shin/ubuntu-ko-irc-in-python)이며, 
irclogs.ubuntu.com에 호스팅된 ubuntu-ko 채널을 바로 볼 수 있는 서버 프로그램입니다.
코드 자체는 20줄도 안됩니다.

## 뭔가 얻어가는 느낌

뭐라도 해보니까 조금 얻어가는게 있는 듯합니다.

크롤링 극초반 지식이지만, ```urllib```의 사용법도 학습하고, ```codecs```로 열어서 인코딩 바로 잡아주고, ```re``` 모듈도 체험해본 값진 시간이였습니다.

## 저만의 코드 복습

제가 혹시나 향후 까먹을 걸 대비해서 (저를 위해) 쉬운 코드도 되짚어 보려합니다.

```python
from _datetime import datetime
import time
import codecs
import urllib.request
import emoji
import re
```
datetime, time, codecs, urllib,emoji,re를 임포트해서 작성해봤습니다.

* datetime : today().strftime로 현재의 날짜와 시간을 문자열로 출력하기 위해 작성. 이 코드에서는 ("%Y/%m/%d")로 형식을 지정했습니다.

* time : 사실 코드에 직접 쓰이진 않지만, 작업 새로고침할 시간을 지정하기 위해 사용했습니다.

* codecs : 원래 open으로 바로해도 되지만, utf-8로 인코딩하기위해 사용했습니다.

* urllib.request :  url의 경로에서 파일을 받아와서 특정 이름으로 파일이름을 저장해줍니다. (url,file name)으로 사용합니다.

* emoji : 이모티콘을 파이썬에서 구현해주는 외부 모듈입니다. emojize 메소드를 사용하여 텍스트를 전부 인식하게해서 알아서 바꿔주도록 했습니다 ```=)```를 ```😃```과 같이 나타나게 해줍니다. 

* re : 정규 표현식 관련 모듈입니다. 자세한 언급은 생략합니다.

```python
today_date = datetime.today().strftime("%Y/%m/%d")
u = ("https://irclogs.ubuntu.com/" + today_date + "/%23ubuntu-ko.txt")
```

irclogs.ubuntu.com에 날짜 형식을 보시면 아시겠지만, 2017/12/24처럼 되어있기 때문에 날짜 형식을 지켜줍니다.

그리고 나머지 링크를 합쳐줍니다.

```python
while True:
    down = urllib.request.urlretrieve(u, "ubuntu-ko.txt")
    f = codecs.open("ubuntu-ko.txt", "r", "utf-8")
    text = f.read()
    filter_slack = emoji.emojize(re.sub("<bridgebot>", "[Slack]", text))
    print(filter_slack)
``` 

나머지 링크 합쳐놓은 것(u)을 합쳐서 내려받고, utf-8 변환해서, 불러들이고, 일부 고쳐야 될거 고쳐주고. 이모지(이모티콘)지원한것을 바로 ```print```해줍니다!

## 컴파일 오류

모듈 가져온것중에 대부분 빌트인된 것만 썻지만, 이모티콘을 처리하기 위해 외부 모듈을 가져다가 썻습니다.

```python
import emoji
```
아마도 위와 같은 코드를 pure 파이썬에서 작성하면 작동안합니다.

따로 pip로 설치해야 합니다.

```bash
$ pip install emoji --upgrade
```

혹은 깃허브를 클론해서 설치해도 됩니다.
```bash
$ git clone https://github.com/carpedm20/emoji.git
$ cd emoji
$ python setup.py install
```

# 마무리

이 글을 마치며 생각해보니, 위 프로젝트는 더 만들려고 구상해둔 계획이 더 있는데 딴 프로젝트를 진행하면서 하니까 개발 진행 속도가 거의 안나는거 같습니다.

일정한 계획이 있는 것도 아니니까 틈틈히 시간나는데로 열심히 해봐야겠습니다.


### * 2017/12/27 수정 : 일부 오타를 고쳤습니다.