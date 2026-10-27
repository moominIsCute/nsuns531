# nSuns 531 홈짐 앱 설치 방법

폰에 설치해서 쓰는 웹앱(PWA)입니다. 한 번 올려 두면 오프라인에서도 작동합니다.

## 1. 깃허브 페이지에 올리기 (무료, 약 5분)

1. github.com 에 로그인하고 오른쪽 위 **+ → New repository** 를 누릅니다.
   - 이름: `nsuns531` (아무 이름이나 가능)
   - **Public** 선택 → **Create repository**
2. 만들어진 저장소 화면에서 **uploading an existing file** 링크를 누릅니다.
3. 이 폴더의 파일 8개를 모두 끌어다 놓고 **Commit changes** 를 누릅니다.
   - index.html, sw.js, manifest.webmanifest, README.md
   - icon-192.png, icon-512.png, icon-maskable-512.png, apple-touch-icon.png
4. 저장소의 **Settings → Pages** 로 갑니다.
   - Source: **Deploy from a branch**
   - Branch: **main**, 폴더 **/ (root)** → **Save**
5. 1~2분 뒤 같은 화면 위쪽에 주소가 나옵니다.
   - 예: `https://아이디.github.io/nsuns531/`

## 2. 폰에 설치하기

- **아이폰 (Safari)**: 주소를 열고 → 공유 버튼 → **홈 화면에 추가**
- **안드로이드 (Chrome)**: 주소를 열고 → 메뉴(⋮) → **앱 설치** 또는 **홈 화면에 추가**

홈 화면의 빨간 531 아이콘으로 열면 전체 화면 앱으로 실행됩니다.

## 기록 저장에 관해

- 기록은 **그 폰 안에만** 저장됩니다. 서버로 보내지 않습니다.
- **기록·그래프** 탭 맨 아래 **백업 파일 내려받기** 로 가끔 백업하세요.
- 폰을 바꾸면 새 폰에 앱을 설치한 뒤 **백업 파일 불러오기** 로 옮깁니다.
- 아이폰은 앱을 오래(몇 주) 열지 않으면 저장 데이터가 지워질 수 있습니다. 홈 화면에 추가해서 쓰면 이 위험이 줄어듭니다.
- Claude 안의 트래커 페이지에 쌓인 기록은 이 앱으로 자동으로 넘어오지 않습니다.

## 앱을 고친 뒤 다시 올릴 때

1. 바뀐 파일을 같은 저장소에 다시 업로드합니다.
2. `sw.js` 맨 위 `VERSION` 값을 바꿉니다. 예: `nsuns-v1` → `nsuns-v2`
   - 이걸 바꿔야 폰에 저장된 예전 화면 대신 새 버전이 뜹니다.

---

# 안드로이드 전용 앱(APK)으로 쓰기

브라우저 없이 기록을 앱 안에 저장하는 진짜 안드로이드 앱입니다. APK는 깃허브가 대신 만들어 줍니다.

## 처음 한 번만
1. 저장소에서 **Add file → Upload files** → `android` 폴더(통째로), `index.html`, `sw.js` 를 끌어다 놓고 **Commit changes**.
2. **Add file → Create new file** → 파일 이름 칸에 `.github/workflows/android-build.yml` 입력
   → 이 폴더의 `android-build.yml` 내용을 메모장으로 열어 전부 복사해 붙여넣기 → **Commit changes**.
3. 저장소 위쪽 **Actions** 탭에서 초록 체크가 뜰 때까지 3~5분 기다리기.
4. 폰에서 아래 주소를 열어 APK를 받아 설치:
   https://github.com/moominIsCute/nsuns531/releases/latest/download/nsuns531.apk

## 기록 옮기기
새 앱 → 기록·그래프 → 백업 파일 불러오기 → 다운로드 폴더의 nsuns-backup-날짜.json 선택

## 앱을 고친 뒤
`index.html` 만 다시 올리면 깃허브가 새 APK를 자동으로 만듭니다.
같은 주소에서 받아 덮어 설치하면 기록은 그대로 유지됩니다.
(`android/app/nsuns531.keystore` 파일을 지우거나 바꾸면 덮어 설치가 안 되니 그대로 두세요.)
