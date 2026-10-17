### Echo · jayden0903

게임 서버와 macOS 도구를 만듭니다. 한국어 마인크래프트 생존 서버 하나를 엔진 패치부터 접속 경로, 안티치트, 채팅 감시, 운영 도구까지
혼자 만들고 운영하면서 나온 것들을 정리해 두었습니다.

I build game-server infrastructure and small macOS tools. Most of the code here came out of running a Korean Minecraft
survival server end to end: engine patches, ingress routing, anticheat tooling, chat moderation and operations.

#### Projects

| | What it does | Stack |
|---|---|---|
| [**LidOn**](https://github.com/jayden0903/LidOn) | 맥북 뚜껑을 닫아도 빌드·AI 코딩 에이전트가 계속 돌게 해 주는 메뉴 막대 앱. `brew install --cask jayden0903/tap/lidon` | Swift, SwiftUI |
| [**minecraft-anticheat-replay**](https://github.com/jayden0903/minecraft-anticheat-replay) | 의심 플레이어의 마지막 1분을 게임 안에서 다시 보는 플러그인. 플레이어뿐 아니라 주변 몹과 그 시점의 블록까지 되살림 | Java, PacketEvents, CoreProtect |
| [**korean-chat-moderation**](https://github.com/jayden0903/korean-chat-moderation) | 한국어 게임 채팅 감시: 규칙 → 앞 대화를 보는 문맥 모델 → 애매한 줄만 로컬 LLM. GPU 없이 CPU 한 대에서 | Python, PyTorch, llama.cpp |
| [**folia-spawn-governor**](https://github.com/jayden0903/folia-spawn-governor) | 렉 걸린 Folia 리전에서만 몹 스폰을 줄임. 50명이 한 리전에 묶인 최악의 경우 4 TPS → 19.4–19.9 TPS | Java, Folia |
| [**folia-exact-perf-patches**](https://github.com/jayden0903/folia-exact-perf-patches) | 게임 결과는 바닐라와 똑같이 두고 계산만 줄이는 Folia 26.2 패치 3개 | Java, Folia patches |
| [**minecraft-ingress-queue**](https://github.com/jayden0903/minecraft-ingress-queue) | TCPShield 뒤에서 경로 여러 개로 트래픽을 나누고, 서명된 일회용 입장표와 공정 대기열로 받는 입구 서버 | Java, Paper, Velocity |
| [**mc-server-supervisor**](https://github.com/jayden0903/mc-server-supervisor) | screen으로 돌리는 서버의 감시·순서 시작·안전 재시작. 일부러 끈 것과 죽은 것을 구분 | Python (stdlib only) |
| [**minecraft-panorama-webgl**](https://github.com/jayden0903/minecraft-panorama-webgl) | 게임에서 찍은 6면 사진으로 타이틀 화면 같은 웹 배경을 그리는 WebGL 컴포넌트 | WebGL, JavaScript |

#### Things I care about

- 측정하고 나서 바꾸기. 숫자는 실험 서버와 실제 운영 기록에서 잰 것만 씁니다.
- 게임 결과를 바꾸지 않는 최적화. 바닐라와 다르게 동작하면 버그로 봅니다.
- 되돌릴 수 있게 바꾸기. 모든 운영 변경은 이전 파일과 되돌리는 방법을 같이 남깁니다.
