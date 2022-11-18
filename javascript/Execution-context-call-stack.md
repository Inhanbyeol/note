# Execution context
   
   
자바스크립트 코드가 실행되는 환경을 의미한다.
자바스크립트에서 대표적으로 두 가지 타입의 Execution context가 있다.

실행할 코드에 제공할 환경 정보들을 모아놓은 객체들로 자바스크립트의 동적 언어로서의 성격을 가장 잘 파악할 수 있는 개념이다.
   
**   1. Global Execution context   **
      자바스크립트 엔진이 처음 코드를 실행할 때 Global Execution Context가 생성된다. 생성 과정에서 전역 객체인 Window Object (Node는 Global) 를 생성하고 this가 Window 객체를 가리키도록 한다.
**   2. Function Execution context   **
      자바스크립트 엔진은 함수가 호출 될 때마다 호출 된 함수를 위한 Execution Context를 생성한다.    
      모든 함수는 호출되는 시점에 자신만의 Execution Context를 가진다.
      
      
### 자바스크립트는 실행 컨텍스트가 활성화되는 시점에 다음과 같은 현상이 발생한다.
  - 호이스팅이 발생한다(선언된 변수를 위로 끌어올린다)
  - 외부 환경 정보를 구성한다
  - this 값을 설정한다.


# call stack
### 코드가 실행되면서 생성되는 Execution Context를 저장하는 자료구조
   
   엔진이 처음 script를 실행할 때, Global Execution Context를 생성하고 이를 Call Stack에 push한다.  
   그 후 엔진이 함수를 호출할 때 마다 함수를 위한 Execution Context를 생성하고 이를 Call Stack에 push 한다.   
   자바스크립트 엔진은 Call Stack의 Top에 위치한 함수를 실행하며 함수가 종료되면 stack에서 제거(pop)하고 제어를 다음 Top에 위치한 함수로 이동한다.   
