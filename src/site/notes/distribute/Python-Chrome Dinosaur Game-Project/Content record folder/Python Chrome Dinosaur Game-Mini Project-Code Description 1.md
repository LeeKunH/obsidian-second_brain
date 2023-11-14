---
{"dg-publish":true,"permalink":"/distribute/python-chrome-dinosaur-game-project/content-record-folder/python-chrome-dinosaur-game-mini-project-code-description-1/","tags":["파이썬/프로젝트"],"noteIcon":""}
---

### 날짜 2023-11-02 22:09

# 주제-키워드 =>



---
# 연관된 기록 =>
위에서 작성한 내용과 연관성이 있는 기록-노트를 연결.
" [[]] "
- 



---
### 코드1
```python
'''
C:\Users\GUN\OneDrive - 한국산업기술대학교\바탕 화면\웹-개발-취업캠프\파이썬-크롬공룡게임\self_ChromeDinoGame\constants.py

프로젝트 구현에 필요한 코드파일들을 임포트함
'''

import pygame
import os

'''
# 전역 상수 정의 - 초기 게임 설정 값
# 게임화면\\스크린 설정.
# 게임 화면\\스크린 사이즈 값 정의


pygame 라이브러리에 있는 함수를 이용 게임 화면 설정값을 정의

공식문서_설명에 set_mode()함수의 인수에는 어떠한 값들이 들어가야 하는지 설명이 나와있음
'''

'''
선배 코드 벤치마킹을 통해
코드 추가
    ㅡ
    set_caption
    ㅡ
    icon
    ㅡ
    set_icon


ㅡ
`pygame.display.set_caption('달려라 공룡@@@')`을 사용하여 게임 창의 제목을 설정

'''
pygame.init()

SCREEN_HEIGHT = 1100
SCREEN_WIDTH = 600
SCREEN = pygame.display.set_mode((SCREEN_HEIGHT, SCREEN_WIDTH))
icon = pygame.image.load(os.path.join("self_ChromeDinoGame\\Assets\\Dino","DinoStart.png"))
pygame.display.set_caption('달려라 공룡@@@')
pygame.display.set_icon(icon)

'''
게임 속 객체들, 주변 그래픽드에 사용할 이미지들을 내 로컬환경에서 불러와 변수에 할당.
    ㅡ
    아하!
    내 특정한 로컬환경에 있는 이미지 파일을 스크립트 파일에 불러오기 위해선 저런 코드를 사용하는구나!
    .
    ㅡ
    스크립트 파일에 구체적으로 불러올 이미지 경로를 os.path.join()으로 알려주고 있음
    ㅡ
    pygame모듈.image모듈.load함수를 사용해 이미지 파일을 아마도? 코드파일이 읽을 수 있는 형태로 변수에 할당?



# 절대경로
C:\Users\GUN\OneDrive - 한국산업기술대학교\바탕 화면\웹-개발-취업캠프\파이썬-크롬공룡게임\self_ChromeDinoGame\Assets\Dino\DinoDuck1.png


# 상대경로
self_ChromeDinoGame\Assets\Dino\DinoDuck1.png


2개를 번갈아 출력하면서 게임 실행 시 뛰는 것 처럼 보이도록
RUNNING 동작은 이미지 파일 2개임
따라서 리스트 데이터 타입으로 묶어서 변수에 할당.
즉, 러닝이라는 동작을 구현하기 위해 RUNNING 변수를 정의 > 이미지를 할당
    ㅡ
    따라서 이미지가 1개면 굳이 리스트를 이용해 변수에 할당할 필요 X
    EX)JUMPING 확인

'''

'''
실습 영상에서는 2개 이미지를 생략했다.
내가 지금 추가한다
선배 코드를 참고해서

ㅡ DinoDead.png 추가
종료 공룡 아이콘

ㅡ DinoStart.png
시작 공룡 아이콘

ㅡ GameOver.png
게임종료 이미지

'''

RUNNING = [pygame.image.load(os.path.join("self_ChromeDinoGame\\Assets\\Dino","DinoRun1.png")), pygame.image.load(os.path.join("self_ChromeDinoGame\\Assets\\Dino","DinoRun2.png")) ]

JUMPING = pygame.image.load(os.path.join("self_ChromeDinoGame\\Assets\\Dino","DinoJump.png"))

DUCKING = [pygame.image.load(os.path.join("self_ChromeDinoGame\\Assets\\Dino","DinoDuck1.png")), pygame.image.load(os.path.join("self_ChromeDinoGame\\Assets\\Dino","DinoDuck2.png")) ]

START = pygame.image.load(os.path.join("self_ChromeDinoGame\\Assets\\Dino","DinoStart.png"))

DEAD = pygame.image.load(os.path.join("self_ChromeDinoGame\\Assets\\Dino","DinoDead.png"))

# C:\Users\GUN\OneDrive - 한국산업기술대학교\바탕 화면\웹-개발-취업캠프\파이썬-크롬공룡게임\self_ChromeDinoGame\Assets\Other

GAMEOVER = pygame.image.load(os.path.join("self_ChromeDinoGame\\Assets\\Other","GameOver.png"))

'''
ㅡ
게임 속 장애물 객체들 존재
EX) 큰 선인장 / 작은 선인장 / 새

위와 마찬가지로 게임 속 객체에 사용할 이미지를 불러오고 변수에 할당

ㅡ
게임 속 단순 배경 그래픽들 존재

'''
SMALL_CACTUS = [pygame.image.load(os.path.join("self_ChromeDinoGame\\Assets\\Cactus","SmallCactus1.png")),
                pygame.image.load(os.path.join("self_ChromeDinoGame\\Assets\\Cactus","SmallCactus2.png")),
                pygame.image.load(os.path.join("self_ChromeDinoGame\\Assets\\Cactus","SmallCactus3.png"))]

LARGE_CACTUS = [pygame.image.load(os.path.join("self_ChromeDinoGame\\Assets\\Cactus","LargeCactus1.png")),
                pygame.image.load(os.path.join("self_ChromeDinoGame\\Assets\\Cactus","LargeCactus2.png")),
                pygame.image.load(os.path.join("self_ChromeDinoGame\\Assets\\Cactus","LargeCactus3.png"))]

BIRD = [pygame.image.load(os.path.join("self_ChromeDinoGame\\Assets\\Bird","Bird1.png")),
        pygame.image.load(os.path.join("self_ChromeDinoGame\\Assets\\Bird","Bird2.png"))]

# 배경 요소_변수 정의
CL = pygame.image.load(os.path.join("self_ChromeDinoGame\\Assets\\Other", "Cloud.png"))
BG = pygame.image.load(os.path.join("self_ChromeDinoGame\\Assets\\Other", "Track.png"))

```
=>



