---
title: "클라우드 플레어로 블로그 배포하기"
description: ""
summary: ""
date: 2024-03-10
categories: ["Devops", "Cloudflare"]
tags: ["devops", "cloudflare", "github", "hugo"]
#externalUrl: ""
#showSummary: true
draft: false
---

{{< figure
src="content/images/featured.png"
alt="Cloudflare Pages"
caption="Cloudflare Pages"
>}}

## Netlify 사용하고 있던 도중에...
최근에 Netlify에서 DDoS를 통해 약 1억원 가량이 [사용자에게 청구되는 사건](https://news.hada.io/topic?id=13554)이 있었습니다.  
당연하지만 해당 사건으로 인해 개발 커뮤니티가 뜨거웠고 저도 그 소식을 접하게 되었죠  

이런 조그마한 개발 블로그에 설마 저런 상황이 벌어질리는 없겠지만..  
혹시라는게 있으니까 사용하던 Netlify에서 다른 정적 사이트 클라우드를 사용하기로 했습니다

## 다른 플랫폼은?
처음에는 Vercel을 생각했는데 거기도 Netlify와 다른게 없는 상황이여서 선택지에서 배제했습니다.  
여러가지로 검색을 해보던 와중에 클라우드플레어에서 [Cloudflare Pages](https://developers.cloudflare.com/pages)라는 서비스를 제공해준다는 것을 알게 되었습니다.  
클라우드 플레어는 DDoS 관련 방어등으로 유명한 클라우드 회사로 무료 DDoS 방어를 제공하고 있습니다.  
제가 플랫폼을 옮기려는 목적과 부합하기 때문에 선택했습니다.  

### Cloudflare Pages 제공 혜택
- 한번에 1개의 빌드만 가능
- 달마다 500개의 빌드 가능
- 최대 100개의 커스텀 도메인 지원
- 제한없는 사이트
- 제한없는 요청
- 무제한 대역폭

## Cloudflare Pages 사용기
설정을 모두 끝마친 모습입니다.  
이미 Hugo 베이스의 레포지토리를 가지고 있어서 금방 설정할 수 있었습니다.

{{< figure
src="content/images/cf_pa_ma.png"
alt="Cloudflare Pages Panel"
caption="Cloudflare Pages Panel"
>}}

Pages는 이상하게 메인 도메인을 커스텀 도메인으로 설정할 수 없었습니다.  
도메인 관리를 클라우드플레어를 사용하게 하려는 의도인지는 잘 모르겠지만 참 아쉬운 부분입니다.

### 생각보다 좋은 성능
Netlify랑 구체적인 비교를 하지 않았지만 빌드 퍼포먼스 면에서 좀 더 빠른 느낌이 들었습니다.  
물론 보안적 측면을 바라보고 플랫폼을 이동했지만 의외의 수확이였습니다.

### 무료 티어의 제약
위의 제공혜택을 보면 알겠지만 개인 사용자의 측면에서는 부족한 점이 하나도 없었습니다.  
기업 측면에서는 어차피 규모와 가격적 측면을 고려해서 선택해서 사용할테니까요

## 포스팅을 마치며
계속 사용해보면서 여러가지 기능을 활용해볼 예정입니다.  
현재 분기 설정을 통해 배포전 미리보기 기능을 테스트해보고 있습니다.  

추후에 Pages 포스팅은 다양한 활용방법으로 찾아오겠습니다.  
제 글을 읽어주셔서 감사합니다 :)
