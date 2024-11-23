# React Deep Dive

2011년 페이스북의 뉴스피드 페이지에서 처음 선보인 리액트(React)
2018년을 기점으로 제이쿼리(jQuery)를 대체하는 프론트엔드 프레임워크로 자리잡음

왜 이렇게 빠르게 성장하고 있는가?

- 명시적인 상태 변경 : 리액트는 단방향 바인딩만 지원한다.
  Angular, Vue는 양방향 바인딩을 지원한다.
  아래 코드의 예시처럼 앵귤러는 name이 변경되는 곳을 모두 찾아야 하지만
  리액트는 setName이 호출되는 곳만 찾으면 된다.
  <b>하지만</b> 무조건 단방향이 좋다는 것이 아니고 데이터 흐름의 변화가 단순하기 때문에 코드 읽기가 쉽고 버그를 야기할 가능성이 비교적 적다는 점이 좋다는 것

  ```javascript
  // 앵귤러
  import { Component } from "@angular/core";
  @Component({
    selector: "app-name",
    template: `<input type="text" [(ngModel)]="name" />`,
  })
  export class AppComponent {
    name = "";
  }
  // 리액트
  import { useState } from "react";

  function App() {
    const [name, setName] = useState("");

    function handleChange(e) {
      setName(e.target.value);
    }

    return <input type="text" value={name} onChange={handleChange} />;
  }
  ```

- JSX : 자바스크립트 문법에 HTML 문법을 추가한 형태로 마치 태그 처럼 보이는 문법
- 강력한 커뮤니티, 그리고 메타 : 많은 이슈를 겪은 큰 커뮤니티가 존재, 또한 바벨과 같은 초대형 오픈소스 프로젝트도 재정난을 겪었지만 리액트는 메타라는 회사에서 지원하고 있어 안정적인 프레임워크로 자리잡음

위와 같은 이유로 리액트는 성장하고 있고 많은 사람이 사용하는 프레임워크로 자리잡고 있다.
때문에 실무에서 이미 많이 사용되고 있지만 그래도 모르는 것이 많아 공부하게 되었다.
