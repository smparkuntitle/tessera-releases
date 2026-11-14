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
  최신 버전 <b>0.9.4</b> · 2026-11-14 출시 · <a href="CHANGELOG.md">업데이트 노트</a>
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

## 이전 판(0.8.20)으로 돌아가기

0.9 판(새 화면 — 0.9.0·0.9.1)에서 문제가 있으면 언제든 0.8.20으로 돌아갈 수 있습니다. 0.9 판은 연결·설정·편집기 파일을 0.8.20이 읽는 형식으로 저장하므로 그대로 보입니다(0.9 판에서 바꾼 연결·설정도 이어집니다). 비밀번호는 0.8.20 때 저장한 것이 그대로 남아 있고, 0.9 판에서 새로 저장하거나 바꾼 비밀번호는 0.8.20에서 다시 넣어야 합니다. 연결 목록의 폴더·접힘·패널 크기와 스니펫은 0.9.1의 것이라 0.8.20에서는 보이지 않습니다(지워지지 않습니다 — 0.9.1로 돌아오면 다시 보입니다). 0.9.0을 처음 실행하기 전 상태는 앱 데이터 폴더의 `backup-before-0.9.0` 사본에 있습니다.

1. Tessera를 닫습니다.
2. [0.8.20 릴리스](https://github.com/smparkuntitle/tessera-releases/releases/tag/v0.8.20)에서 설치본을 받습니다 — 맥 `Tessera-0.8.20-arm64.dmg` · Windows `Tessera_0.8.20_x64-setup.exe`(폐쇄망 `Tessera_0.8.20_x64-offline-setup.exe`).
3. 그 위에 설치합니다(맥은 Applications 폴더에 덮어 놓기, Windows는 설치 파일 실행).
4. Tessera를 열면 0.8.20으로 열립니다. 맥은 앱이 바뀌었으므로 저장된 비밀번호를 처음 읽을 때 키체인 암호 창이 다시 뜹니다 — 로그인 암호를 넣고 [항상 허용]. 새 판 업데이트 알림이 오면 '나중에'를 누르세요.

## 이번 판에서 바뀐 점 (0.9.4)

### 고친 점
- **자동 커밋 탭에서 스키마·데이터베이스를 바꾼 뒤의 실행이 다른 스키마의 같은 이름 표를 바꿀 수 있던 문제를 고쳤습니다.** Oracle `ALTER SESSION SET CURRENT_SCHEMA`, MySQL·SQL Server `USE`, PostgreSQL `SET search_path` 같은 세션 설정은 그 문장이 돈 세션에만 남는데, 그 탭의 다음 실행이나 결과 편집 커밋이 다른 세션에서 돌면(다른 탭 실행·스키마 트리·자동 완성 등이 그 세션을 쓰던 순간) 로그인 스키마의 같은 이름 표가 바뀌었습니다. 0.8.0부터 있던 문제입니다(PostgreSQL·SQL Server·Oracle에서 확인, MySQL은 같은 길로 봄 — 같은 이름 표가 두 스키마에 있을 때만, 없으면 '표 없음' 오류로 끝났습니다). 이제 세션 설정을 실행한 탭은 자기 세션에서만 실행하고(상태줄 '세션 고정' — 세션 설정·PL/SQL 블록·프로시저 호출을 돌린 자동 커밋 탭은 그 탭 전용 연결을 하나 더 씁니다), 그 세션이 끊기면 다른 세션에서 돌리지 않고 실행을 막은 뒤 설정 문장을 다시 실행하라고 알립니다. 트랜잭션이 열린 탭에서는 세션 설정 문장을 받지 않습니다(커밋·롤백 뒤 다시). 이전 판에서 자동 커밋 탭으로 세션 설정(스키마 바꾸기) 뒤에 UPDATE·DELETE·결과 편집을 했다면, 로그인 스키마에 같은 이름 표가 있는지와 그 표의 값을 확인해 주세요.
- 서버가 막 켜진 Oracle에 붙은 직후, 배경 사전 조회(편집 준비·외래 키 정보)가 세션을 모두 차지해 새 탭의 조회가 최대 25초 기다리던 것을 고쳤습니다. 배경 조회는 세션 하나만 차례로 쓰고 사용자 실행이 먼저입니다.
- 같은 때 연결 끊김 알림이 연결 직후 준비 작업이 끝날 때까지 늦던 것을 고쳤습니다(Oracle 11.2 시험 서버에서 4~6초 → 바로. 19c 시험 서버에서는 연결 직후 스키마 트리를 불러오는 동안 3초쯤 남았습니다).
- `SELECT … FROM DUAL`처럼 편집할 수 없는 Oracle 사전 표 조회는 편집 준비 확인 없이 바로 실행합니다(서버가 막 켜진 직후 13~15초 기다리던 것).
- 키 없는 Oracle 표의 편집 준비 확인이 3초를 넘으면 결과를 먼저 보여 주고, 준비가 끝나면 같은 조회를 한 번 더 가져와 편집을 켭니다(예전에는 결과를 20초까지 붙잡았습니다). 다시 가져올 때는 정렬·거르기·선택·스크롤을 그대로 두고, 메시지 탭에 "편집을 켜려고 같은 조회를 한 번 더 가져왔습니다"를 남깁니다. 10초 넘게 걸린 조회는 다시 보내지 않습니다.
- 라이트 테마에서 [수동] 커밋 단추가 켜졌는지 잘 보이지 않던 것을 고쳤습니다(켜진 칸에 진한 테두리와 면).

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
