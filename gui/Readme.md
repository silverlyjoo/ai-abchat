### GUI

사용자 커스텀 데이터를 학습시키는 파일입니다.
알고리즘 파트가 끝난 후 여기다가 연결합니다



#### 시작하기 전에

> pyqt5 설치하기

파이썬 gui를 사용하려면 PyQt5라는 패키지를 사용해야한다. PyQt5는 Qt어플리케이션 프레임 워크를 위해 Python에 바인딩된 세트라고 한다. **Qt어플리케이션 프레임워크 파이썬에 사용하기 위한 패키지**라고 보면 되겠다

Qt는 컴퓨터 프로그래밍에서 GUI프로그램 개발에 널리 쓰이는 크로스 플랫폼 프레임워크라고 한다

콘솔에 아래 명령어를 입력해 패키지를 설치해주자

```consol
pip install pyqt5
```

```
pip install pyqt5-tools
# 윈도우 창을 원활히 그리기위해서다.
```



> 그래프를 그릴 준비하기

콘솔에 아래 명령어를 입력해 패키지를 설치하자

```
pip install matplotlib
```

---

#### 시작하기

##### init

스타일에 대한 [참고자료](https://soma0sd.tistory.com/95?category=872646)



**initUI, setMoreUI, setFinalUI **

진행되는 상황에 따라 ui를 변화시킵니다.



**testData**

사용자가 학습된 모델을 확인해보기 위한 기능입니다.

사용자가 입력값을 주면, 각각의 알고리즘으로 계산한 뒤 정확도를 기록합니다.

기록된 정확도는 선그래프로 보여줍니다.





##### initUI

gui를 생성하는 부분입니다.
button, label, event등을 설정합니다.

- 아직 경로선택과 파일이름 입력, 데이터 입력에대한 검증절차를 넣지 않았습니다
- 기본 경로를 데스크탑으로 할까 합니다. 아직 구현하지 않았습니다



##### makeCM

학습시키는 버튼을 누를시 호출되는 함수입니다.
입력된 경로, 파일 이름, 선택된 학습 데이터로 알고리즘을 실행시킨 후 결과를 저장합니다.



##### showFileDialog

학습 데이터 선택 다이얼로그를 띄우는 함수입니다.



##### showPathDialog

저장 경로를 지정하기위해 다이얼로그를 띄우는 함수입니다.



**saveCLF**

사용자가 선택한 알고리즘으로 학습된 모델을
사용자가 지정한 경로에 입력한 이름으로 저장합니다.

확장나는 ```.clf```로 고정입니다





##### center

gui를 윈도우 중앙에 띄우기 위한 함수입니다.



---

### OpenServer.py

로컬 서버가 열리는 파일입니다.

app.py의 내용이 여기 연결됩니다.

- TODO List

  - 서버가 켜지면 초록불이, 꺼지면 빨간불이 노출됩니다.
  - 어떤 클라이언트가 접속했는지, 어떤 입력을 넣었고 아웃풋이 나갔는지를 모니터링하면 좋을것같습니다....만
  - 여러 클라이언트의 모니터링이 하나의 콘솔에 찍히면 너무 복잡할 것 같으니 채널을 나누면 좋을듯한데

  

..