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
  최신 버전 <b>0.8.16</b> · 2026-10-24 출시 · <a href="CHANGELOG.md">업데이트 노트</a>
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

## 이번 판에서 바뀐 점 (0.8.16)

### 바뀐 점
- Oracle 11g(11.2)에도 Instant Client 없이 바로 연결합니다. 대소문자를 가리지 않던 옛 방식의 비밀번호도 됩니다. Instant Client는 꼭 필요한 경우에만 쓰고, 그때는 이유를 연결 진단에 보여 줍니다.
- Oracle Cloud 지갑(zip)을 가져와 보안 연결로 붙습니다.
- 쿼리 탭을 끌어서 순서를 바꿀 수 있습니다. 키보드로도 옮길 수 있고, 바꾼 순서는 다시 열어도 그대로입니다.
- 새 쿼리 탭을 ⌘T(Windows는 Ctrl+T), '파일 › 새 쿼리 탭', 명령 팔레트, 연결 우클릭, 탭 줄 빈 곳 두 번 누르기로 엽니다.
- 연결 설정 '고급'에 '클라우드' 칸이 생겼습니다. AWS·Azure·Google Cloud·Oracle Cloud 중 고르면 그에 맞는 인증·보안 연결 칸만 나타납니다. 호스트 주소가 클라우드 주소로 보이면 한 줄로 알려 드리고, 설정은 직접 켜실 때만 바뀝니다.
- 업데이트를 받는 동안 진행률(받은 크기·남은 시간)과 설치·다시 시작 단계를 보여 줍니다.
- 업데이트 알림과 정보 창에서 이번 판에서 바뀐 점을 읽을 수 있고, 지난 판들의 노트도 볼 수 있습니다.
- 앱 이름은 어디서나 'Tessera'입니다. 버전은 정보 창·업데이트 안내·프로그램 목록의 버전 칸에만 보입니다.
### 고친 점
- 오류 안내 문구와 업데이트 안내에 남아 있던 옛 버전 표기를 지웠습니다.
- 예전 판에서 11g 연결에 Instant Client를 쓰도록 정해져 있던 연결도, 이번 판에서는 먼저 Instant Client 없이 연결해 봅니다. 그렇게 못 할 때는 비밀번호를 보내기 전에 멈추고 Instant Client로 넘어갑니다.
- 클라우드 로그인 토큰은 서버 인증서를 확인하는 보안 연결로만 보냅니다.
### 알아 둘 점
- 클라우드 로그인 토큰은 저장하지 않습니다. 연결할 때마다 이 컴퓨터의 AWS·Azure·Google Cloud 로그인 정보에서 새로 받습니다.
- 맥에서 새로 설치하면 앱 이름이 'Tessera'로 바뀝니다. 예전 0.7을 같은 이름으로 설치해 두었다면 덮어쓸지 묻습니다. 앱 안에서 업데이트한 경우에는 원래 이름이 그대로 남습니다 — 바꾸려면 앱을 끈 뒤 응용 프로그램 폴더에서 이름을 'Tessera'로 바꾸면 됩니다.
- 내려받기 파일 이름에 버전이 없어졌습니다. 설치본 저장소 첫 화면의 단추는 늘 최신 판을 내려받습니다.

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
