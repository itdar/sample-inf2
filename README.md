# sample-inf2 — 룰렛 당첨자 뽑기 웹앱

인프런 강의 **"무료 클라우드 인프라 구축하기 2"** Chapter 6 실습용 샘플 레포입니다.

## 구성

```
sample-inf2/
├── index.html                        # 룰렛 웹앱 (단일 HTML)
├── Dockerfile                        # nginx:alpine 베이스에 HTML 1장 복사
└── .github/
    └── workflows/
        └── docker-publish.yml        # main push 시 linux/arm64 이미지 빌드 → Docker Hub 업로드
```

## 사용법 (수강생)

1. 이 레포를 **Fork**
2. Docker Hub 에서 Access Token 생성 (`Account Settings` → `Personal access tokens`, **Read & Write**)
3. Fork 한 레포의 `Settings` → `Secrets and variables` → `Actions` 에 repository secret 등록:
   - `DOCKERHUB_USERNAME`: Docker Hub 사용자명
   - `DOCKERHUB_TOKEN`: 생성한 Access Token
4. `Actions` 탭에서 워크플로우 활성화 후 `Run workflow` 실행 (또는 main 에 push)
5. Docker Hub 에서 `본인계정/sample-inf2:latest` (OS/ARCH: `linux/arm64`) 확인

## 빌드 없이 바로 쓸 이미지 (강의의 방법 A)

```
itdar/sample-inf2:latest
```

## 로컬 미리보기

`index.html` 을 브라우저로 열면 룰렛 동작을 바로 확인할 수 있습니다.
