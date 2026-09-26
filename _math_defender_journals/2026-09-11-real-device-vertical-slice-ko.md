---
title: 휴대폰에서 두 바퀴 돌았다
date: 2026-09-11 21:30:00 +0900
lang: ko
category: FIRST PLAYABLE VERTICAL SLICE
summary: 에디터에서는 돌던 게임이 실제 Android 기기에서는 계속 막혔다. 화면, 터치, 배치, 재시작을 하나씩 고쳐서 결국 두 번째 플레이까지 이어졌다.
description: Math Defender의 첫 playable vertical slice가 실제 Android 기기에서 반복 플레이까지 통과하기까지의 과정.
permalink: /journals/2026-09-11-real-device-vertical-slice.html
translation_url: /en/journals/2026-09-11-real-device-vertical-slice.html
---
지난 기록에서는 Math Defender가 처음으로 한 스테이지를 끝까지 돌았다.

문제를 풀고,
Scout를 지나고,
영웅을 배치하고,
전투하고,
Result까지 가서 다시 시작할 수 있었다.

그때는 꽤 큰 고비를 넘었다고 생각했다.

그런데 실제 Android 휴대폰에 넣어보니 다시 이야기가 달라졌다.

*아래 화면 이미지는 당시 실기기 사진이 아니라, 이후 해당 플레이 흐름을 Unity Play Mode에서 재현해 생성한 저널용 캡처다.*

![실제 기기 기준으로 다시 다듬은 Math Defender Problem 화면](https://fiverocksgames.github.io/math-defender/assets/journals/2026-09-11/problem-388c8bd4.png)

*실기기 검증에서 다룬 Problem 단계를 Play Mode로 재현한 캡처. 에디터에서 보이던 것과 실제 휴대폰에서 읽고 누를 수 있는 것은 같은 문제가 아니었다.*

처음에는 문제 화면이 너무 작았다.
전투판은 화면에 제대로 들어오지 않았고,
Preparation에서는 보이는 버튼을 눌러도 실제 배치 흐름이 자연스럽게 이어지지 않았다.

에디터에서 "된다"와 휴대폰에서 "플레이할 수 있다"는 또 다른 말이었다.

한 번 고치고 다시 올렸다.
이번에는 화면 방향과 크기는 나아졌지만 Scout가 작았다.

![Scout 단계 Play Mode 재현 화면](https://fiverocksgames.github.io/math-defender/assets/journals/2026-09-11/scout-388c8bd4.png)

*Scout 단계의 저널용 Play Mode 재현 캡처. 실제 기기에서 확인한 문제는 화면 크기와 가독성이었다.*

다시 고쳤다.

그다음에는 터치 입력은 들어가는데 영웅이 놓이지 않았다.
카드를 끌어서 칸 위에 가져다 놓는 동작 자체는 인식됐지만, 실제 영웅 prefab 연결이 기기 빌드에서 맞지 않아 배치가 실패했다.

그래서 Preparation의 입력 방식도 바꿨다.

기존에는

> 영웅 선택 → 칸 선택 → Place 버튼

처럼 여러 단계를 거쳤다.

휴대폰에서는 이 흐름이 생각보다 자주 헷갈렸다.
그래서 화면 아래 Hero Bar에서 영웅 카드를 바로 끌어 전투판 칸에 놓는 Drag-to-Place 방식으로 바꿨다.

![Hero Bar에서 전투판으로 바로 끌어 놓는 Preparation 화면](https://fiverocksgames.github.io/math-defender/assets/journals/2026-09-11/preparation-388c8bd4.png)

*Preparation 단계. 여러 번 눌러 배치하던 흐름 대신 Hero Bar의 카드를 전투판 칸으로 바로 끌어 놓는 방식으로 바뀌었다.*

유효한 칸 위에서는 피드백이 보이고,
놓으면 즉시 배치되고,
골드가 차감되고,
실제 배치가 끝난 뒤에만 전투를 시작할 수 있게 했다.

문제는 한 번에 끝나지 않았다.

실제 기기에서 다시 확인할 때마다

- 글씨 크기,
- Scout 화면,
- 영웅 카드 표시,
- 터치 좌표,
- Grid 판정,
- 영웅 prefab 연결,
- Restart 뒤 초기 상태

같은 것들이 차례로 걸렸다.

자동 테스트가 통과해도 휴대폰에서 막히면 다시 수정했다.
Journal Capture가 성공해도 실제 손가락으로 배치가 안 되면 완료로 보지 않았다.

그리고 9월 11일,
마지막 빌드를 다시 실제 Android 기기에서 돌렸다.

영웅을 끌어 놓고,
전투를 시작하고,

![배치를 마치고 실제 전투가 진행되는 Battle 화면](https://fiverocksgames.github.io/math-defender/assets/journals/2026-09-11/battle-388c8bd4.png)

*Battle 단계의 Play Mode 재현 캡처. 실기기에서는 배치를 끝낸 뒤 전투까지 이어지는 흐름을 별도로 확인했다.*

Result까지 간 다음,
Restart Stage를 눌렀다.

![전투를 끝내고 다시 시작할 수 있는 Result 화면](https://fiverocksgames.github.io/math-defender/assets/journals/2026-09-11/result-388c8bd4.png)

*Result 단계의 Play Mode 재현 캡처. 실기기에서는 Restart Stage 뒤 깨끗한 Problem 상태로 돌아가는 것까지 검증했다.*

게임은 깨끗한 Problem 상태로 돌아왔다.

거기서 다시 한 번 진행했다.

두 번째 run도 Preparation과 Battle까지 정상적으로 이어졌다.

이번에는 "한 번 끝까지 갔다"보다 조금 더 중요한 걸 확인했다.

**끝까지 간 뒤 다시 시작해도 게임이 계속 플레이된다.**

이 과정에서 첫 playable vertical slice도 마침내 기준선을 통과했다.

아직 완성된 게임은 아니다.
전투 보드는 더 보기 좋아져야 하고,
Hero Bar와 Grid도 더 다듬어야 한다.
무엇보다 지금 구조가 정말 재미있는지는 계속 확인해야 한다.

하지만 이제는 적어도 실제 휴대폰을 손에 들고

> 문제를 풀고 → 준비하고 → 싸우고 → 결과를 보고 → 다시 시작한다

는 흐름을 반복할 수 있다.

지난번에는 "연결됐다"와 "플레이된다"가 다르다는 걸 배웠다.

이번에는 하나를 더 배웠다.

"한 번 플레이된다"와 "다시 플레이된다"도 다른 말이었다.

그래서 이번 기록의 기준은 두 바퀴다.