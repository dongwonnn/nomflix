설계 순서

1. 기본 세팅
2. 페이지들 작성
3. home을 첫 페이지로 하기 위해 react-router 적용
4. Components/Routes.js에 몰아서 작성.
5. Header.js.
   각각 이동할 수 있는 li태그들 모음집
6. <Redirect from ="*" to="/"> 
   맞는 라우트가 없다면 다 검사 후에 이 / 페이지로 이동
7. Switch 이용해서 하나만 들어갈수 있게 설정
8. css 적용하는 방법. 알맞게 설정
   -> styled-componenet(LINK) 사용 가능
9. LINK를 ROUTER 밖에서 사용하면 안된다.
   10 . styled-reset : CS를 이용해서 CSS를 초기화해서 0의 상태에서 시작
   -> Components/GlobalStyles.js 파일에 글로벌적으로 쓸 css 작성.

   ```
   import { createGlobalStyle } from "styled-components"
   import reset from "styled=reset";
   const globalStyles = createGlobalStyle`
        ${rest};
        a{
            test-decoration:none;
            color:inherit;
        }
        *{
            box-sizing-border-box;
        }
        body{
            font-family:-apple-system~~
            fs: 14px;
            backc:rbga(20,20,20,1)
        }
        `
    export default globalStyles
   ```

   - App.js에 적용

10. 태그들 밑에 border-bottom 라인 긋기

    - SC에 props를 전달할 수 있음.
    - ${props => (props.current ? "blue" : "transparent")};
    - currnet : boolean 속성. currnet={조건식} -> 조건식이 참이면 true

11. WithRouter -> 컴포넌트 연결하기. Router에 정보 줄 수 있음.

    ```
    export default withRouter(({location : {pathname }})) => (
        <Header>
            // {console.log} 해서 어떤 값으로 구분해야하는지 확인
            <List>
                <Item current={pathname === "/"}>
                    <Slink>
                <Item current={pathname === "/tv"}>
                    <Slink>
                <Item current={pathname === "/search"}>
                    <Slink>
            </List>
        </Header>
    ))
    ```

## API 적용하기

1. src/api.js에 불러온다.
   - yarn add axios
   ```
   const api = axios.create({
       baseURL: ""
       params: {
           pai_key:""
           language: ""
       }
   })
   ```
   - fetch?

## Container
