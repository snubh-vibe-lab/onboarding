# AI 바이브코딩 핸즈온 사전 설치 가이드 (Mac)

## 이 가이드의 목적

5/27 핸즈온에서 Claude Desktop 앱 안의 코드 실행 기능을 사용하려면 컴퓨터에 Git이 깔려 있어야 합니다. 이 가이드는 Mac 사용자가 핸즈온 전에 아래 3가지를 준비할 수 있도록 돕습니다.

- Claude Pro 구독
- Claude Desktop 앱 설치
- Git 설치 (핵심)

**예상 소요 시간:** 15~30분 (인터넷 속도와 Homebrew 설치 여부에 따라 다름)

---

## Step 1. Claude Pro 구독 ($20/월)

1. 브라우저에서 [claude.ai](https://claude.ai) 접속
2. 우측 상단 **Sign up** → 이메일로 가입 또는 Google 로그인
3. 좌측 하단 프로필 → **Upgrade Plan** → **Pro** 선택 → 결제 정보 입력
4. 결제 완료 시 프로필 아래 "Pro" 뱃지 표시

> 이미 ChatGPT Plus 구독 중인 경우 그 도구로도 참여 가능합니다. 단, 강사 시연은 Claude 기준으로 진행됩니다.
>
> **Gemini의 경우 코딩 도구(에이전트)가 Claude/ChatGPT와 달라 본 핸즈온 워크플로우에 그대로 적용하기 어렵습니다.**

---

## Step 2. Claude Desktop 앱 설치

1. [claude.ai/download](https://claude.ai/download) 접속
2. **Download for Mac** 클릭 → `.dmg` 파일 다운로드
3. `.dmg` 파일 더블클릭 → Claude 아이콘을 **Applications 폴더로 드래그**
4. Applications 폴더에서 Claude 앱 실행
5. 로그인 (Step 1에서 만든 계정)

> Apple Silicon (M1/M2/M3/M4) Mac과 Intel Mac 모두 동일 방법입니다. 다운로드 시 자동으로 맞는 버전이 내려옵니다.

---

## Step 3. Git 설치 (Claude Desktop 코드 실행에 필수)

> 터미널을 한 번도 써본 적 없어도 괜찮습니다. 아래 순서대로만 따라 하시면 됩니다.

### 3-1. 터미널 열기

1. 키보드 `Cmd + Space` → "터미널" 입력 → Enter
2. 검은색 또는 흰색 창이 뜨면 성공

### 3-2. Git이 이미 설치되어 있는지 확인

터미널에 아래 명령어를 복사·붙여넣기 후 Enter.

```bash
git --version
```

- `git version 2.xx.x` 같은 버전이 출력되면 이미 설치되어 있습니다. → **최종 체크리스트로 바로 이동.**
- "command not found" 또는 설치 팝업이 뜨면 아래 3-3 진행.

### 3-3. Git 설치 (택 1)

#### 방법 A. Xcode Command Line Tools (가장 간단, 권장)

터미널에 아래 명령어 입력 → Enter.

```bash
xcode-select --install
```

팝업이 뜨면 **설치** 클릭 → **동의** → 5~10분 대기. 완료 후 터미널에서 다시 `git --version` 실행하면 버전이 출력됩니다.

#### 방법 B. Homebrew 경유 (이미 Homebrew 쓰시는 분)

```bash
brew install git
```

#### 방법 C. Homebrew 새로 설치 (고급)

Homebrew가 없는데 앞으로도 개발 도구를 깔 예정이면 이 방법. 그게 아니면 방법 A를 권장합니다.

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

설치 완료 후 아래 한 줄로 PATH 설정 (Apple Silicon Mac 기준).

```bash
echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> ~/.zshrc && source ~/.zshrc
```

그 다음:

```bash
brew install git
```

---

## 트러블슈팅

### "git: command not found" 가 계속 나올 때

- 터미널을 **완전히 닫고 다시 열어**보세요 (환경 변수 재적용).
- 그래도 안 되면 `xcode-select --install` 한 번 더 시도.

### Homebrew 설치 중 sudo 비밀번호 요구

- Mac 로그인 비밀번호를 입력하면 됩니다. 입력 중에는 화면에 아무것도 안 보이지만 정상 동작합니다.

### Apple Silicon Mac에서 `brew` 명령이 안 먹을 때

PATH 설정이 누락된 경우입니다.

```bash
eval "$(/opt/homebrew/bin/brew shellenv)"
```

### Intel Mac의 Homebrew 경로

Intel Mac은 `/usr/local/bin/brew` 입니다. Apple Silicon의 `/opt/homebrew` 대신 `/usr/local`로 대체하시면 됩니다.

---

## 최종 체크리스트

설치 완료 후 아래 3가지가 모두 ✅ 되어야 핸즈온 당일 바로 시작할 수 있습니다.

- [ ] claude.ai 에서 Pro 구독 활성화 확인
- [ ] Claude Desktop 앱 로그인 완료
- [ ] 터미널에서 `git --version` 실행 시 버전 출력
