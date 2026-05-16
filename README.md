# Onboarding

# AI 바이브코딩 핸즈온 사전 설치 가이드 (Windows)

## 이 가이드의 목적

5/27 핸즈온 전에 아래 두 경로 중 **하나 이상**을 준비해 주세요.

- **A. 클로드 (Claude)** — Claude Desktop 앱 안의 코드 실행 기능을 사용
- **B. 코덱스 (ChatGPT)** — cmd(명령 프롬프트)에서 Codex CLI 사용

강사 시연은 Claude 기준으로 진행되지만, ChatGPT 사용자는 Codex CLI로 같은 워크플로우를 따라갈 수 있습니다. 가능하면 두 경로 모두 깔아두시는 것을 권장합니다.

**예상 소요 시간:** 경로당 10~20분

> WSL(Windows Subsystem for Linux)은 필요하지 않습니다. 일반 Windows 환경에서 그대로 진행하시면 됩니다.

---

## Step 0. Windows 버전 확인 (Windows 10 사용자만)

`Win + R` → `winver` 입력 → Enter. 창에 표시되는 버전을 확인합니다.

- **Windows 11 사용자:** Windows Terminal이 기본 내장되어 있습니다. **Step 1로 바로 이동.**
- **Windows 10 사용자:** PowerShell 기본 창이 강의 환경과 다소 다를 수 있어, **Windows Terminal 설치를 먼저 권장합니다.**

### Windows 10 — Windows Terminal 설치

