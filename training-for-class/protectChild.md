- 문제
  2중 if문을 연습할 겸 어린이 보호 구역에서 자동차의 속도를 제어해보자
  - 출력 예시
  ![Alt text](image-3.png)
  1. 자동차 출발 문구 출력
  2. 속력 입력
  3. 30키로 이상이면 속도를 줄여주세요 출력
  4. 30키로 이하라면 주행을 계속 해주세요 출력
  5. 0이라면 자동차 정지 문구 출력하면서 종료
  - **2번부터 4번은 반복해야함!!**
- 조건
  - 클래스
    - Main
    - Car
    - Driver
    - 더 필요하다면 추가 가능하지만 최소한 이렇게 세개는 사용할 것
  - Main
    - dirver 인스턴스
    - 자동차 출발 문구
    - driverMotion 이라는 메소드 호출
  - Car
    - speed : int (private으로 설정할 것)
    - setSpeed() : 무조건 사용
    - getSpeed() : 무조건 사용
    - isNormalSpeed() : boolean
    - speedController()
  - Driver
    - dirverMotion()
  - 무조건 사용을 제외한 다른 메소드는 이름도 변경 가능하고 용도도 변경 가능함!
- 답
  ```java
  public class CarExample {
      public static void main(String[] args) {
          Driver driver = new Driver();

          System.out.println("자동차 출발");

          driver.driverMotion();
      }
  }
  ```
  ```java
  import java.util.Scanner;

  public class Driver {
      Scanner scanner = new Scanner(System.in);
      Car car = new Car();

      public void driverMotion() {
          while (true) {
              System.out.println("자동차 속력을 입력해주세요");
              int speed = scanner.nextInt();

              car.setSpeed(speed);
              car.speedController();

              if (speed == 0) {
                  System.out.println("자동차가 정지합니다.");
                  break;
              }
          }

      }
  }
  ```
  ```java
  public class Car {
      private int speed;

      public void setSpeed(int speed) {
          this.speed = speed;
      }

      public int getSpeed() {
          return speed;
      }

      public boolean isNormalSpeed() {
          if (this.speed > 0) {
              return true;
          } else {
              return false;
          }
      }

      public void speedController() {
          if (isNormalSpeed()) {
              if (getSpeed() > 30) {
                  System.out.println("속도를 줄여주세요");
              } else {
                  System.out.println("주행을 계속해주세요");
              }
          }
      }
  }
  ```
