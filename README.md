# java-calculator-precourse

## 1. 기능 요구 사항
[기능 요구 사항.md](./docs/%EA%B8%B0%EB%8A%A5%EC%9A%94%EA%B5%AC%EC%82%AC%ED%95%AD.md)

## 2. 기능 구현시 고려해야 할 사항
1. 구분자가 2개 이상 연속으로 오는 경우는 예외로 처리할 것인가?
   - 예외로 처리하지 않고 가장 마지막 구분자를 기준으로 분리하겠다.
   - 기본 골자가 되는 계산기도 연산자를 여러번 쓰면 덮어쓰기 되기 때문에 해당 방식으로 적용한다.
2. 커스텀 구분자가 여러 개인 경우는 예외로 처리할 것인가?
   - 예외로 처리하지 않고 이 또한 가장 마지막 커스텀 구분자를 기준으로 분리하겠다.
   - 이유는 위와 동일하다.

## 3. 기능 구현 상세 계획
### 1. 클래스 분리
   - Calculator 클래스
     - 계산기의 기본 기능을 담당하는 클래스
     - 문자열을 입력받아 계산하는 기능을 담당한다.

   - Parser 클래스
     - 문자열을 파싱하는 기능을 담당하는 클래스
     - 문자열을 입력받아 숫자와 구분자를 분리하는 기능을 담당한다.

   - Input 클래스
     - 입력에 대한 기능을 담당하는 클래스
     - 문제에 맞는 형식으로 입력받는 기능을 담당한다.

   - Output 클래스
     - 출력에 대한 기능을 담당하는 클래스
     - 문제에 맞는 형식으로 출력하는 기능을 담당한다.

### 2. 기능 구현 체크리스트
   - [v] 쉼표(,) 또는 콜론(:)을 구분자로 가지는 문자열을 전달하는 경우 구분자를 기준으로 분리한 각 숫자의 합을 반환한다.
   - [v] 커스텀 구분자를 지정하고 커스텀 구분자를 기준으로 분리한 각 숫자의 합을 반환한다.
   - [v] 구분자가 2개 이상인 경우 마지막 구분자로 적용하여 처리한다.
   - [v] 커스텀 구분자에 여러 개의 구분자가 들어온 경우 마지막 커스텀 구분자로 적용하여 처리한다.