[Microsoft 공식 가이드](https://learn.microsoft.com/ko-kr/windows/terminal/install)에서 안내된 방법 중 하나로 설치하세요. 가장 간단한 방법은 Microsoft Store에서 "Windows Terminal" 검색 → 설치입니다.

설치 후 시작 메뉴에서 "Terminal" 또는 "Windows Terminal"을 실행할 수 있게 됩니다. 이후 이 가이드에서 "PowerShell"이나 "cmd"라고 적힌 부분은 Windows Terminal 안에서 해당 탭을 여는 것으로 대체할 수 있습니다.

---

# A. 클로드의 경우

## Step 1. Claude Pro 구독 ($20/월)

1. 브라우저에서 [claude.ai](https://claude.ai) 접속
2. 우측 상단 **Sign up** → 이메일로 가입 또는 Google 로그인
3. 좌측 하단 프로필 → **Upgrade Plan** → **Pro** 선택 → 결제 정보 입력
4. 결제 완료 시 프로필 아래 "Pro" 뱃지 표시

> 이미 ChatGPT Plus 구독 중인 경우 **B 경로**로 참여 가능합니다. 단, 강사 시연은 Claude 기준으로 진행됩니다.
>
> **Gemini의 경우 코딩 도구(에이전트)가 Claude/ChatGPT와 달라 본 핸즈온 워크플로우에 그대로 적용하기 어렵습니다.**

---

## Step 2. Claude Desktop 앱 설치

1. [claude.ai/download](https://claude.ai/download) 접속
2. **Download for Windows** 클릭 → `.exe` 설치 파일 다운로드
3. `.exe` 파일 더블클릭 → 설치 마법사 진행 (기본 옵션 그대로 Next)
4. 시작 메뉴에서 **Claude** 실행
5. 로그인 (Step 1에서 만든 계정)

---

## Step 3. Git for Windows 설치 (Claude Desktop 코드 실행에 필수)

### 3-1. 이미 설치되어 있는지 확인

1. 키보드 `Win + R` → `powershell` 입력 → Enter (PowerShell 창 열림)
   - Windows 10에서 Windows Terminal을 설치한 경우, 시작 메뉴에서 "Terminal" 실행해도 됩니다.
2. 아래 명령어 복사·붙여넣기 후 Enter.

```powershell
git --version
```

- `git version 2.xx.x.windows.x` 같은 버전이 출력되면 이미 설치되어 있습니다. → **최종 체크리스트로 바로 이동.**
- "not recognized…" 에러가 나면 아래 3-2 진행.

### 3-2. Git for Windows 설치

1. [gitforwindows.org](https://gitforwindows.org) 접속
2. **Download** 클릭 → `Git-2.xx.x-64-bit.exe` 다운로드
3. 다운로드 파일 더블클릭 → 설치 마법사 진행
4. 설치 옵션 (기본값 그대로 **Next** 눌러도 OK):

| 단계 | 권장 옵션 |
|------|-----------|
| License | Next |
| Select Destination | Next (기본 경로) |
| Select Components | Next (기본 체크) |
| Select Start Menu Folder | Next |
| Choosing the default editor | **"Use Notepad…"** 선택 (권장, VS Code 있으면 VS Code 선택 가능) |
| Adjust PATH environment | **"Git from the command line and also from 3rd-party software"** 선택 (기본값) |
| Choose SSH executable | Next |
| HTTPS transport backend | Next |
| Line ending conversions | Next (기본값) |
| Terminal emulator | Next |
| Default behavior of `git pull` | Next |
| Credential helper | Next |
| Extra options | Next |

5. **Install** 클릭 → 완료까지 2~5분 대기

### 3-3. 설치 확인

> **중요: PowerShell 창을 완전히 닫고 다시 열어야 PATH가 적용됩니다.**

1. 기존 PowerShell 창 닫기
2. `Win + R` → `powershell` → Enter (새 PowerShell 창)
3. 아래 명령어 실행

```powershell
git --version
```

버전 번호가 출력되면 ✅ 완료.

---

# B. 코덱스 (ChatGPT)의 경우

> 이 경로는 **cmd(명령 프롬프트)**에서 동작합니다. `Win + R` → `cmd` 입력 → Enter 로 cmd 창을 열어주세요. PowerShell이나 Windows Terminal에서도 동일하게 작동합니다.

## Step 1. ChatGPT Plus 구독 ($20/월)

1. 브라우저에서 [chatgpt.com](https://chatgpt.com) 접속
2. 우측 상단 **Sign up** → 이메일로 가입 또는 Google 로그인
3. 좌측 하단 프로필 → **Upgrade plan** → **Plus** 선택 → 결제 정보 입력
4. 결제 완료 시 프로필 아래 "Plus" 뱃지 표시

> Codex CLI는 ChatGPT Plus / Pro / Business / Edu / Enterprise 구독에 모두 포함되어 있어 별도 라이선스가 필요 없습니다. Plus($20/월)면 충분합니다.

---

## Step 2. Node.js 22 LTS 설치 (Codex CLI의 필수 의존성)

Codex CLI는 npm으로 설치하기 때문에 Node.js 22 이상이 필요합니다.

### 2-1. 이미 설치되어 있는지 확인

1. `Win + R` → `cmd` 입력 → Enter (cmd 창 열림)
2. 아래 명령어 복사·붙여넣기 후 Enter.

```cmd
node --version
```

- `v22.x.x` 또는 그 이상이 출력되면 이미 설치되어 있습니다. → **Step 3으로 이동.**
- 버전이 `v22` 미만이거나 "not recognized…" 에러가 나면 아래 2-2 진행.

### 2-2. Node.js 22 LTS 설치

1. [nodejs.org](https://nodejs.org) 접속
2. **LTS** 버전(22.x) 다운로드 → `node-v22.x.x-x64.msi` 파일
3. 다운로드 파일 더블클릭 → 설치 마법사 진행 (기본 옵션 그대로 **Next**)
   - "Automatically install the necessary tools…" 체크박스는 **체크 해제 권장** (시간이 오래 걸리고 본 핸즈온에는 불필요)
4. **Install** 클릭 → 완료까지 1~3분 대기

### 2-3. 설치 확인

> **중요: cmd 창을 완전히 닫고 다시 열어야 PATH가 적용됩니다.**

1. 기존 cmd 창 닫기
2. `Win + R` → `cmd` → Enter (새 cmd 창)
3. 아래 두 명령어 실행

```cmd
node --version
npm --version
```

두 줄 모두 버전 번호가 출력되면 ✅ 완료.

---

## Step 3. Codex CLI 설치 및 인증 (cmd에서)

### 3-1. Codex CLI 전역 설치

cmd 창에서 아래 명령어 실행:

```cmd
npm install -g @openai/codex
```

> **패키지 이름에 주의하세요.** 반드시 `@openai/codex` 입니다. `codex` (스코프 없음) 는 OpenAI와 무관한 2012년 패키지이므로 잘못 설치하면 동작하지 않습니다.

설치는 30초~2분 정도 걸립니다. 끝나면 아래로 확인:

```cmd
codex --version
```

버전 번호가 출력되면 ✅ 설치 완료.

### 3-2. ChatGPT 계정으로 로그인

cmd 창에서 아래 명령어 실행:

```cmd
codex
```

처음 실행하면 인증 화면이 뜹니다. **"Sign in with ChatGPT"** 를 선택하면 브라우저가 열립니다. Step 1에서 만든 ChatGPT Plus 계정으로 로그인하면 됩니다.

로그인 완료 후 cmd 창으로 돌아오면 Codex CLI 프롬프트가 표시됩니다. 종료는 `Ctrl + C` 두 번 또는 `/exit` 입력.

### 3-3. (권장) Git for Windows 설치

Codex CLI는 Git을 직접 호출해 변경사항을 staging/commit 합니다. **A 경로의 Step 3** 을 참고해 Git for Windows를 설치해 주세요. A 경로를 같이 준비하시는 분은 이미 설치되어 있을 겁니다.

---

## 트러블슈팅

### PowerShell/cmd 에서 "git : 용어가 인식되지 않습니다…" 에러

- PowerShell/cmd 창을 **완전히 닫고 다시 열어** 주세요. PATH가 재적용됩니다.
- 그래도 안 되면 컴퓨터 재부팅 후 재시도.

### cmd 에서 "npm : 용어가 인식되지 않습니다…" 또는 "codex : 용어가 인식되지 않습니다…" 에러

- Node.js 설치 후 cmd 창을 **완전히 닫고 다시 열어** 주세요.
- `node --version` 부터 동작하는지 확인 → `npm install -g @openai/codex` 재시도.
- 그래도 안 되면 컴퓨터 재부팅 후 재시도.

### `npm install -g` 에서 권한 에러 (`EACCES`, `EPERM`)

- cmd 창을 **관리자 권한으로 실행**해 보세요. 시작 메뉴에서 "명령 프롬프트" 우클릭 → "관리자 권한으로 실행".

### Codex CLI 실행 시 "not authenticated" 메시지

- `codex` 명령 후 **"Sign in with ChatGPT"** 가 보이지 않으면 `codex auth login` 으로 다시 시도하세요.

### 회사/병원 보안 정책으로 설치가 막힐 때

- 관리자 권한 또는 IT 부서 확인이 필요할 수 있습니다.
- 본인 노트북(개인 소유)으로 참여 권장.

---

## 최종 체크리스트

설치 완료 후 본인이 준비한 경로의 항목이 모두 ✅ 되어야 핸즈온 당일 바로 시작할 수 있습니다.

### A. 클로드 경로

- [ ] claude.ai 에서 Pro 구독 활성화 확인
- [ ] Claude Desktop 앱 로그인 완료
- [ ] PowerShell(또는 Windows Terminal)에서 `git --version` 실행 시 버전 출력

### B. 코덱스 (ChatGPT) 경로

- [ ] chatgpt.com 에서 Plus 구독 활성화 확인
- [ ] cmd 에서 `node --version` 실행 시 `v22.x.x` 이상 출력
- [ ] cmd 에서 `codex --version` 실행 시 버전 출력
- [ ] `codex` 실행 후 ChatGPT 계정으로 로그인 완료

### 공통

- [ ] Appstore/Playstore 에서 2개의 App 다운받기: Github 앱과, 인증을 위한 Google Authenticator, Authy, Microsoft Authenticator 중 1개 선택해서 깔아놓기만 함
