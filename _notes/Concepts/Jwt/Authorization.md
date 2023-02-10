1. Authorization / 권한부여

-   권한부여는 누가 무엇을 할 수 있는지 결정하는 규칙
    -   파일, 데이터 등과 같은 시스템 리소스에 대한 액세스 수준을 결정하는 데 사용되는 보안 메커니즘
    -   예로 DBA는 데이터베이스 작성 및 삭제 권한이있는 반면 Software Engineer는 읽기 및 쓰기 권한만 주어짐


-   기본적으로 개인에게 조직의 기밀 리소스에 대한 부분 또는 전체 액세스 권한이 부여되는 프로세스

-   기술에는 역할 기반 액세스 제어, JSON 웹 토큰, SAML, OpenID 권한 부여, 0Auth 등이 있음


-   줄여서 **AuthZ**라고도 함

- Making sure that the user send request to your server is the same user that actually logged in during to authentication process

- This is normally done is by using session(cookies)