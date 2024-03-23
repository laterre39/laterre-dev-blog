---
title: "Hugo에서 blowfish 테마 커스텀 수정하기"
description: ""
summary: ""
date: 2024-03-23
categories: ["Hugo", "Blog"]
tags: ["blowfish", "blog", "hugo", "custom"]
#externalUrl: ""
#showSummary: true
draft: false
---

{{< figure
src="featured.png"
alt="Blowfish Theme"
caption="Blowfish Theme"
>}}

## 블로그 커스텀하기
블로그 개설한지 벌써 한 3개월이 지난듯 싶습니다.  
포스팅 의미있는거 해보려고는 하는데 뭔가 딱히 아직 포스팅을 할만한 유의미한 정보가 없어서 못하고 있습니다...

이번에 블로그를 커스텀하면서 적용한 코드를 정리하고자 합니다.

## 블로그 적용 기술
블로그에 적용한 기술들을 한번 정리해봤습니다.

### Cloudflare Pages 적용

[포스팅 바로가기](https://blog.laterre.dev/posts/%ED%81%B4%EB%9D%BC%EC%9A%B0%EB%93%9C-%ED%94%8C%EB%A0%88%EC%96%B4%EB%A1%9C-%EB%B8%94%EB%A1%9C%EA%B7%B8-%EB%B0%B0%ED%8F%AC%ED%95%98%EA%B8%B0/)  

기존에 블로그에 포스팅한 글로 대체하겠습니다.  
Netlify를 사용하다가 Cloudflare로 교체해서 서버리스 플랫폼을 사용하고 있습니다.

자세한 내용은 포스팅을 참고 해 주세요.

### 나눔고딕 폰트 적용
Blowfish 테마에서 기본적으로 제공하는 폰트는 다음과 같습니다.
```css
  font-family: ui-sans-serif, system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, "Noto Sans", sans-serif, "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol", "Noto Color Emoji";
```
기본적으로 한글 폰트를 기기에서 지원하는 폰트로 지원하고 있습니다.   
하지만 저는 한글 포스팅의 가독성을 높이기 위해 네이버에서 개발한 [나눔고딕](https://hangeul.naver.com/font) 폰트를 사용하기로 했습니다.

```css
@font-face { /* 나눔고딕 한글에만 적용 */
    font-family: "Nanum Gothic";
    src: url('/fonts/NanumGothic-Regular.ttf');
    unicode-range: U+1100-11FF, U+3130-318F, U+A960-A97F, U+AC00-D7A3, U+D7B0-D7FF;
}

html {
    font-family: "Nanum Gothic", ui-sans-serif, system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, "Noto Sans", sans-serif, "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol", "Noto Color Emoji";
}
```
**custom.css**  
테마에서 제공하는 custom.css를 활용해서 블로그 전역에 폰트 사용을 위한 css를 등록합니다.  
유니코드 범위 지정을 통해 한글만 나눔고딕 폰트를 적용하도록 했습니다.

Unicode Range: [한글, 영어, 숫자 서로 다른 폰트 적용하기](https://velog.io/@kimheewon/%ED%95%9C%EA%B8%80-%EC%98%81%EC%96%B4-%EC%88%AB%EC%9E%90-%EC%84%9C%EB%A1%9C-%EB%8B%A4%EB%A5%B8-%ED%8F%B0%ED%8A%B8-%EC%A0%81%EC%9A%A9%ED%95%98%EA%B8%B0unicode-range-8fi3p345)

해당 방식을 활용하면 영문 또는 숫자등의 문자에 각기 다른 폰트를 활용할 수 있습니다.  
영문 폰트는 유명한 영문 폰트를 사용하고 있기 때문에 별도로 적용하지 않았습니다.