<!-- 이 파일은 소스 저장소 release-notes/README.template.md에서 infra/release-publish.sh가 만든다. 여기서 직접 고치지 말 것 -->
<p align="center">
  <img src="assets/logo.svg" width="96" height="96" alt="Tessera 로고">
</p>

<h1 align="center">Tessera</h1>

<p align="center">
  <b>모든 데이터를, 있는 그대로.</b><br>
  Oracle · PostgreSQL · MySQL/MariaDB · SQL Server를 한 앱에서 다루는 DB 클라이언트
</p>

<p align="center">
  최신 버전 <b>0.8.20</b> · 2026-11-01 출시 · <a href="CHANGELOG.md">업데이트 노트</a>
</p>

<table align="center">
  <tr>
    <td align="center" valign="top">
      <a href="https://github.com/smparkuntitle/tessera-releases/releases/latest/download/Tessera-macOS.dmg">
        <picture>
          <source media="(prefers-color-scheme: dark)" srcset="assets/download-macos-dark.svg">
          <img src="assets/download-macos.svg" width="320" height="68" alt="macOS용 내려받기 (Apple Silicon)">
        </picture>
      </a>
      <br><sub>Intel Mac은 아직 지원하지 않습니다</sub>
    </td>
    <td align="center" valign="top">
      <a href="https://github.com/smparkuntitle/tessera-releases/releases/latest/download/Tessera-Windows-setup.exe">
        <picture>
          <source media="(prefers-color-scheme: dark)" srcset="assets/download-windows-dark.svg">
          <img src="assets/download-windows.svg" width="320" height="68" alt="Windows용 내려받기">
        </picture>
      </a>
      <br><sub><a href="https://github.com/smparkuntitle/tessera-releases/releases/latest/download/Tessera-Windows-offline-setup.exe">폐쇄망(인터넷 없는 PC)용 Windows 설치본</a></sub>
    </td>
  </tr>
</table>

## 처음 설치할 때

Tessera는 아직 Apple·Microsoft 유료 인증서로 서명하지 않아, 처음 한 번은 운영체제가 확인을 묻습니다.

**macOS**
1. 내려받은 `Tessera-macOS.dmg`를 열고 Tessera를 Applications 폴더로 끌어 놓습니다.
2. Tessera를 처음 열면 "확인할 수 없는 개발자" 안내가 뜹니다. **완료**를 누릅니다.
3. **시스템 설정 › 개인정보 보호 및 보안**의 맨 아래에서 Tessera 옆 **그래도 열기**를 누르고, 다시 묻는 창에서 **열기**를 누릅니다.

**Windows**
1. 내려받은 `Tessera-Windows-setup.exe`를 실행합니다.
2. "Windows의 PC 보호" 창이 뜨면 **추가 정보**를 누른 뒤 **실행**을 누릅니다.
3. 관리자 권한 없이 설치됩니다. 인터넷이 없는 PC에는 폐쇄망용 설치본을 쓰세요(필요한 구성 요소가 함께 들어 있습니다).

## 업데이트

새 판이 나오면 앱이 알아서 알려 주고, 누르면 받아서 설치한 뒤 다시 시작합니다. 폐쇄망에서는 새 설치본을 받아 덮어 설치하면 됩니다.

## 이번 판에서 바뀐 점 (0.8.20)

