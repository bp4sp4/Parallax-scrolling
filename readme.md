# Parallax Scrolling(w.fastcompus)

<h2>24/03/12(금) 시작 ~ 24/03/12 끝</h2>

데모 사이트 : <a href="https://bp4sp4.github.io/Parallax-scrolling/">Parallax Scrolling</a>

<h3>css : scroll-behavior</h3>

- scroll-behavior
  - 브라우저가 유저의 페이지 스크롤을 어떻게 동작시킬지 명시
  - value 타입
    - smooth : 부드러운 스크롤, 대부분 브라우저에서 default
    - auto( or instant) : 부드러운 효과 없이 즉시 스크롤

```
 element {
    scroll-behavior : value
 }

 value : `smooth` | `auto(instant)`
```

<h3>스크롤 smmoth</h3>

- 기본 html a태그 미작동시킴
- behavior : "smmoth" 값넣음

```
    const link = document.querySelector('a[href="#document-title"]')

    link.addEventListener("click", () => {
        event.preventDefault()

        document.querySelector("#document-title").scrollIntoView({
            behavior: "smooth"
        })
    })
```

<h3>Parallax Scrolling 기법</h3>

- svg 파일내 id 들을 자바스크립트로 구현

```
const sun = document.getElementById("sun")
```

- 반응형 대비로 clinet width로 전역변수 생성

```
let clientWidth = document.documentElement.clientWidth
```

- 너비가 800 이상이면 Parallax Scrolling 작동
- 너비가 800 이하이면 Parallax Scrolling 미작동

```
window.addEventListener("scroll", () => {
        if (clientWidth > 800) {
            ...
            ...
        }
}
 window.addEventListener("resize", () => {
        clientWidth = document.documentElement.clientWidth

        if (clientWidth < 800) {
            ...
            ...
        }
 }


```
