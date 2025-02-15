# Temperature Control Automation Script

이 코드는 한국의 유튜버 [애플코딩](https://youtu.be/bn59L-ar744?si=HNe4R0KTGRzrVgSE)의 [세계최초 온라인 에어컨](http://myaircon.online)을 조절하는 리모컨이다. 아쉽게도 세계최초 온라인 에어컨의 조작부는 모두에게 공개되어 있기 때문에 내가 원하는 온도를 유지하는 게 어려워 이 코드를 제작하게 되었다.

![myaircon-online-remote](https://github.com/user-attachments/assets/91e46f6c-4f16-48c7-b988-1d541f881207)

이 스크립트는 27°C의 최적 온도를 유지하기 위해 온도를 자동으로 조절하며, 딜레이 시간을 자동으로 조정하고, 사용자가 설정을 조작할 수 있는 인터페이스를 제공합니다.

## 기능

- 원하는 온도(27°C)를 유지하기 위해 온도를 자동으로 조절합니다.
- 온도가 원하는 값에 도달할 때까지 딜레이 시간을 동적으로 업데이트합니다.
- 딜레이 시간을 수동으로 설정하고 자동 조절 기능을 토글할 수 있는 사용자 인터페이스를 제공합니다.
- 온도 상태와 현재 딜레이 시간을 실시간으로 로그에 표시합니다.

## 작동 방식

1. **온도 조절**:
    - 스크립트는 현재 온도를 표시하는 HTML 요소의 변화를 관찰합니다.
    - 온도가 원하는 값보다 낮으면 플러스 버튼을 클릭하여 온도를 올립니다.
    - 온도가 원하는 값보다 높으면 마이너스 버튼을 클릭하여 온도를 낮춥니다.

2. **자동 딜레이 조절**:
    - 스크립트는 샘플링 기간 동안 원하는 온도의 비율을 계산합니다.
    - 비율이 목표값(38%)보다 낮으면 딜레이 시간을 줄여 조정 속도를 높입니다.
    - 비율이 목표값보다 높으면 딜레이 시간을 늘려 조정 속도를 늦춥니다.

3. **사용자 인터페이스**:
    - 사용자가 딜레이 시간을 슬라이더로 수동 설정할 수 있도록 컨트롤 패널을 추가합니다.
    - 자동 조절 기능을 켜고 끌 수 있는 버튼을 제공합니다.
    - 실시간 로그와 현재 딜레이 시간을 컨트롤 패널에 표시합니다.

## 설치 및 사용법

1. 리포지토리 클론:
    ```sh
    $ git clone https://github.com/koreazombie/myaircon-online-remote.git
    ```

2. 프로젝트 디렉토리로 이동:
    ```sh
    $ cd myaircon-online-remote
    ```
    
3. 코드를 복사하여 웹 브라우저의 개발자 도구 콘솔 창에 붙여넣기:
    - 웹 페이지를 열고, `F12` 또는 `Ctrl+Shift+I`를 눌러 개발자 도구를 엽니다. 맥(MAC) `Command+option+i`
    - `Console` 탭으로 이동합니다.
    - `temperature-control-automation.js` 파일의 코드를 복사하여 콘솔 창에 붙여넣고 엔터를 눌러 실행합니다.