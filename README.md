# 프로젝트 명

​

숫자야구 게임.

​

## 프로젝트 설명

​

console로 사용자의 값을 받아 게임을 진행

알고리즘 자체는 기존에 알고있던 숫자야구 게임과 크게 다르지 않음

restart 나 exit 절차를 추가

​

# 프로그램 틀

​

: 세 개의 class로 역할을 나누어 프로그램을 진행한다.

​

1. 게임을 시작할 메인 함수가 있는 Application class

 

2. 게임이 시작되어 진행될 Game class

  

3. Game class 에서 참조할 수들을 받아주는 Number class, 예외값 검사나 형변환의 기능도 맡는다.

​

​

## 기능 목록

​

### Game class

​

1. **gameStart** 함수 flag를 세워 특정 조건을 만족할 때까지 게임을 진행한다.

​

- flag의 false 값은 **setRestratOrExit** 함수에서 Exit 값 '2' 즉, '1' 값이 들어오지 않는다면 리턴된다.

​

​

2. **setRestratOrExit** 함수는 restart 값인 '1'이 입력되면 computer 정답값을 초기화 하고 리턴시켜 gameStart 함수를 계속하여 진행하게 한다.

​

- restart, exit 값을 받는 함수 **inputRestartOrExit**,

  

- 여기서 올바른 값이 들어왔는지 확인하는 함수 **isRightAnswer**

​

3. strike 와 ball 의 개수를 구하고 만일 정답일 때 setRestratOrExit 함수를 호출할 **printHint** 함수

​

- 정답이 아닌 값이 들어왔을 때 한 게임의 값을 리턴해줄 **makeHint** 함수

​

- computer 의 정답과 player의 답을 비교하여 strike 와 ball의 개수를 구할 **countStrike**, **countBall** 함수

​

#### console로 사용자의 값을 받는 과정이므로 예외값은 항상 검사해주어야 한다.

​

​

### Number class

​

- computer의 랜덤 정답을 리스트로 리턴해줄 **setRandomNumbers** 함수

  

- player의 답을 받아줄 **getInputNumber** 함수

  

- player의 답은 문자열로 들어온다. 문자열을 List 형으로 변환해줄 **stringToList** 함수

  

- player의 답 중 오류가 있는지 확인 하는 함수 만약 오류가 존재한다면 IllegalArgumentException를 반환한다.

  

- player의 답의 길이가 3이 아니라면 오류를 반환하는 **isThreeDigits** 함수,

  

- 숫자값이 아닌 다른 문자가 들어온다면 오류를 반환하는 **isNumber** 함수,

  

- 길이 3의 숫자 중 중복된 값이 있다면 오류를 반환하는 **isNotDuplicate** 함수
