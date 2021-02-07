# package.json

서비스에 필요한 패키지의 버전을 관리하는 파일

1. package name
> package 이름  
package.json 의 name 속성에 저장
2. version
> 패키지의 버전
3. entry point
>자바스크립트 실행 파일 진입점  
보통 마지막으로 module.exports 를 하는 파일을 지정  
package.json 의 main 속성에 저장
4. test command
>코드를 테스트할 때 입력할 명령어  
package.json scripts 속성 안의 test 속성에 저장
5. git repository
> 코드를 저장해둔 Git 저장소 주소  
package.json repository 속성에 저장
6. keywords
>npm 공식 홈페이지에서 패키지를 쉽게 찾을 수 있도록 해줌  
package.json keywords 속성에 저장
7. license
> 해당 패키지의 라이선스

## package.json 생성
```shell
╰─$ npm init
This utility will walk you through creating a package.json file.
It only covers the most common items, and tries to guess sensible defaults.

See `npm help init` for definitive documentation on these fields
and exactly what they do.

Use `npm install <pkg>` afterwards to install a package and
save it as a dependency in the package.json file.

Press ^C at any time to quit.
package name: (npm-test) npmtest
version: (1.0.0) 0.0.1
description: hello package.json
entry point: (index.js) index.js
test command: 
git repository: 
keywords: 
author: rio
license: (ISC) 
About to write to /Users/rio/npm-test/package.json:

{
  "name": "npmtest",
  "version": "0.0.1",
  "description": "hello package.json",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "author": "rio",
  "license": "ISC"
}


Is this OK? (yes) 

```

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