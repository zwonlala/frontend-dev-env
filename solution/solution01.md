# "1-webpack/1-entry" solution

<br>

## 먼저 npm 으로 프로젝트 설정

> npm init -y

-> -y 옵션: 기본값을 다 사용해서 package.json 파일 생성(설정)

그리고 package.json의 "scripts" 부분에 "build" 스크립트를 추가하여 `"build": "webpack"` 으로 설정함

<br>

## 그리고 기본 설정 파일을 생성

프로젝트 디렉터리에 **webpack.config.js** 파일을 생성하구 내부에

```
module.export = {

}
```

먼저 module.export 를 통해 webpack 설정 파일을 export  
(ES6가 사용하는 모듈이 아닌, 노드가 사용하는 모듈이므로 이렇게(이런 키워드를) 작성해야 함!)

필수적으로 사용해야하는 키워드가 3가지가 있음

- mode : development와 production이 잇음
- entry
- output

해당 키워드에 대한 설정을 해줌

```javascript
const path = require("path");

module.exports = {
  mode: "development",
  entry: {
    main: "./src/app.js",
  },
  output: {
    filename: "[name].js", //여기서 "[name]"이 부분이 위의 main으로 대치되게 설정
    //그리고 path를 설정해주기 위해 최상단에 path 모듈을 불러옴
    path: path.resolve("./dist"),
  },
};
```

<br>

## webpack을 설치하고 그 다음 아까 등록해둔 스크립트를 실행

> npm install -D webpack webpack-cli

위 문장을 통해 webpack을 설치하고

`npm run build` 명렁어를 실행하면

dist라는 폴더에 main.js 파일(번들링된 결과)이 생성됨!!

<br>

## 생성된 결과물을 index.html에 로딩

index.html의 주석부분에

```html
<script src="./dist/main.js"></srcipt>
```

위 문장을 삽입하구

cmd 창에 `open index.html` 문장을 실행하면 결과 화면이 나옴.

<br>

## 끗

<br>
<br>
<br>
<br>
