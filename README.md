# AllTalk Developers Docs

[developer.alltalk.co.kr](https://developer.alltalk.co.kr) 문서 저장소.
[Mintlify](https://mintlify.com) 기반으로 빌드 · 배포됩니다.

## 로컬 개발

Mintlify CLI 설치 (최초 1회):

```bash
npm i -g mintlify
```

로컬 서버 실행 (기본 포트 3000):

```bash
mintlify dev
```

## 구조

```
mint.json              # Mintlify 설정 (네비게이션, 테마)
introduction.mdx       # 랜딩 페이지
quickstart.mdx         # 빠른 시작
authentication.mdx     # 인증
guides/                # 개념 가이드
api-reference/         # 엔드포인트별 레퍼런스
  introduction.mdx
  messaging/           # SMS, 알림톡, 친구톡, 브랜드메시지
  address/             # 주소록 · 그룹
  send/                # 발송 내역
logo/                  # 로고 이미지 (dark.svg, light.svg)
```

## 배포

GitHub 레포를 Mintlify 대시보드에 연결하면 `main` 브랜치 push 시
자동으로 `developer.alltalk.co.kr`에 반영됩니다.

### 최초 셋업

1. GitHub 레포 생성 후 이 디렉토리를 push
2. [mintlify.com/dashboard](https://mintlify.com/dashboard) 로그인
3. **Add new deployment → GitHub** 선택, 이 레포 연결
4. 도메인 설정: Mintlify Dashboard → Settings → Custom Domain
   - `developer.alltalk.co.kr` 입력
   - DNS에 Mintlify가 안내하는 CNAME 레코드 추가
5. HTTPS 자동 발급 대기 (수 분 ~ 수 시간)

## 문서 작성 가이드

- 파일 확장자는 `.mdx` (React 컴포넌트 사용 가능)
- 각 파일 최상단에 frontmatter 필수:
  ```
  ---
  title: "페이지 제목"
  description: "검색 · OG 메타 설명"
  ---
  ```
- API 레퍼런스는 `api: "POST https://..."` 속성 추가 시
  오른쪽에 자동으로 코드 블록 영역이 렌더링됨
- 네비게이션에 새 페이지 추가 시 `mint.json`의 `navigation` 배열 업데이트

## 컴포넌트 레퍼런스

자주 쓰는 Mintlify 컴포넌트:

- `<Note>`, `<Warning>`, `<Tip>` — 강조 박스
- `<CodeGroup>` — 언어별 탭 코드 블록
- `<Steps>` — 단계별 가이드
- `<ParamField>`, `<ResponseField>` — API 파라미터/응답 문서화
- `<RequestExample>`, `<ResponseExample>` — 요청/응답 예제

전체 목록: https://mintlify.com/docs/content/components
