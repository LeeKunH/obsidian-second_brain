---
{"dg-publish":true,"permalink":"/distribute/python-chrome-dinosaur-game-project/content-record-folder/python-chrome-dinosaur-game-mini-project-code-description-2/","tags":["파이썬/프로젝트"],"noteIcon":""}
---

### 날짜 2023-11-05 16:30

# 주제-키워드 =>



---
# 연관된 기록 =>
위에서 작성한 내용과 연관성이 있는 기록-노트를 연결.
" [[]] "
- [[distribute/Python 파이썬/Content record folder/타입힌트용 클래스-타입힌트기호\|타입힌트용 클래스-타입힌트기호]]


-------------------------------

### 코드1
```python
C:\Users\GUN\OneDrive - 한국산업기술대학교\바탕 화면\웹-개발-취업캠프\파이썬-크롬공룡게임\self_ChromeDinoGame\main.py

import pygame
import os
import random
from constants import * # 전역상수 코드 따로 정의 후 불러와 사용.

'''
ㅡ
게임 화면에 공룡 플레이어 존재
따라서 Dinosaur 클래스 정의 후 Dinosaur 인스턴스-객체-요소 생성 진행
'''

class Dinosaur() :
    '''
    ㅡ
    게임 속 객체는 화면 스크린 상 위치할 좌표를 설정해야함
    X_POS
    Y_POS

    Y_POS_DUCK
    공룡 엎드려 달릴 때 좌표점 달라짐
    ㅡ
    JUMP_VEL 이 변수가 가지는 의미를 잘생각.
    옵시디언 "점프상황-코드 이해" 내용 확인

    '''

    X_POS = 80
    Y_POS = 310
    Y_POS_DUCK = 340
    JUMP_VEL = 8.5 # 공룡 점프 시 높이

    '''
    ㅡ
    Dinosaur클래스 생성자 메서드 정의.
        인스턴스가 생성되자마자 들어갈
        생성자 메서드 내부에는 공룡 캐릭터 초기 설정값들을 정의한다.

    ㅡ
    전역 상수에 할당한 이미지 데이터들을 해당 클래스 인스턴스에 할당되도록 클래스 속성에 할당
    duck_img
    run_img
    jump_img

    '''
    def __init__(self) -> None:
        self.duck_img = DUCKING
        self.run_img = RUNNING
        self.jump_img = JUMPING

        '''
        ㅡ
        공룡 객체 초기 자세 설정.
        특정 조건에 따른 흐름제어
            특정 조건에 따른 적절한 행동 이미지 사용

        ex) 사용자가 특정 키를 누르면...특정 이벤트를 발생시키면 그에 따른 흐름제어
        동작 이미지 설정
        동작 조건 설정

        따라서 초기 동작은 dino_run 이구나

        '''
        self.dino_duck = False
        self.dino_run = True
        self.dino_jump = False

        '''
        ㅡ
        step_index는 초당 프레임과 연관성 있음
        프레임.

        ㅡ
        공룡 객체 self.image이미지.
        처음에는 run_img 리스트에 들어있는 0번 이미지로 설정
            ㅡ
            위에서 우리는 run 이미지를 2개 사용한다고 정의함.
            0번 인덱스 이미지 <> 1번 인덱스 이미지를 번걸아 가면서 사용해 캐릭터 동작 구현

        ㅡ
        jump_vel
        공룡 객체가 점프하는 상황을 코드로 구현하기 위해 위에서 정의한 점프한 높이_속도 값 의미를 가지는 self.JUMP_VEL값을 업데이터 되면서 계속 변해야 하기 떄문에 self.jump_vel 할당함

        즉, self.JUMP_VEL 이 값은 초기 설정값
        그 이후 점프라는 동작이 발생하면 self.jump_vel값은 계속 업데이트된다 변한다.
        '''
        self.step_index = 0
        self.jump_vel = self.JUMP_VEL
        self.image = self.run_img[0]


        '''
        ㅡ
        공룡 객체 피격범위를 설정함
        dino_rect이 변수 안에 get_rect()함수가 이미지 사이즈에 따른 충돌박스 사이즈를 구해줌
        ㅡ
        게임 화면에 존재하는 모든 것들 스크린 안에 존재하도록 좌표점 설정
        피격박스 위치 설정
            ㅡ
            위에서 이미 공룡 객체 좌표설정함
            공룡 객체 피격박스는 당연하게도 공룡 객체와 같다.
            ㅡ
            변수 헷갈림 주의
            self.X_POS : 공룡 객체의 좌표
            dino_rect.x: 공룡 객체의 충돌박스 좌표

        '''
        self.dino_rect = self.image.get_rect()
        self.dino_rect.x = self.X_POS
        self.dino_rect.y = self.Y_POS


    '''
    ㅡ
    update()
    공룡 클래스 내부에 메서드 정의
        사용자가 특정 키를 눌렀을 때 = 특정 이벤트가 발생했을 때에 따른
        흐름제어_동작제어 구문을 작성

    따라서 update메서드 안에 매개변수_인수로 위에서 정의한 userInput값이 들어간다. 인수로서

    위에서
    self.dino_duck = False
    self.dino_run = True
    self.dino_jump = False
    동작 조건이 들어있는 변수를 정의함.

    '''

    def update(self, userInput) :
        if self.dino_duck :
            self.duck()
        if self.dino_run :
            self.run()
        if self.dino_jump :
            self.jump()

        '''
        ㅡ
        초기
        공룡 객체의 self.step_index = 0 이였음.

        step_index는 점점 커진다.
        특정 조건_크기가 되면 다시 0부터 증가되도록 코드 작성 = 초기화 설정 코드 작성
        특정 조건에 따른_상황에 따른 흐름제어를 하고 싶을 땐 if문을 사용하는것

        '''
        if self.step_index >= 10 :
            self.step_index = 0

        '''
        ㅡ
        사용자가 특정 이벤트를 발생시키면 = 특정 키보드의 입력이 감지되면
        흐름 제어 코드 작성
        동작 제어 코드 작성

        ㅡ
        위에서 userInput = pygame.key.get_pressed() 정의함
        따라서 userInput 변수에는 특정한 값이 할당되어 있는 상태

        사용자가 K_UP 누르고 점프 상태가 아니라면 점프한다
        코드 작성

        이해 ㅇㅇㅇ
        키를 눌렀을 때 공룡 캐릭터 점프 되야함

        주의 =>
        단순하게 생각하면 조건 명제를 (userInput[pygame.K_UP]) 이외에 (self.dino_jump)를 한번 더 작성한 이유를 생각해보자
            ㅡ
            뒤 조건명제를 작성하지 않았다면
            이단 점프가 발생할 수 있다.
            이단점프는 내가 원하는 동작이 아니다.
            따라서
            추가적인 조건명제를 작성한 것.

        ㅡ
        사용자가 K_DOWN를 누르고 + 점프 상태가 아니라면 > 엍드리는 동작조건 True변경 > 동작 실행

         ㅡ
        사용자가 점프 상태가 아니라면 + K_DOWN를 누르지 않았다면 > run 조건 True 변경
            = 달리는 상태라면

        '''

        if userInput[pygame.K_UP] and not self.dino_jump :
            self.dino_duck = False
            self.dino_jump = True
            self.dino_run = False
        elif userInput[pygame.K_DOWN] and not self.dino_jump :
            self.dino_duck = True
            self.dino_jump = False
            self.dino_run = False
        elif not (self.dino_jump or userInput[pygame.K_DOWN]) :
            self.dino_duck = False
            self.dino_jump = False
            self.dino_run = True

    '''
    ㅡ 이 부분과 연관성 있음
        def update(self, userInput) :
        if self.dino_duck :
            self.duck()
        if self.dino_run :
            self.run()
        if self.dino_jump :
            self.jump()

    따라서 아래부터는 해당 동작에 따른 함수를 정의_기능을 정의
    '''


    def duck(self) :

        self.image = self.duck_img[self.step_index//5]
        self.dino_rect = self.image.get_rect()
        self.dino_rect.x = self.X_POS
        self.dino_rect.y = self.Y_POS_DUCK # run 달라 좌표점
        self.step_index += 1

    def run(self) :

        '''
        ㅡ
        위에서 전역 상수에 할당한 "달리기"이미지를 인스턴스 변수에 할당
        RUNNING = [pygame.image.load(os.path.join("Assets/Dino","DinoRun1.png")), pygame.image.load(os.path.join("Assets/Dino","DinoRun2.png")) ]

        self.run_img = RUNNING
            self.image = self.run_img[0]

        위에서 초기 이미지로 0번 인덱스 이미지로 할당했음
        하지만 게임 구현 상상.
        0번 <> 1번 번갈아 가면서 self.run_img 객체 run이미지에 할당되야함
            ㅡ
            그 이후 self.image 객체 현재 상테 이미지에 할당되야 하고

        ㅡ
        이러한 상황을 구현하기 위해 리스트 안에 인덱싱을 self.step_index//5 이러한 로직을 작성한 것
            ㅡ
            self.step_index 객체 스탭 변수의 값이 1씩 증가됨.
            0 1 2 3 4 5 6 7 8 9 10
            0 0 0 0 0 1 1 1 1 1 1  ....
            이러한 흐름이 발생
                ㅡ
                이해 ㅇㅇㅇ

        ㅡ
        def update(self, userInput) :
        이 함수가 호출되면 step_index값을 매번 확인함.
        '''

        self.image = self.run_img[self.step_index//5]
        self.step_index += 1 # 1씩 증가 -> 10이 되는순간 값 초기화

        '''
        ㅡ
        위에서 아래와 같은 코드구분을 작성했었음
            ㅡ
            def __init__(self) 생성자 메서드 내부에 작성.
            ㅡ
            지금은 def run() 내부에 작성.

        그때는 공룡 클래스 인스턴스 생성시 초기값을 설정한 의미

        이번에 다시 같은 코드를 작성한 이유=>
        특정 동작에 따라서 좌표값이 변하기 때문
            달리는 상황 좌표점
            점프 동작 좌표점
            엎드리기 동작 좌표점

        따라서 모든 동작 메서드 함수 내부에 같은 코드가 반복된다.
        '''
        self.dino_rect = self.image.get_rect()
        self.dino_rect.x = self.X_POS
        self.dino_rect.y = self.Y_POS
        self.step_index += 1 # 1씩 증가 -> 10이 되는순간 값 초기화

    # 점프 동작 함수 정의
    '''
    ㅡ
    점프 동작을 했을 때 필요한 값들이 호출되도록_생성되도록 하는 함수 정의
        점프 동작에 대한 자세한 내용은 기록확인
    '''
    def jump(self) :
        '''
        ㅡ
        점프를 하면
        객체 이미지에 점프 이미지로 초기화_할당

        ㅡ
        이 부분에 대한 자세한 설명은 기록확인
        '''
        self.image = self.jump_img
        if self.dino_jump :
            self.dino_rect.y = self.dino_rect.y - self.jump_vel * 4
            self.jump_vel = self.jump_vel - 0.8

        if self.jump_vel < -self.JUMP_VEL :
            self.dino_jump = False # 점프가 끝난 상황
            self.jump_vel = self.JUMP_VEL # 다시 처음값으로 초기화 // 왜? 점프는 언제든 다시 가능


    '''
    ㅡ
    위에서 다양한 동작 함수를 정의함.
        ㅡ
        해당 동작함수가 호출되면 그 동작후녀에 필요한 설정값들이 생성된다.
            ㅡ
            따라서 그 이후에는 화면에 그 상황을 그려줘야 한다
            draw함수를 정의
    SCREEN을 그려줘야 한다.
    따라서 함수의 매개변수_인수로서 SCREEN이 들어가기에 매개변수 이름도 SCREEN으로 설정한다.
        ㅡ
        그게 명명 규칙
    ㅡ
    내가 정의하지 않았지만
    blit() 함수를 사용해 화면을 그려준다.
        ㅡ
        1번 매개변수에는 객체의 이미지가 들어감, 2번 매개변수에는 좌표점이 들어간다
    '''

    def draw(self, SCREEN) :
        SCREEN.blit(self.image, (self.dino_rect.x, self.dino_rect.y))

'''
ㅡ
배경에 존재하는 구름 객체를 위한 클래스 정의
'''

class Cloud() :
    '''
    ㅡ
    생성자 메서드 내부에는 해당 객체의 초기 설정값들이 들어간다. 작성된다.
        ㅡ
        초기 x 위치_좌표값 정의.
        초기에는 게임 스크린 보다 오른쪽에 존재하는 상황.
        따라서 처음에는 보이지 않는다.
        ㅡ
        초기 y 위치 좌표값 정의.
        구름은 하늘에 존재한다.
        따라서 코드를 저렇게 작성하면서 구름의 위치가 상단에 출력되도록 한다.
        ㅡ
        구름 객체에 절대 상수로 정의한 이미지 할당
        ㅡ
        get_width()함수를 이용해 로컬에 있는 구름 이미지의 사이즈를 파악
        왜?
        update()함수에서 이 값이 필요하기 때문.
        그래서 구름이 계속 초기화 가능해짐

    '''
    def __init__(self) -> None:
        self.x = SCREEN_WIDTH + random.randint(300, 500)
        self.y = random.randint(50, 100)
        self.image = CL
        self.width = self.image.get_width()

    '''
    ㅡ
    구름 객체의 초기 설정값이 게임이 진행됨에 따라서 계속 업데이트 되야 하기 때문에 그러한 기능을 수행하는 함수정의.
    '''
    def update(self) :
        '''
        ㅡ
        배경이 어떻게 이동이 되고 있는지 자세한 설명은 옵시디언 기록 확인
        ㅡ
        조건문 의미 =>
        구름 x 좌표값이 게임 스크린 영역을 넘어가는 순간 다시 원래 위치에서부터 시작하도록 값을 초기화
            ㅡ
            원래 위치로 보내도 되지만 구름이 자주 등장하지 않도록?
            초기 위치보다 좀 더 멀리 보내준다.
        '''
        self.x -= game_speed

        if (self.x < - self.width ) :
            self.x = SCREEN_WIDTH + random.randint(1300, 2000)
            self.y = random.randint(50, 100)

    '''
    ㅡ
    화면에 보이는 모든 객체는 결국 게임 스크린에 출력_그려져야 함.
    따라서 그러한 기능을 수행하는 draw()함수 정의
    '''


    def draw(self, SCREEN ) :
        SCREEN.blit(self.image, (self.x, self.y))

'''
ㅡ
게임 안에 장애물 요소 존재.
따라서 해당 클래스 정의
'''
class Obstacle :
    '''
    ㅡ
    장애물 객체 초기값 설정_정의

    ㅡ
    다른 클래스에서는 
    self.image 객체 이미지 변수에 해당 이미지를 바로 할당함.
    하지면 여기선 image 매개변수를 할당함.
    왜?
    현재 이 클래스는 장애물-부모 클래스이기 때문

    자식 클래스에서 부모 클래스를 상속받고 > 자식클래스에서 부모 클래스의 생성자를 호출해야 그떄서야 해당 이미지가 객체 이미지 변수에 할당됨.

    즉, self.image = image 이부분은 자식클래스에서 image어떤 값이 들어갈지 정해짐

    ㅡ
    type 매개변수를 정의한 이유.
    현재 장애물-선인장 이미지 다양함.
        작은 선인장 이미지 3개
        큰 선인장 이미지 3개
    위에서 모두 리스트로 묶어 저장했음
    따라서 랜덤하게 선인장 이미지들을 인덱싱 후 랜덤하게 화면에 출력하기 위함.
    즉, 랜덤하게 이미지를 인덱싱하기 위한 인덱스


    
    '''
    def __init__(self, image, type) -> None:
        self.image = image
        self.type = type
        '''
        ㅡ
        현재 image값이 자식클래스에 넘어온 리스트임
        type에 결정된 값에 따라서 인덱싱이 된 이후에 그 이미지의 충돌박스 사이즈를 위해 코드가 저렇게 작성되어 있음

        '''
        self.rect = self.image[self.type].get_rect()
        '''
        ㅡ
        장애물 좌표값 설정
        게임 실행 상황 생각.
        스크린 오른쪽 > 왼쪽으로 이동함
        따라서 처음 x값은 딱 화면 폭값으로 설정한 것
        '''
        self.rect.x = SCREEN_WIDTH

    # 선인장을 값을 위한 함수 정의
    '''
    ㅡ
    게임이 진행되면서 계속 업데이트 되야함
    그러한 기능을 구행하는 update 함수 정의

    '''
    def update(self) :
        '''
        ㅡ
        아래 코드를 통해
        오른쪽 > 왼쪽으로 이동하는 상황 코드로 정의
        '''
        self.rect.x -= game_speed


        '''
        ㅡ
        위에서 정의한 다른 이동하는 객체?들은 화면 영역을 벗어나면 다시 처음 값으로 초기화를 진행함.

        하지만 이 객체는 pop메서드를 사용해 아예 제거함

        왜?
        제거해주지 않으면 화면 영역밖을 벗어난 선인장 값들이 메모리에 계속 쌓이는 상황이 발생

        '''

        if self.rect.x < - self.rect.width :
            '''
            ㅡ
            아래 코드 의미 
            리스트 마지막 값을 반환하고 
            원본 객체에서 제거한다
            '''
            obstacles.pop()

    '''
    ㅡ
    게임 속 객체를 정의했으면
    최종적으로 draw 그려줘야 한다.
    '''
    def draw(self, SCREEN) :
        SCREEN.blit(self.image[self.type], self.rect)

'''
ㅡ
장애물-작은 선인장 객체 정의
'''
class SmallCactus(Obstacle) :
    '''
    ㅡ
    생성자 내부에 초기값 정의

    ㅡ
    부모 클래스에 작성된 type 값이 자식클래스에서 결정된다.
    의미
        리스트에 들어있는 이미지들을 랜덤하게 가져오기 위해

    ㅡ
    super 함수를 사용해서 
    자식 클래스에서 결정된 값을
    부모 클래스의 생성자메서드를 호출해 값을 할당하고 있다.
        ㅡ
        이 코드로 super함수를 제대로 이해함
        부모 클래스의 메서드를 호출하고 있는 것.
        직접 호출
        원래는 자동호출이지만 자식 클래스에서 호출해 사용

    '''
    def __init__(self, image) -> None:
        self.type = random.randint(0,2)
        super().__init__(image, self.type)
        self.rect.y = 325

class LargeCactus(Obstacle) :
    def __init__(self, image ) -> None:
        self.type = random.randint(0,2)
        super().__init__(image, self.type)
        # 큰 선인장 y 좌표값
        '''
        ㅡ
        큰 선인장이 작은 선인장 y값보다 작다
        당연하다
        큰 선인장이 원점과 더 가까워야한다 더 크니까.
        '''
        self.rect.y = 300

class Bird(Obstacle) :
    def __init__(self, image) -> None:

        '''
        ㅡ
        새 객체는 선인장 객체와 달리 이미지가 2개일뿐더라 동작하는 방식이 다르다.
            ㅡ
            0번 이미지 <> 1번 이미지 번갈아 가면서 출력이 되야한다.
            움직이는 것처럼 보이게 하기 위해
            ㅡ
            따라서 
            self.type = random.randint(0,2)
            이부분이 달라진다.
            선인장은 랜덤하게 type 값이 들어가야되고
            새는 0을 넣는다.
            ㅡ
            공룡 달리는 상황과 비슷
            따라서 self.index 작성
        '''

        self.type = 0
        self.index = 0
        super().__init__(image, self.type)
        self.rect.y = 250

    def draw(self, SCREEN):
        if self.index >= 9 : # 0 1 2 3 ~ 7 8 9되는 순간 초기화
            self.index = 0

        '''
        # 화면에 출력
        # 0번 이미지 1번 이미지를 번걸아가면서 출력 = 날개짓
        # 반복문에서 호출할떄마다 1씩 증가
        '''

        SCREEN.blit(self.image[self.index//5], self.rect)
        self.index += 1


'''
메인 함수 정의
'''

def main() :
    '''
    ㅡ
    아래 코드 확인
    game_speed 변수 정의함.
    파이썬 코드 네임스페이스_범위 생각

    이 함수 내부에서 정의가 되었지만 전체적으로 사용이되는 값이다.
    따라서 전역 변수로 정의.

    ㅡ
    x_pos_bg, y_pos_bg
    게임 스크린 배경에 대한 좌표 변수는 전역변수로 정의한다.
        ㅡ
        공룡이 땅위에서 달리고 뛰는 상황
    따라서 background() 함수 내부에 처음 x,y_pos_bg 변수가 정의된다.


    ㅡ
    points
    게임 점수를 측정하는 변수 전역변수로 정의

    ㅡ
    obstacles
    장애물 객체 변수 전역변수로 정의.
        ㅡ
        아래에서 리스트로 정의했음

    ㅡ
    실습코드에 작성한 폰트를 사용하면 한글이 출력되지 않는다.
    이유?
    따라서 선배 개발자 코드에 작성되어 있는 폰트로 변경해본다.

    '''
    global game_speed
    global x_pos_bg, y_pos_bg
    global points
    global obstacles


    '''
    ㅡ
    run 변수 정의
    게임 루프문을 작성해 게임을 반복 실행하기 위해
        반복문에 사용할 조건변수

    ㅡ
Clock 클래스 인스턴스 생성
    게임 상에서 시간을 측정하기 위해

    ㅡ
    공룡 클래스 인스턴스 생성 = 플레이어 생성
    player

    ㅡ
    game_speed
    게임 속도 설정값 정의

    게임 구현 생각 =>
    캐릭더가 움직이는 것 처럽 보이지만 사실 뒷배경이 움직이고 있는 것.

    ㅡ
    x_pos_bg
    공룡이 달리고 있는 배경_트랙의 좌표 초기값 설정

    ㅡ
    points 점수는 0부터 시작
    초기값 설정

    ㅡ
    cloud 
    클라우드 인스턴스 생성


    '''

    run = True
    clock = pygame.time.Clock()
    cloud = Cloud()
    player = Dinosaur()
    game_speed = 14
    x_pos_bg = 0
    y_pos_bg = 380
    points = 0
    # 라이브러리에 있는 폰트를 가져온다
    font = pygame.font.Font('freesansbold.ttf', 20)
    # font = pygame.font.Font(None, 20)
    obstacles = []
    death_count = 0

    '''
    ㅡ
    점수 기능 구현을 위해 함수 정의
    '''
    def score() :
        '''
        ㅡ
        게임 최종 구현 모습 생각

        시간이 지남에 따라서 난이도가 상승한다.
            = 게임 속도가 상승한다
        이러한 상황을 구현하기 위해 점수를 1씩 증가시킨다.

        '''
        global points, game_speed
        points += 1

        '''
        ㅡ
        포인트 100단위로 게임 난이도를 올리는 상황을 저러한 코드로 작성

        ㅡ
        text
        점수 표시를 위한 글씨 설정 진행

        마찬가지로
        화면에 출력하기 위해선 범위를 지정해줘야 한다
        따라서 get_rect() 함수 사용 후 위치 설정 진행

        ㅡ
        textRect.center
        게임 실행이 되면서 화면에 점수가 출력된다
        오른쪽 상단에



        '''

        if points % 100 == 0 :
            game_speed += 1

        text = font.render(f"points : {str(points)}", True, (0,0,0))
        textRect = text.get_rect()
        textRect.center = (1000,40)
        SCREEN.blit(text, textRect)

    # 백그라운-배경을 새성하기 위한 함수 정의
    '''
    ㅡ
    게임 속 배경 구현을 위한 함수 정의
    main() 내부에 배경에 사용할 변수를 정의했었음
    그것을 참조해서 사용하기 위해 global 예약어 사용

    '''

    def background() :
        global x_pos_bg, y_pos_bg
        '''
        ㅡ
        절대 상수에 존재하는 이미지의 폭값을 파악하기 위해 get_width() 사용 > image_width 변수에 할당
            ㅡ
            image_width는 배경 이미지 변수값임
            주의

        ㅡ
        화면에 출력
        blit() 이용.

        '''
        image_width = BG.get_width() # 대략 2404
        '''
        ㅡ
        현재 배경은 한번에 2장?을 출력함
        1번
           처음 초기값_좌표값 0, 380에 배경 이미지 출력
        2번
            0 + 2404 , 380 좌표값에
            배경이미지 한번 더 출력.
        왜?
        배경이미지는 1번이후 바로 뒤이어 출력이 되야 하기 때문.

        '''

        SCREEN.blit(BG, (x_pos_bg, y_pos_bg))
        SCREEN.blit(BG, (image_width + x_pos_bg, y_pos_bg))

        # 위 상황을 조건문으로 흐름 제어 / 뒷 배경이 스크린을 다 지나가면 다시 처음 처음 위치값으로 초기화

        '''
        ㅡ
        위 상황을 조건문으로 흐름 제어 진행
        뒷 배경이 스크린 영역을 다 지나가면 다시 처음 위치값으로 초기화 진행

        계속 생성되도록
        ㅡ
        위에서 정의한 game_speed 변수 값으로 화면이 이동하는 듯한 효과를 설정

        '''

        if x_pos_bg <= - image_width :
            SCREEN.blit(BG, (image_width + x_pos_bg, y_pos_bg))
            x_pos_bg = 0
        x_pos_bg -= game_speed

    '''
    ㅡ
    게임 루프문 작성
    게임 실행이 반복적으로 이루어짐

    ㅡ
    get()함수를 이용 사용자 이벤트를 감지함.
        함수 설명 확인. : List[Event]
        리스트로 반환출력됨
    리스트 안에 들어있는 요소는 Event객체
    내부 프로세스는 잘 모르겠으나 tpye속성에 특정한 값이 들어있음 숫자 타입으로
    그 값이 QUIT값과 같다면 게임 동작을 멈춤

    사용자가 종료버튼을 누르면....
    Q. 뭐가 종료버튼?? 어떤 키를 눌러야??

    '''

    while run :
        for event in pygame.event.get() :
            if event.type == pygame.QUIT :
                run = False

        '''
        ㅡ
        화면 스크린 색 설정
        (method) def fill(
            color: ColorValue,
            rect: RectValue | None = None,
            special_flags: int = 0
        ) -> Rect

        R,G,B 값으로

        ㅡ
        get_pressed()
        사용자가 이벤트-특정한 키를 누르는것을 감지하는 함수 사용
        userInput에 값 할당

        ㅡ
        `get_pressed()` 함수는 현재의 키보드 입력 상태를 가져오는 것
        즉, 단지 현재 상태값을 가져옴 = 입력 상태를 확인하는 함수
        따라서 이벤트 핸들러 코드라고는 부를 수 없음

        이벤트 핸들러보다는 게임 루프 내에서 주기적으로 호출되는 입력 처리 함수가 더 적절.

        '''
        SCREEN.fill((255, 255, 255))
        userInput = pygame.key.get_pressed()


        '''
        ㅡ
        위에서 공룡 클래스 정의 > 인스턴스 생성함
        공룡 = 플레이어를 화면에 그린다.
            ㅡ
            위에서 userInput변수 정의함.
            이 변수 안에는 사용자가 어떤 키를 눌렀는지에 대한 값이 들어가 있음
            따라서 사용자가 누른 값을 업데이트 진행
            update()
        '''

        player.draw(SCREEN)
        player.update(userInput)

        '''
        # 장애물 요소_객체 관련 부분
            # 장애물 요소_객체 3개
            # 0번 작은 선인장, 1번 큰 선인장, 2번 새
                # 작은 선인장, 큰 선인장은 이미지 3개
        
            # obstacles 리스트에 아무것도 없을 때
        '''
        if len(obstacles) == 0 : 
            if random.randint(0, 2) == 0 :
                '''
                # 작은 선인장 클래스 인스턴스를 obstacles리스트 요소값들로 넣어줌
                    # 작은 선인장 클래스 호출하기 위해선 image 인수 필요
                '''

                '''
                # 작은 선인장 클래스가 호출되서 해당 클래스 로직이 돌아가고 결국은 최종적으로 랜덤한 작은 선인장 이미지 1개가 obstacles 리스트에 들어간다

                 # 큰 선인장 클래스 인스턴스를 obstacles리스트 요소값들로 넣어줌
                # 큰 선인장 클래스 호출하기 위해선 image 인수 필요

                '''

                obstacles.append(SmallCactus(SMALL_CACTUS)) 
            elif random.randint(0, 2) == 1 :
                obstacles.append(LargeCactus(LARGE_CACTUS))
            elif random.randint(0, 2) == 2 :
                obstacles.append(Bird(BIRD))

        '''
        # 어떤 장애물 요소가 들어갔는지는 몰라도 부모 클래스에 있는 draw 메서드를 이용해서 화면에 출력
        '''
        for obstacle in obstacles : # 리스트 요소 반복
            obstacle.draw(SCREEN) # 화면에 장애물 출력
            obstacle.update() # 부모 클래스 업데이트 메서드 호출 - 객체 이동하는 모습을 위해

            '''
            # 플레이어-공룡-사각형과 장애물 사각형 충돌이 감지가 된다면
            2초간 딜레이 발생

            ㅡ
            충돌이 발생하면 카운트가 되도록 변수 정의
                ㅡ
                위에서 
                death_count = 0 정의함

            이 카운트를 메뉴에 표시하기 위해 menu함수 호출
            '''
            if player.dino_rect.colliderect(obstacle.rect) :
                pygame.time.delay(2000)
                death_count += 1 
                menu(death_count) 



        '''
        # 위에서 배경을 위한 함수를 정의함 - 호출
        # 위에서 구름 요소를 위한 클래스 정의함 - 구름 화면에 출력 - 업데이트
        ㅡ
        주의
        객체를 그려준다음에 이동이 되야한다
        따라서 draw > update 함수 호출
        '''
        background()
        cloud.draw(SCREEN) 
        cloud.update()

        '''
        ㅡ
        위에서 함수 정의했으니 호출한다
            main 함수 내부에 score함수 정의함
        지금은 while run 내부에서 호출.
        게임 루프가 돌면서 호출이 되야하니까
        '''
        score()
        
        
        '''
        ㅡ
        화면 주사율을 설정하는 코드 작성
        위에서 Clock클래스 인스턴스 생성함

        tick() 화면 주사율값 설정

        초당 30초 업데이트 설정
        update()

        '''
        
        clock.tick(30)
        pygame.display.update()


'''
ㅡ
게임에서 점수_메뉴 기능을 정의
main함수 내부에 정의한 points변수를 사용하기 위해 global 예약어 사용

'''
def menu(death_count) :
    global points

    '''
    # 초기 설정값 정의
        # 게임 실행을 위한 반복문 작성
    ㅡ
    주의
    현재 추가적인 화면을 정의하고 있따.

    즉 게임이 실행되는? 화면과
    게임 점수 메뉴가 출력되는 화면을 각각 정의함
    출력함

    
    '''
    run = True 
    while run : 
        SCREEN.fill((255,255,255)) 
        font = pygame.font.Font('freesansbold.ttf', 30)

        '''
        # 한번도 죽지 않았다면
            # 화면에 적절한 내용 출력할 값을 변수에 할당
        '''
        if death_count == 0 :
            text = font.render("Press any Key to Start!", True, (0,0,0))
            SCREEN.blit(START, (SCREEN_WIDTH // 2 - 20, SCREEN_HEIGHT // 2 - 140)) # 코드 추가
        elif death_count > 0 :
            text = font.render("Press any Key to Start!", True, (0,0,0))
            score = font.render("Your Score :  " + str(points), True, (0,0,0)) # 죽었을 때 점수를 출력
            scoreRect = score.get_rect() # 위치 파악을 위한 사각형 값 할당
            scoreRect.center = (SCREEN_WIDTH//2, SCREEN_HEIGHT//2 + 50) # 점수판 위치 설정
            SCREEN.blit(score, scoreRect)
            SCREEN.blit(DEAD, (SCREEN_WIDTH // 2 - 20, SCREEN_HEIGHT // 2 - 140)) # 코드추가
            SCREEN.blit(GAMEOVER, (SCREEN_WIDTH // 2 , SCREEN_HEIGHT // 2 - 100)) # 코드추가

        textRect = text.get_rect() # 메뉴에 출력될 텍스트 위치 설정을 위함
        textRect.center = (SCREEN_WIDTH//2, SCREEN_HEIGHT//2)# get_rect() 메서드 호출 후 반환값이 클래스 인스턴스고 그 안에 center 변수가 정의되어 있음
        SCREEN.blit(text, textRect)
        SCREEN.blit(RUNNING[0], (SCREEN_WIDTH//2 - 20 , SCREEN_HEIGHT//2 - 140)) # 화면에 위치 지정 후 객체_요소 출력
        pygame.display.update()

        '''
        # 사용자의 event 감지를 통한 게임 종료 진행 흐름 제어
                # pygame에 QUIT 변수에 들어있는 값과 사용자 동작 감지를 통한 값과 같다면
        '''
        for event in pygame.event.get() :
            if event.type == pygame.QUIT : # 의미 : 사용자가 게임 스크린 x 버튼을 누른다면....
                run = False
            if event.type == pygame.KEYDOWN : # 사용자가 아무런 키를 누르면 main 함수가 다시 실행되도록 작성
                main() # main 함수가 호출되면 > 게임 실행


'''
ㅡ
위에서 main함수 정의함
메인함수 호출 구문 작성
이렇게 작서하는 이유?
    ㅡ
    파이썬 코드 파일 호출 실수를 막기 위함
    해당 코드파일을 직접 실행했을 때만 작동
'''

if __name__ == "__main__":
    menu(death_count=0)

```