### 바뀐 점
- **숫자 저장 형식 점검(Oracle)** — 메뉴 막대 '데이터 › 숫자 저장 형식 점검(Oracle)…'(또는 명령 팔레트에서 '숫자'). 이전 판(11g 서버는 0.8.16~0.8.18, 12c 이상 서버는 0.8.0-alpha.14·0.8.15~0.8.18)에서 Instant Client 없이 이미 있던 정수 칸을 100·1000·-1200처럼 0이 아닌 100의 배수로 고쳐 저장했다면, 그 값이 Oracle 표준이 아닌 형태로 들어가 검색에 걸리지 않을 수 있습니다. 표를 고르면 먼저 읽기만 해서 몇 칸인지 세고, 원하면 찾은 칸만 한 번에 고칩니다(값은 그대로 · 저장 형식만 표준으로 · 고치기 전 원래 바이트를 파일로 남김 · 트리거가 있는 표는 미리 알림). 자세한 순서는 안내서 7절에 있습니다.
### 고친 점
- MySQL 표 구조 편집에서 열의 주석·형·NULL·기본값을 바꿀 때 AUTO_INCREMENT·unsigned·ON UPDATE CURRENT_TIMESTAMP·열 문자 집합·콜레이션이 사라지던 문제를 고쳤습니다. 이제 원래 속성을 그대로 이어 적고, 지킬 수 없는 열(생성 열 등)은 바꾸기 전에 이유와 함께 막습니다. 다른 열만 바꿀 때 주석 바꾼 열이 빠지던 것도 고쳤습니다.
- Oracle 19c에서 서버를 막 켠 뒤 DDL 보기를 여러 번 열면 '순서가 맞지 않는 가져오기'(ORA-01002)가 이어서 나던 원인을 찾아 고쳤습니다(같은 조회를 다시 실행할 때 열 정의를 다시 보내는 순서). 이제 다시 읽기 없이도 오류가 나지 않습니다.
- Oracle 쿼리 편집기에서 `:NEW`·`:OLD`를 쓰는 트리거를 만들 때 "바인드 값이 필요합니다"로 막히던 문제를 고쳤습니다(Instant Client 없이 연결한 경우).
- PostgreSQL 표의 DDL 보기에 그 표의 트리거(CREATE TRIGGER)가 함께 나오고, 외래 키 대상 표도 스키마까지 적습니다.
- 실제 실행 계획의 안전 장치를 넓혔습니다. SQL Server에서 `USE`·`SET NOCOUNT` 같은 세션 설정이 섞인 문장, MySQL에서 MyISAM 등 되돌릴 수 없는 표를 고치는 문장은 실행하지 않고 이유를 알려 드립니다. MySQL이 실측을 주지 않은 경우에도 예상 계획을 보여 준다는 안내가 붙습니다.
- 숫자 저장 형식 고치기가 마지막 확정 단계에서 연결이 끊기면, '바뀐 것 없음' 대신 '확정됐는지 알 수 없음 — 다시 점검'과 원래 값 파일 위치를 알려 드립니다.
- 정보 창 '바뀐 것'에서 지난 판을 펼쳤을 때 그 판 제목이 위로 다 올라가지 못하던 것을 고쳤습니다.

지난 판들의 노트는 [CHANGELOG.md](CHANGELOG.md)에 있습니다.

## 주요 기능

- **한 앱, 네 가지 DB** — 별도 클라이언트 설치 없이 바로 연결합니다. Oracle 11g도 Instant Client 없이 붙습니다.
- **글자가 깨지지 않는 연결** — US7ASCII·CP949 같은 오래된 문자셋의 한글도 서버에 있는 그대로 읽고 씁니다.
- **빠른 SQL 편집기** — 자동 완성, 문장 단위 실행, 탭마다 따로 쓰는 DB 세션, 실행 계획.
- **큰 결과도 가볍게** — 수십만 행 결과를 부드럽게 넘겨 보고, 표 안에서 바로 고쳐 저장합니다.
- **가져오기·내보내기** — CSV·TSV·엑셀·JSON·INSERT 문. 엑셀에서 복사한 내용을 표에 바로 붙여 넣습니다.
- **옮겨 오기 쉬움** — DBeaver·SQL Developer·DataGrip의 연결 목록을 가져옵니다(비밀번호는 가져오지 않음).
- **클라우드 DB** — AWS·Azure·Google Cloud·Oracle Cloud의 DB에 맞는 인증·보안 연결을 고릅니다.
- **비밀번호는 안전하게** — 운영체제 키체인(맥)·자격 증명 관리자(Windows)에만 저장합니다.

## 지원 환경

- **DB** — Oracle 11.2 이상 · PostgreSQL · MySQL / MariaDB · SQL Server
- **운영체제** — macOS(Apple Silicon) · Windows 10·11(64비트)
- **화면 언어** — 한국어 · English
