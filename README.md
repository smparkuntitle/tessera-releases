# Tessera — 설치본 배포

Tessera(Oracle · PostgreSQL · MySQL/MariaDB · SQL Server 범용 DB 클라이언트)의 **설치본과 업데이트 파일만** 올리는 저장소입니다. 소스 코드는 여기에 없습니다.

## 설치
- **macOS (Apple Silicon)**: 릴리스의 `Tessera-<버전>-arm64.dmg`를 열고 Tessera를 응용 프로그램 폴더로 끌어 놓습니다.
- **Windows (일반판)**: `Tessera_<버전>_x64-setup.exe` — WebView2가 없으면 설치 중에 내려받습니다.
- **Windows (폐쇄망판)**: `Tessera_<버전>_x64-offline-setup.exe` — WebView2 고정 버전이 들어 있어 인터넷·관리자 권한 없이 설치됩니다.

## 업데이트
처음 한 번 설치한 뒤에는 앱이 이 저장소의 `latest.json`을 확인해 새 버전을 알려 주고, "지금 설치"를 누르면 경고 창 없이 교체됩니다(업데이트 파일은 자체 서명 키로 검증). 폐쇄망에서는 확인이 조용히 실패하므로 새 설치본을 직접 받아 덮어 설치하세요.

## 사전 공개
이름에 `alpha`·`beta`가 붙은 릴리스는 사전 공개(시험)판입니다.
