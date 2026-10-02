# 클린지상주의 콘텐츠 리포트

이 업체의 작업 기준 폴더는 `content_report/clean-jisang`입니다.

## 파일 구성

- `index.html`: 현재 사용하는 보고서. 스타일과 동작 코드가 함께 들어 있습니다.
- `size-logo.png`: 화면에서 사용하는 로고. 흰 배경과 테두리 프레임 안에 표시합니다.
- `assets/next-phoenix-logo.png`: 제작 및 운영사 넥스트피닉스 로고. 왼쪽 하단에 투명 배경 그대로 표시합니다. 로고 옆 `제작 · 제공 ↗`의 화살표에만 홈페이지 링크를 연결합니다. 푸터에는 링크 없는 `BY NEXTPHOENIX` 텍스트만 표시합니다.
- 운영 채널 바로가기는 데스크톱에서 발행 요약의 오른쪽에, 모바일(740px 이하)에서 콘텐츠 라이브러리 바로 아래에 표시합니다.
- `logo.jpg`: 제공받은 원본 이미지. 보관용입니다.
- `tests/verify-report.cjs`: 로컬 보관용 데이터 처리와 오류 처리 검증. GitHub 업로드에서는 제외합니다.
- `tests/fixtures/`: 로컬 보관용 2026-10-02 시트 응답 테스트 자료입니다. 보고서가 이 파일들을 읽거나 예시 데이터로 표시하지 않습니다.
- `archive/`: 로컬 보관용 이전 디자인 및 과거 연결 점검 자료. 현재 보고서에서는 사용하지 않습니다.

## 로컬 확인

`content_report` 폴더에서 서버를 실행합니다.

```powershell
python -m http.server 8765 --bind 127.0.0.1
```

브라우저 주소: `http://127.0.0.1:8765/clean-jisang/`

기존 로컬 작업 폴더의 검증 실행 (`tests/`는 배포 저장소에 포함하지 않습니다):

```powershell
node clean-jisang/tests/verify-report.cjs
```

## 시트 연결 및 배포

- 구글시트 ID: `1qdBMfG2TC4ZZzL9GMB337Wn5WSbPE4GBoJfPVJKhqvE`
- 클린지상주의 탭: `1802451476`
- 첫 행: `업로드날짜`, `플랫폼`, `주제`, `링크`
- E2/E3/E4: 블로그/인스타그램/페이스북 채널 주소
- 화면을 열거나 새로고침 버튼을 누르면 공개된 시트를 읽습니다.
- 사이트 배포에는 `index.html`, `size-logo.png`, `assets/next-phoenix-logo.png`가 필요합니다. 같은 상대 경로를 유지합니다.
- `tests`, `archive`, 원본 `logo.jpg`는 사이트 배포에 필요하지 않습니다.
- GitHub 저장소: https://github.com/woorissu/clean-jisang (브랜치: `main`)
- GitHub 코드 업로드와 실제 사이트 배포는 별도입니다.
