# 0.2.11 제출 자료 확인

확인일: 2026-11-13. 기존 작업본을 수정하지 않고 `origin/main` (`69b558b`)에서 분리한 작업본으로 확인했다. Android 앱 코드는 변경하지 않았다.

## 최신 release

- 저장소 APK 목록과 Android main의 버전은 0.2.11 / versionCode 13이다. 별도 GitHub Release 게시물은 없다. APK는 `apk/`에 있다.
- `apksigner verify --print-certs`로 0.2.11 release 서명 유효성을 확인했다.
- 인증서 SHA-256: `f888bfaf40b5b0eb766d6eba8ad99dbd932c37eaad1fda992e981e756813d111`. 0.2.10 release와 동일하다.
- APK SHA-256: `71a5390515550f526d86026cd611e39fffbf9e928421ca212cb82fc359d9f464`. 저장된 `SHA256SUMS.txt`와 일치한다.
- APK 소스 `463798f`와 현재 Android main의 비교에서 추가 변경 파일은 `docs/verification/release-0.2.11.md`뿐이다. 앱 코드 차이는 없다.
- 이번 확인에서 release 전체 시연이나 0.2.10 → 0.2.11 업데이트 시험을 다시 수행하지 않았다. 기존 업데이트 시험 기록은 Android 저장소의 0.2.11 검증 기록을 따른다.

## README 수정

최신 버전을 0.2.10이라고 설명하던 첫 문단과 최신 소스 링크, 권장 debug APK, 서명 간 설치 안내를 수정했다. 0.2.10의 과거 검증 결과는 그대로 과거 기록으로 유지한다. release는 앱 내부 시연 데이터이며 서버 설정과 데모 패널이 없음을 명시했다.

## 시연 영상

별도 Pleos 에뮬레이터 `emulator-5580`에서 저장소의 0.2.11 debug APK를 설치해 실제 화면을 녹화했다. 사용자 휴대폰과 다른 세션 기기는 조작하지 않았다. 앱에서 방문지·인원을 정하고 방문 시작을 눌러 순정 내비로 전환한다. 접수는 사용자 화면 승인 후 실행한다.

영상의 ETA 변화·주행 제한·도착·하차·호출은 debug 시연 입력, 접수는 FakeBackend다. 실제 매장 접수·실차·사람 목소리 STT 검증 영상이 아니다. 한국어 설명 음성은 영상 편집용 합성 내레이션이며 앱 음성 인식 입력에 사용하지 않았다. 일반 adb 화면 녹화이며 공식 FormFactorConsole 검증이 아니다.

녹화한 debug 설치에서 `dumpsys package`의 `SYSTEM_ALERT_WINDOW: granted=true`를 확인했고, 순정 내비 위 보조 질문 카드가 표시됐다. 질문 카드의 일반 설치 표시 가능 여부를 새로 확정한 것은 아니다. 영상 속 승인 조작은 정차 상태에서 앱 화면의 걸기 버튼으로 했다.
