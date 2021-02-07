# npm install
- express 설치하기
```shell
╰─$ npm install express
npm notice created a lockfile as package-lock.json. You should commit this file.
npm WARN npmtest@0.0.1 No repository field.

+ express@4.17.1
added 50 packages from 37 contributors and audited 50 packages in 1.926s
found 0 vulnerabilities
```
- morgan cookie-parser express-session 설치
```shell
╰─$ npm install morgan cookie-parser express-session
npm WARN npmtest@0.0.1 No repository field.

+ cookie-parser@1.4.5
+ express-session@1.17.1
+ morgan@1.10.0
added 10 packages from 5 contributors and audited 60 packages in 1.557s
found 0 vulnerabilities
```
```json
"dependencies": {
    "cookie-parser": "^1.4.5",
    "express": "^4.17.1",
    "express-session": "^1.17.1",
    "morgan": "^1.10.0"
  },
```
- 개발용 패키지 설치 (실제 배포시에는 사용되지 않음)
```shell
╰─$ npm install --save-dev nodemon

> nodemon@2.0.7 postinstall /Users/rio/npm-test/node_modules/nodemon
> node bin/postinstall || exit 0

Love nodemon? You can now support the project via the open collective:
 > https://opencollective.com/nodemon/donate

npm WARN npmtest@0.0.1 No repository field.

+ nodemon@2.0.7
added 118 packages from 57 contributors and audited 178 packages in 5.372s

11 packages are looking for funding
  run `npm fund` for details

found 0 vulnerabilities
```
```json
  "devDependencies": {
    "nodemon": "^2.0.7"
  }
```
- 전역(global) 설치
>패키지를 현재 폴더의 node_modules 에 설치를 하는 것이 아니라  
npm이 설치되어있는 폴더에 설치  
보통 명령어로 사용하기 위해 전역 설치함
```shell
╰─$ npm install -global rimraf
/Users/rio/.nvm/versions/node/v14.15.4/bin/rimraf -> /Users/rio/.nvm/versions/node/v14.15.4/lib/node_modules/rimraf/bin.js
+ rimraf@3.0.2
added 12 packages from 4 contributors in 0.645s

╰─$ rimraf node_modules
```
>전역설치한 패키지는 package.json 에 기록되지 않아 다시 설치할 때 어려움  
이러한 경우를 위한 npx 가 있음  
devDependencies에 기록 한 후, 앞에 npx 명령어를 붙여 실행하면 전역설치처럼 명령어로 사용가능
```shell
╰─$ npm install --save-dev rimraf
╰─$ npx rimraf node_modules
```
- 명령어 줄여쓰기
  1. npm install: npm i  
  1. save-dev: -D  
  1. globla: -g

# 기타 npm 명령어
- npm outdated: 업데이트 할 수 있는 패키지가 있는지 확인  
Current 와 Wanted 가 다르다면 업데이트가 필요
- npm update: 업데이트 가능한 모든 패키지가 Wanted 에 적힌 버전으로 업데이트
- npm update [패키지명]: 패키지 업데이트
- npm uninstall [패키지명]: 패당 패키지를 제거하는 명령어  
패키지가 node_modules 폴더와 package.json 에서 사라짐  
**npm rm 패키지명** 으로 줄여쓸수있음
- npm serach [검색어]: 패키지를 검색
- npm info [패키지명]: 패키지의 세부 정보를 파악  
package.json 의 내용과 의존 관계, 설치 가능한 버전 정보 등이 표시됨
- npm adduser: npm 로그인을 위한 명령어 (패키지를 배포할 때 로그인이 필요)  
npm 공식 사이트에서 가입한 계정으로 로그인  
- npm whoami: 로그인한 사용자가 누구인지 알림 (로그인 상태가 아니면 에러 발생)
- npm logout: npm adduser 로 로그인한 계정을 로그아웃
- npm version [버전]: package.json 의 버전을 올림
> **npm version 5.3.2** : 원하는 버전의 숫자를 넣음  
**npm version minor** : 해당 부분의 숫자를 1 올림
- npm deprecate [패키지명] [버전] [메시지]: 해당 패키지를 설치할 때 경고 메시지를 띄움
- npm publish: 자신이 만든 패키지를 배포
- npm unpublish: 배포한 패키지를 제거 (24시간 이내에 배포한 패키지만 제거가능)
- npm ci: package.json 대신 package-lock.json 기반하여 패키지 설치  
더 엄격하게 버전을 통제하여 패키지를 설치