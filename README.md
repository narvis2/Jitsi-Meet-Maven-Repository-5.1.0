## 🍎 Jitsi-Meet 기반 화상회의 SDK 화 작업 테스트

- ✔️ Jitsi-Meet Repository 👉 [Jitsi-Meet](https://github.com/jitsi/jitsi-meet)
- 이 프로젝트는 `react-native-jitsi-meet` 프로젝트와 함께 사용하기 위해 `Jitsi-Meet` `SDK` `Version` `5.1.0` 을 채택하여 사용하였습니다.

### 🍀 Jitsi-Meet Android SDK 화 작업 순서

- 1️⃣ [jitsi-Meet git](https://github.com/jitsi/jitsi-meet) 👉 Repository Clone
- 2️⃣ `npm --legacy-peer-deps install`
- 3️⃣ `postinstall` npm script 실행
  > - npm patch-package --error-on-fail && jetify
- 4️⃣ android `local.properties` 설정하기 (`ANDROID_SDK_ROOT` 설정)
- 5️⃣ `cd android`
- 6️⃣ `cd scripts`
- 7️⃣ `sh release-sdk.sh`
- ⚠️ 오류 ⚠️
  - 1️⃣ /jitsi-maven-repository/releases: No such file or directory 👉 clone 받은 폴더 내부에 필요한 폴더 생성
    > ✅ **_참고_** ✅
    >
    > - release-sdk.sh 스크립트 성공시 sdk 가 /jitsi-maven-repository/releases 에 생성됨
    > - 1️⃣ **_clone 받은 폴더 내부_** 에 `jitsi-maven-repository` 폴더 생성
    > - 2️⃣ `jitsi-maven-repository` 내부에 `release` 폴더 생성
    > - 3️⃣ `clone` 받은 폴더 내부 > `jitsi-maven-repository` > `release` > `sdk` 생성
  - 2️⃣ mvn: command not found 👉 maven 다운로드 및 환경 변수 설정
    > ✅ **_참고_** ✅ [참고 사이트](https://www.digitalocean.com/community/tutorials/install-maven-mac-os)
    >
    > > 나는 development 에 압축 파일 풀고 환경변수 설정함
- 🍬 SDK Version 변경 🍬
  - android > `gradle.properties`
    > - `appVersion`
    >   > - 99.0.0 👉 1.0.0
    > - `sdkVersion`
    >   > - 99.0.0 👉 1.0.0

## ❗️Jitsi-Meet SDK 6 버전 이상 오류❗️

- `BaseReactView`, `JitsiMeetViewListener` 가 `SDK 6` 버전 이상부터 없어서 `not found exception` 발생
- **_✅ 참고 ✅_**
  > - [Jitsi-Meet SDK Version 관리 Github](https://github.com/jitsi/jitsi-meet-release-notes/blob/master/CHANGELOG-MOBILE-SDKS.md)
