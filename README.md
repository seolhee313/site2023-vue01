## Vue.js

youtube, movie와 같은 restful API를 postman사이트를 이용하여 데이터를 분류하고 그 중에서 원하는 데이터만 가져와서 사용했습니다.<br>
prettier, eslint를 이용해 문법에 오류가 없도록 작업하며 코드정리를 하였습니다.

![image](https://github.com/seolhee313/site2023-vue01/assets/125417882/8a961c73-70f1-408f-b5bd-bd54bc47b287)

- Live Demo : https://sitecheon-vue01.netlify.app/
- 작업 기간 : 2일

## 사용 스택

- vue 3.2.13
- sass 1.32.7
- swiper 8.4.7

## 특징

- [YOUTUBE](https://console.cloud.google.com/apis/) API
- [UNSPLASH](https://www.postman.com/downloads/) API
- [MOVIE](https://www.themoviedb.org/?language=ko) API

## 학습

- 가상 DOM과 Reactivity(반응성) 시스템을 통해 빠른 렌더링과 DOM 업데이트를 수행합니다. 필요한 부분만 업데이트하므로 성능이 향상되며, 작은 규모의 프로젝트부터 큰 규모의 애플리케이션까지 효율적으로 작동합니다.
- 템플릿 문법을 활용하여 컴포넌트 기반 개발을 쉽게 할 수 있습니다.
- 컴포넌트 기반 아키텍처를 사용하여 UI를 작은 단위로 쪼개고 재사용 가능한 컴포넌트를 만들 수 있습니다. 이로 인해 코드의 재사용성이 높아지고 유지 보수가 용이해집니다.
- 단방향 데이터 흐름을 지원합니다. 데이터는 상위 컴포넌트에서 하위 컴포넌트로만 전달되며, 하위 컴포넌트는 상위 컴포넌트의 데이터를 수정할 수 없습니다. 이로 인해 데이터의 흐름이 예측 가능하고 유지 보수가 용이해집니다.

## 개발 환경 프로젝트 실행 방법

1. **레포지토리 클론 :** `git clone https://sitecheon-vue01.netlify.app/`
2. **Node.js와 npm 설치 :** `Node.js 공식 웹사이트에서 Node.js를 다운로드하고 설치. Node.js를 설치하면 npm도 함께 설치됩니다.`([ Node.js ](https://nodejs.org))
3. **Vue 프로젝트 생성 :** `npm install -g @vue/cli`
4. **scss 설치 :** `npm install node-sass`
5. **router 설치 :** `npm install vue-router`
6. **swiper 설치 :** `npm install swiper`
7. **프로젝트 시작 :** `npm run serve`

## API 요청

1. **YOUTUBE :** ([ YouTube Data API v3 ](https://console.cloud.google.com/apis/)에서 API Key 발급 필요)
1. **UNSPLASH :** ([ postman ](https://www.postman.com/downloads/)에서 API Key 발급 필요)
1. **MOVIE :** ([ themoviedb ](https://www.themoviedb.org/?language=ko)에서 API Key 발급 필요)

## Screenshots

![image](https://github.com/seolhee313/site2023-react01/assets/125417882/925a3aeb-51f4-4131-8a37-8296b62817b7)
![image](https://github.com/seolhee313/site2023-react01/assets/125417882/cfd14920-6c5d-45f6-9252-4c5533a2d76d)
![image](https://github.com/seolhee313/site2023-react01/assets/125417882/1cc35930-2eda-462e-a3cc-ca0b17f06b64)
