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
