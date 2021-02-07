# package 버전 
SemVer 방식의 버전 넘버링  
SemVer: Semantic Versioning (유의적 버전)
> [Major].[Minor].[Path]  
Major: 하위 호환이 되지 않는 변경사항  
Minor: 하위 호환이 되는 변경사항  
Patch: 간단한 버그 수정

## 어떤 버전을 설치해야 하는지 알리기
* [^] : Minor 버전까지만 설치하거나 업데이트
> **express@^1.1.1**  
1.1.1 이상부터 2.0.0 미만 버전까지 설치됨  
2.0.0 버전은 설치되지않음  
1.x.x 와 같이 표현 할 수도 있음  
minor 버전까지는 호환이 보장되기 때문에 ~ 보다 ^를 많이 사용함
* [~] : Patch 버전까지만 설치하거나 업데이트
> **npm i express@~1.1.1**  
1.1.1 이상부터 1.2.0 미만 버전까지만 설치됨  
1.1.x 와 같이 표현 할 수도 있음
* [>] [<] [> =] [< =] [=] : 초과, 미만, 이상, 이하, 동일
> **npm i express@>1.1.1**  
1.1.1 보다 높은 버전이 설치됨
* @latest : 안정된 최신 버전의 패키지 설치
>**npm i express@latest**  
**npm i express@x**

* @next : 가장 최근 배포판을 사용  
@latest 와 다르게 안정되지 않은 알파, 베타버전의 패키지를 설치할 수 있음
>알파: **1.1.1-alpha.0**  
베타: **2.0.0-beta.1**  
출시직전: **2.0.0-rc.0** (rc: Release Candidate)
