# Vite + React 템플릿

Vite 커스텀 템플릿 구성

## 스캐폴딩 명령

degit 명령을 사용해 프로젝트를 스캐폴딩합니다.

```sh
degit songyi225/vite-react <프로젝트_이름>
```

---

## 커스텀 템플릿 디렉토리 구조

![스크린샷 2024-07-31 오전 1 02 30](https://github.com/user-attachments/assets/2a43549b-055c-4a98-881f-73d03aac9c13)

---

## 설치 패키지

pnpm 사용

#### vite 패키지 설치

```sh
pnpm add -D vite
```

#### react, react-dom

```sh
pnpm add react react-dom
```

#### type 선언 패키지

```sh
pnpm add @types/react @types/react-dom @types/node -D
```

#### vite 플러그인

```sh
pnpm add @vitejs/plugin-react -D
```

#### ESLint

9버전의 eslint 설치

```sh
pnpm create @eslint/config@latest
```

#### ESLint hooks, refresh

```sh
pnpm add eslint-plugin-react-hooks eslint-plugin-react-refresh -D
```

---

## 느낀점

디렉토리를 구성하고 설치 명령어 입력하면서 차근차근 진행했더니 궁금한 사항을 그때 그때 찾아보면서 공부했던 것 같습니다. 나중에 환경구성할 때 지금의 기억을 떠올리면서 조금이라도 수월하게 진행할 수 있을 것 같습니다.

#### 커스텀 템플릿 구동화면 캡쳐

![스크린샷 2024-07-31 오전 1 39 26](https://github.com/user-attachments/assets/0911ca6a-1642-4569-81d1-1f46a91eb120)

---

## 깨달은 점..

> React

리액트를 처음 접하다보니 react와 react-dom이 분리되어있는걸 이해하기 어려워서 그냥 냅다 같이 설치하자~를 공식처럼 외우고 있었는데 이번에 환경구성하면서 찾아보니 react-dom을 통해 웹 브라우저에 렌더링할 수 있다는 것을 알게되었습니다!

react-dom의 client api에서 creatRoot를 사용하여 리액트 루트를 생성하고, 화면에 표시될 수 있도록 렌더링해주는 render() 함수를 사용한다.. 라는 흐름을 이해하게 되었습니다.

> StrictMode

@vitejs/plugin-react 플러그인을 사용하면 `import React from "react";` 코드를 생략해도 JSX 구문을 변환할 수 있습니다.

StrictMode를 사용하기 위한 코드인 `import { StrictMode } from "react";` 에서 사용하는 react 패키지는 위에서 생략한 react 패키지와 동일한 패키지에서 StrictMode를 가져오는 것으로 보입니다.

이는 JSX 변환 기능과는 다른 별도의 기능이라서 작성해주는걸로 이해했습니다. (맞는거겠죠?)

main.jsx의 render 내부에 StrictMode를 작성해준 것처럼 컴포넌트가 렌더링될 때 같이 작성해주면 미리 버그를 발견할 수 있다는 장점이 있는 것을 깨달았습니다.

StrictMode는 개발 환경에서만 활성화되기 때문에 프로덕션 성능에는 문제가 없을 것으로 보입니다. (맞겠죠..?ㅎ\_ㅎ)
