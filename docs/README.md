## 🎯 기능목록


### 1.입력기능
1-1.  서로 다른 3자리 수 입력을 받음 [v]
1-2.  입력이 서로 다른 3자리 수 인지 검사 [v]
1-3.  입력한 각각의 수가 1~9의 숫자인지 검사 [v]
1-4.  게임을 재시작 할것인지 종료할것인지 검사 [v]
1-5.  입력이 1인지 2인지 검사 [v]
1-6.  사용자가 잘못된 입력값을 입력 시 IllegalArgumentException 발생 후  [v]  

### 2.출력기능
2-1. 입력 파라미터에 따른 메시지 출력 [v]
2-2. 사용자 입력에 따른 힌트 메시지 출력 [v]
2-3. 힌트 메시지 출력 시 첫 입력이 볼이면 볼의 갯수 먼저 출력, 반대로 스트라이크면 스트라이크 갯수 먼저 출력 [v]
 



### 3. 숫자야구 기능
3-1.  숫자야구 정답 리스트 생성  [v]
3-2.  사용자 입력에 대한 볼, 스트라이크, 낫싱 결과 생성  [v]
3-3.  사용자 입력이 정답인지 판단  [v]
3-4.  게임 종료 후 사용자의 입력에 따라 재시작 혹은 종료   [v]


### 4.실행 기능
4-3.  시작 메시지를 출력하고 정답 리스트 생성  [v]
4-1.  사용자의 입력을 받고 힌트 메시지를 출력을 반복  [v]
4-1.  사용자의 입력이 정답일 시 사용자의 입력에따라 게임 재시작 혹은 종료  [v]
4-2.  IllegalArgumentException 발생 시 메시지 출력후 게임 종료 [v]


### 느낀점
- 요구사항들을 어떻게 분리하여 class를 작성할지 어려웠다. 
-> 출력만을 담당하는 OutPutManager, 입력만을 담당하는 InputManager, 게임에 필요한 기능들을 담당하는 GameManager, 
이들을 합쳐 전체적인 게임을 실행하는 Runner로 구성   
  
- 게임에서 자주 출력되는 메시지들을 어떻게 관리하다 할까 properties 파일로 추출
->각각의 메시지에 대한 출력 메서드를 만들까하다가 하나의 properties 파일에 모든 출력 메시지들을 관리하고 
하나의 메서드에서 해당 메시지의 properties key값을 파라미터로 받아 메시지를 출력하게 구현  

- 언뜻 간단해 보이는 요구사항이지만 만들다보니 생각보다 신경 쓸 부분이 많아지고 즉흥적으로 기능들을 추가하기 시작, 설계의 중요성을 깨닫게 되었다.
-> 힌트 메시지를 출력 시 사용자의 입력에 따라 볼, 스트라이크의 위치가 달라질 수 있다고 생각하였지만 테스트 케이스를 실행중 틀린것을 알게 되었다.
구현 시작 전 충분한 설계가 필요하다는것을 알게 되었다.