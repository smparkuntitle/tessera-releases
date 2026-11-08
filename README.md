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
  최신 버전 <b>0.9.0</b> · 2026-11-08 출시 · <a href="CHANGELOG.md">업데이트 노트</a>
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

0.9.0(새 화면)에서 문제가 있으면 언제든 0.8.20으로 돌아갈 수 있습니다. 0.9.0은 0.8.20이 읽는 형식으로만 저장하므로 연결·비밀번호·설정·편집기 파일이 그대로 보입니다(0.9.0에서 바꾼 연결·설정도 그대로 이어집니다). 0.9.0을 처음 실행하기 전 상태는 앱 데이터 폴더의 `backup-before-0.9.0` 사본에 있습니다.

1. Tessera를 닫습니다.
2. [0.8.20 릴리스](https://github.com/smparkuntitle/tessera-releases/releases/tag/v0.8.20)에서 설치본을 받습니다 — 맥 `Tessera-0.8.20-arm64.dmg` · Windows `Tessera_0.8.20_x64-setup.exe`(폐쇄망 `Tessera_0.8.20_x64-offline-setup.exe`).
3. 그 위에 설치합니다(맥은 Applications 폴더에 덮어 놓기, Windows는 설치 파일 실행).
4. Tessera를 열면 0.8.20으로 열립니다. 맥은 앱이 바뀌었으므로 저장된 비밀번호를 처음 읽을 때 키체인 암호 창이 다시 뜹니다 — 로그인 암호를 넣고 [항상 허용]. 0.9.0 업데이트 알림이 오면 '나중에'를 누르세요.

## 이번 판에서 바뀐 점 (0.9.0)

### 바뀐 점
- **화면이 새로 바뀌었습니다(더 가볍고 빠른 판).** 연결·비밀번호·설정·편집기 파일·실행 기록은 그대로 이어서 씁니다. 처음 실행할 때 그때까지의 자료 사본(앱 데이터 폴더의 `backup-before-0.9.0`)을 먼저 남기고, 무엇을 옮겼는지 요약 창으로 알려 드립니다. 저장은 0.8.20이 읽는 형식 그대로라, 0.8.20으로 돌아가도 연결·설정이 그대로 보입니다.
- **맥: 업데이트 뒤 처음 켤 때 키체인 암호 창이 뜹니다.** 맥 로그인 암호를 넣고 **[항상 허용]**을 누르세요. 이번(0.8.20 → 0.9.0)에는 0.8.20이 따로 저장해 둔 비밀번호를 옮겨 오느라 저장된 비밀번호마다 한 번씩 연달아 뜹니다. 다음 업데이트부터는 앱을 켤 때 **한 번만** 뜨도록 바꿨습니다. 연결할 때는 뜨지 않습니다(비밀번호는 앱 데이터에 암호화해 두고, 여는 열쇠 하나만 키체인에 둡니다). 창에 바로 답하지 못해도 나중에 허용하면 이어서 씁니다. Windows에서는 뜨지 않습니다.
- 키체인 창에서 [거부]를 누르면 연결·연결 테스트 모두 서버에 접속하지 않고(빈 비밀번호를 보내지 않아 계정 잠금 횟수가 늘지 않습니다) 연결 창의 비밀번호 칸으로 안내합니다. 비밀번호를 다시 넣거나, 다음에 연결할 때 [항상 허용]을 누르면 됩니다.
- 실행 계획을 받는 데 오래 걸리면 지난 시간을 보여 주고, 실패하면 [다시 시도] 단추가 나옵니다.
### 알아 둘 점
- 새 화면으로 옮기지 못한 것: 스니펫(새 화면에 아직 없음), 사이드바의 최근 연결 순서·화면 배치, 창 크기·위치. 모두 원래 자리에 그대로 남아 있어 0.8.20으로 돌아가면 다시 보입니다.
- 0.9.0에서 바꾼 연결 비밀번호는 0.8.20으로 돌아가면 반영되지 않습니다(0.8.20은 원래 저장된 값을 씁니다). 거꾸로 0.8.20으로 돌아가 있는 동안 바꾼 비밀번호는, 다시 0.9로 올라온 뒤 그 연결의 비밀번호를 한 번 다시 넣어 주세요(새로 만든 연결은 그대로 옮겨 옵니다).
- 0.8.20으로 돌아가는 방법: https://github.com/smparkuntitle/tessera-releases#이전-판0820으로-돌아가기 — 0.8.20 설치본을 받아 그 위에 설치하면 연결·비밀번호·설정이 그대로 보입니다(맥은 그때도 키체인 창이 항목마다 한 번 뜹니다). 앱 안에서는 설정 › 진단 › '이전 판으로 돌아가기'에 같은 안내가 있습니다.

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
