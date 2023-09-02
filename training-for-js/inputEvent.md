# input과 버튼에 간단한 이벤트를 만들어보자

- 문제
  수업시간에 했던 홈페이지로 넘어가기 실습을 더 정확한 방법으로 만들어보자
  - 이벤트리스너함수를 사용해보자
  - 돔 객체를 잡아서 제어해보자
- 순서
  1. 기본 셋을 복사해서 test.html에 붙여넣기
  2. getElementById 함수를 사용해서 돔 객체 잡기
  3. addEventListener를 사용하여 이벤트 생성
  ### 기본셋
  ```html
  <!DOCTYPE html>
  <html lang="kr">
    <head>
      <meta charset="UTF-8" />
      <meta name="viewport" content="width=device-width, initial-scale=1.0" />
      <style>
        #title {
          color: blue;
        }
      </style>
      <title>이벤트 처리</title>
    </head>
    <body>
      <h1 id="title">이벤트 처리하기!!!</h1>

      <form class="form">
        <input
          class=""
          id="text_input"
          type="text"
          name="주소적는 칸"
          placeholder="type window"
        />
        <input class="" id="btn" type="button" value="Create Window" />
      </form>

      <script type="text/javascript"></script>
    </body>
  </html>
  ```
- 답
  ```html
  <!DOCTYPE html>
  <html lang="kr">
    <head>
      <meta charset="UTF-8" />
      <meta name="viewport" content="width=device-width, initial-scale=1.0" />
      <style>
        #title {
          color: blue;
        }
      </style>
      <title>이벤트 처리</title>
    </head>
    <body>
      <h1 id="title">이벤트 처리하기!!!</h1>

      <form class="form">
        <input
          class=""
          id="text_input"
          type="text"
          name="주소적는 칸"
          placeholder="type window"
        />
        <input class="" id="btn" type="button" value="Create Window" />
      </form>

      <script type="text/javascript">
        let input = document.getElementById("text_input");

        function createWindow(myUrl) {
          new_window = window.open(
            myUrl,
            "이로운",
            "toolbar=no,width=400,height=300,directories=no,status=no,scrollbars=yes,resize=no"
          );
        }

        function getInputValue() {
          let textInput = document.getElementById("text_input").value;
          return textInput;
        }

        input.addEventListener("input", getInputValue);

        let btn = document.getElementById("btn");
        function btnEventListener() {
          let url = getInputValue();
          createWindow(url);
        }

        btn.addEventListener("click", btnEventListener);
      </script>
    </body>
  </html>
  ```