----
### ㅡ 코드/오류 수정


- 오류 발생 이유
스크립트 파일에서 이미지 파일 경로를 제대로 찾지 못해 발생한 오류임
`FileNotFoundError` 오류
	
ㅡ
이 오류를 해결하기 위해서는 이미지 파일 경로를 수정.
현재 코드에서 이미지 파일 경로는 슬래시 (`/`)로 구분되어 있으나, 윈도우즈 환경에서는 **백슬래시 (`\`)** 를 사용
+
백슬래시 (`\`)를 사용하는 것이 문제가 아니라 백슬래시가 **이스케이프 문자로 해석**되어 제대로 처리되지 않았기 때문입니다. 
	
> [!NOTE]
> =>
> 즉 백슬래시가 파일 경로를 위한 의미가 아니라 이스케이프 코드로 해석이 되어 발생한 오류
	
따라서 `\\`와 같이 백슬래시를 두 번 사용하면 하나의 백슬래시로 해석되어 파일 경로로 사용됩니다. 즉, 다음과 같이 코드를 수정해야 합니다:
##### 코드
```
RUNNING = [pygame.image.load(os.path.join("Assets\\Dino", "DinoRun1.png")), pygame.image.load(os.path.join("Assets\\Dino", "DinoRun2.png"))]

```




- 오류 발생 이유/코드
ㅡ 처음 코드
```
RUNNING = [pygame.image.load(os.path.join("Assets\\Dino","DinoRun1.png")), pygame.image.load(os.path.join("Assets\\Dino","DinoRun2.png")) ] # 동작에 대한 이미지가 2개임. 따라서 리스트로 묶어서 할당.
```
하지만 현재 실제 경로는
```
C:\Users\GUN\OneDrive - 한국산업기술대학교\바탕 화면\웹-개발-취업캠프\파이썬-크롬공룡게임\self_ChromeDinoGame\Assets\Dino\DinoRun1.png
```
따라서
```
RUNNING = [pygame.image.load(os.path.join("self_ChromeDinoGame\\Assets\\Dino","DinoRun1.png")), pygame.image.load(os.path.join("self_ChromeDinoGame\\Assets\\Dino","DinoRun2.png")) ] # 동작에 대한 이미지가 2개임. 따라서 리스트로 묶어서 할당.
```
이렇게 작성했어야함


---
# 출처-참고자료=>
- 



