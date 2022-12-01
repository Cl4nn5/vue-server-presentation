# compare-vue-series

Version | vue2  | vue3  | vue3 setup
--- | ----  |----   | ---
Script | Option API | Composition API | Setup Script
장점 1 | 확정된 버전 | 기능에 따른 코드 묶음 | 적은 코드량
장점 2 | 2.7 이상 버전에서<br/>Composition API 사용 가능 | 타입스크립트 사용가능 | 반복적인 코드 사용의 감소
단점 1 | 재사용에 제약이 많음 | 코드량이 많음 | 짧은 역사 => 검색 & 지원 ☹

나의 바람 : vue3 setup  
회사에 필요한 기능 : vue2 + composition API

### composition API의 사용시 코드 배치 형태
  <img src="https://velog.velcdn.com/images/teo/post/ae7d303c-03de-43f4-bb65-aa028e097313/image.png">

## 희망 추진방향
1. react보다 깔끔하고 짧은 코드량 : template
2. node.js를 통한 vue 사용에서 Tree Shaking 강화 
<br/>-> 불필요한 코드 & script 주석 제거
3. Composition API를 통한 코드의 그룹화
4. typeScript와 호환이 잘 되는 vue3.x 사용
5. vue3.x의 Fragment : 템플릿 최상단에서 단 하나의 "div"태그만 허용하였음
<br/>-> 다중 루트 노드의 지원
6. vue3 내에서 에러 발생이 LifeCycle Hook인 onErrorCaptured를 사용하여 에러 캐치 가능 및 대체 템플릿 구현 가능
7. data내에 선언된 객체에 반응성을 부여하기 위해 Vue.$set으로 반응성을 강제주입해야 하였음
<br/>-> 반응성 API(Reactivity API)의 지원(e.g. ref, reactive)
## 결론
- [ ] 1.  node.js 사용
  1. 프론트 서버 분리
  2. 스크립트단 에러 캐치
  3. 에러 발생 컴포넌트 접근의 용이성(with vue Devtools)
  4. 가벼운 개발 툴(vsCode)과 확장도구
  5. 코딩 컨벤션 강제(저장 시점에 자동 적용)
- [ ] 2. typeScript 사용
  1. 컴파일 전 에러 캐치
  2. interface를 통하여 BE서버에서 발송하는 모델의 모습을 예상할 수 있음
- [ ] 3. vue3 버전업그레이드

## 점진적 추구방향
프론트 프레임워크 & 아키텍쳐의 도입
View와 BL(비즈니스 로직 이하 BL)의 분리

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).
