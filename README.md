# 개발 블로그
나만의 블로그 운영하기

## 개발 환경

- Hugo Extended **0.165.0** (Netlify와 동일한 버전)
- Blowfish **v3.6.0** (공식 저장소의 Git 서브모듈)

Blowfish v3.6.0의 지원 범위가 Hugo 0.162.0–0.165.0이므로 Hugo 버전을 0.165.0으로 고정합니다.

```sh
git submodule update --init --recursive
hugo version
hugo server
```

프로덕션 빌드는 `hugo`로 실행합니다. 테마는 프로젝트에 기록된 커밋을 사용하므로
`git submodule update --remote` 대신 위 초기화 명령을 사용하세요.
