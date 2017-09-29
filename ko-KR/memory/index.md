---
제목: 기억
난이도: Scratch 2
언어: ko-KR
stylesheet: scratch
embeds: "*.png"
materials: ["Club Leader Resources/*"]
...

## 커뮤니티 기부 프로젝트 { .challenge .pdf-hidden }
이 프로젝트는 Erik 과 그의 딸 Ruth가 만들고 기부했습니다. 자신의 프로젝트를 기부하고 싶으시다면 [Github에서 저희에게 연락주세요](https://github.com/CodeClub).

# 소개 { .intro }

이 프로젝트에선 무작위 색깔의 순서를 기억해야하는 기억하기 게임을 만들것입니다.

<div class="scratch-preview">
  <iframe allowtransparency="true" width="485" height="402" src="http://scratch.mit.edu/projects/embed/34874510/?autostart=false" frameborder="0"></iframe>
  <img src="colour-final.png">
</div>

# 1 단계: 무작위 색깔 { .activity }

먼저 무작위 순서로 색을 바꿀 수 있는 캐릭터를 만들어 봅시다.

## 단계별 체크리스트 { .check }

+ 새 스크래치 프로젝트를 시작하고 고양이 스프라이트를 지워서 프로젝트를 비게 만드세요. 온라인 스크래치 에디터는 <a href="http://jumpto.cc/scratch-new">jumpto.cc/scratch-new</a> 에서 찾을 수 있습니다.

+ 캐릭터와 배경을 고르세요. 캐릭터는 사람일 필요는 없지만 다른 색을 보여줄 수 있어야합니다.

	![screenshot](colour-sprite.png)

+ 이 게임에선 숫자로 다른 색깔들을 나타내게 할것입니다:

	+ 1 = 빨강;
	+ 2 = 파랑;
	+ 3 = green;
	+ 4 = yellow.

	캐릭터에게 위쪽의 숫자에 맞춘 네가지 색깔의 모양을 주세요. 모양들이 올바른 순서로 있는지 확인하세요.

	![screenshot](colour-costume.png)

+ 무작위 순서를 만드려면 __리스트__를 만들어야 합니다. 리스트는 많은 데이터를 __순서대로__ 저장하는 변수입니다. 새 리스트 `sequence` {.blockdata}를 만들고 캐릭터에서만 사용하면 되니 '이 스프라이트에서만 사용하기'를 체크해주세요. 

	![screenshot](colour-list.png)

	이제 빈 리스트가 왼쪽 상단에 보이고 또한 리스트를 사용하는 새 블록들이 나올것입니다.

	![screenshot](colour-list-blocks.png)

+ 이 코드를 캐릭터에 더해서 리스트에 무작위 숫자를 5번씩 더해넣게 (또한 거기에 맞는 모양을 보여주게)만드세요:

```blocks

깃발 클릭했을 때
(모두 v) 번째 항목을 [sequence v] 에서 삭제하기
(5) 번 반복하기
   ((1) 부터 (4) 사이의 난수)에 [sequence v] 추가하기
   모양을 ((last v) 번째 [sequence v] 항목) (으)로 바꾸기
   (1) 초 기다리기
end
```

	또한 시작하기 전에 리스트를 비웠다는 거에 주목해주세요.

## 도전과제: 소리 넣기 {.challenge}
프로젝트를 몇 번 시험해보세요. 가끔 같은 숫자가 두 번(혹은 그 이상) 연속으로 뽑혀서 순서를 기억하기 힘들게 만들 수 있습니다. 모양이 바뀔 때마다 드럼소리가 들리게 만들 수 있나요?

또한 숫자에 따라 다른 드럼 소리를 들리게 만들 수 있나요? 이 코드는 캐릭터의 모양을 바꾸는 코드와 _매우_ 비슷할 것입니다.

## 프로젝트를 저장하세요 { .save }

# 2 단계: 순서 반복하기 { .activity }

플레이어가 기억한 색의 순서대로 누를 수 있는 네 개의 버튼을 만듭시다.

## 단계별 체크리스트 { .check }

+ 프로젝트에 버튼이 될 네 개의 스프라이트를 더하세요. 각 스프라이트가 네 가지의 색깔에 맞게 수정해주세요.

	![screenshot](colour-drums.png)

+ 빨간 드럼을 클릭하면 캐릭터에게 빨간 드럼 버튼이 눌렸다는 메시지를 방송하게 만듭시다. 이 코드를 빨간 드럼에 더해주세요:

```blocks

이 스프라이트를 클릭했을 때
[red v] 방송하기
```

+ 캐릭터가 메시지를 받으면 1번이 리스트의 시작에 있는지 확인하도록 해야합니다 (즉 빨간색이 다음 순서인가 확인하는 것입니다). 맞았다면 리스트에서 숫자를 제외하고 아니라면 게임 오버 입니다!

```blocks

[red v] 수신할 때
만약 <((1 v) 번째 [sequence v] 항목) = [1]> 라면
   (1 v) 번째 항목을 [sequence v] 에서 삭제하기
아니면
   [Game over!] 을(를) (1) 초동안 말하기
   [모두 v] 멈추기
end
```

+ 또한 리스트가 비면 전체 순서가 맞았다는 뜻이니 빛이 반짝거리게 만들어 줍시다. 이 코드를 캐릭터의 `깃발을 눌렀을때` {.blockevents} 스크립트의 맨 마지막에 넣어주세요:

```blocks
<([sequence v] 의 크기) = [0]> 까지 기다리기
[won v] 방송하고 기다리기
```

+ 스테이지를 클릭하고 이 코드를 넣어서 플레이어가 승리했다면 배경 색이 바뀌도록 만드세요:

```blocks

[won v] 수신할 때
[drum machine v] 소리내기
(50) 번 반복하기
   [색깔 v] 효과를 (25) 만큼 바꾸기
   (0.1) 초 기다리기
end
그래픽 효과 지우기
```

## 도전과제: 버튼 4개 만들기 {.challenge}
위 과정을 파란색, 녹색, 노란색 버튼에 적용하여 버튼 네 가지를 다 만드세요. 각 버튼마다 어떤 코드가 바뀌어야 하고 어떤 코드를 그대로 둘 것인가요?

또한 버튼을 눌렀을 때 소리가 나도록 만들어 볼 수도 있습니다.

꼭 코드를 확인하는 걸 잊지 마세요! 5개 색의 순서를 기억할 수 있나요? 순서가 매번 다른 가요?

## 프로젝트를 저장하세요 { .save }

# 3 단계: 여러 단계의 난이도 { .activity .new-page }

지금까진 색깔의 순서를 5번만 기억하면 됬지만 이제 순서가 늘어나도록 게임을 개선해봅시다.

## 단계별 체크리스트 { .check }

+ 새 변수 를 만들고 `score` {.blockdata}라고 이름지으세요.

	![screenshot](colour-score.png)

+ `score` {.blockdata} 변수는 플레이어가 기억해야할 색의 순서의 길이를 정하는데 사용할것입니다. 점수(와 순서 길이) 를 3으로 시작하기 위해 이 코드를 캐릭터의 `깃발을 눌렀을때` {.blockevents} 코드 맨 앞에 넣으세요:

```blocks
[score v] 에 [3] 저장하기
```

+ 이제 매번 5개의 색깔 순서를 만드는 대신 `score` {.blockdata} 변수가 순서의 길이를 정하게 만듭시다. 캐릭터가 순서의 길이를 정하는데 사용하는 `반복하기` {.blockcontrol} 루프를 이렇게 바꿔주세요:

```blocks
(score) 번 반복하기
end
```

+ 순서를 전부 맞췄다면 점수에 1을 더해 순서의 길이를 늘려야 합니다.

```blocks
[score v] 을(를) (1) 만큼 바꾸기
```

+ 마지막으로 `무한반복하기` {.blockcontrol} 루프로 코드를 감싸서 순서를 만들게 해서 매번 새 순서가 만들어지게 하세요. 캐릭터의 코드는 이렇게 되야 합니다:

```blocks

깃발 클릭했을 때
[score v] 에 [3] 저장하기
무한 반복하기
   (모두 v) 번째 항목을 [sequence v] 에서 삭제하기
   (score) 번 반복하기
      ((1) 부터 (4) 사이의 난수)에 [sequence v] 추가하기
      모양을 ((last v) 번째 [sequence v] 항목) (으)로 바꾸기
      (1) 초 기다리기
   end
   <([sequence v] 의 크기) = [0]> 까지 기다리기
   [won v] 방송하고 기다리기
   [score v] 을(를) (1) 만큼 바꾸기
end
```

+ 친구들에게 게임을 시험해 보게 하세요. 게임을 시작하기 전에 `sequence` {.blockdata} 리스트를 안보이게 해놓는 걸 잊지 마세요!

## 프로젝트를 저장하세요 { .save }

# 4 단계: 최고 득점 { .activity }

최고득점을 저장해서 친구들과 경쟁할 수 있게 만듭시다.

## 단계별 체크리스트 { .check }

+ 프로젝트에 2개의 새 변수, `high score` {.blockdata} 와 `name` {.blockdata}을 더하세요.

+ 게임이 끝날 때 현재 플레이어의 점수가 최고 득점보다 높은 지 확인해야 합니다. 더 높다면 이 점수를 최고득점으로 기록하고 플레이어의 이름을 같이 저장해야 합니다. 빨간색 버튼의 코드는 이제 이렇게 되야 합니다:

```blocks

[red v] 수신할 때
만약 <((1 v) 번째 [sequence v] 항목) = [1]> 라면
   (1 v) 번째 항목을 [sequence v] 에서 삭제하기
아니면
   [Game over!] 을(를) (1) 초동안 말하기
   만약 <(score) > (high score)> 라면
      [high score v] 에 (score) 저장하기
      [High score! What is your name?] 묻고 기다리기
      [name v] 에 (대답) 저장하기
   end
   [모두 v] 멈추기
end
	```

+ 이 코드를 다른 3개의 버튼 들에도 더해야 합니다! 네 가지 버튼의 'Game over'가 전부 같다는 걸 보셨 나요?

	![screenshot](colour-same.png)

+ 만약 소리를 넣는 다던지 'Game over!' 메시지를 바꾸기 위해서 코드를 바꿔야한다면 4번이나 바꿔야 합니다! 그러긴 귀찮고 시간낭비가 될 수 있죠.

	대신 직접 블록을 만들어서 프로젝트에 다시 쓸 수 있습니다! 그러려면 `추가 블록` {.blockmoreblocks}에 들어가서 `블록 만들기`를 클릭하고 'Game over'라고 이름지으세요.

	![screenshot](colour-more.png)

+ 빨간색 버튼의 `아니면` {.blockcontrol} 블록에서 이 코드를 새 블록에 넣으세요:

	![screenshot](colour-make-block.png)

+ 이제 `Game over` {.blockmoreblocks} 라는 새 _함수_ 를 만들어서 어디에든 사용할 수 있게 됬습니다. `Game over` {.blockmoreblocks} 블록을 각 4 버튼의 스크립트에 드래그 해 넣으세요.

	![screenshot](colour-use-block.png)

+ 이제 버튼을 잘못 눌렀을때의 음향 효과를 더하세요. 이 코드는 `Game over` {.blockmoreblocks} 블록에 _단 한번_ 만 넣으면 됩니다!

	![screenshot](colour-cough.png)

## 도전과제: 블록 더 만들기 {.challenge}
4개의 버튼에 모두 사용되는 똑같은 코드가 더 있는 걸 보셨 나요?

![screenshot](colour-more-blocks.png)

모든 버튼에서 사용될 다른 추가 블록을 만들 수 있겠 나요?

## 프로젝트를 저장하세요 { .save }

## 도전과제: 또다른 모양 {.challenge}
게임이 시작할 때 캐릭터가 4개의 색 중 하나를 보여주고 플레이어가 순서를 입력할 때 언제나 마지막 색깔의 모양을 보여주는 걸 보셨 나요?

게임이 시작할 때와 플레이어가 순서를 입력할 때 보여줄 흰색 모양을 캐릭터에 더할 수 있겠 나요?

![screenshot](colour-white.png)

## 프로젝트를 저장하세요 { .save }

## 도전과제: 난이도 {.challenge}
플레이어가 '쉬움'(빨간색과 파란색 드럼만 사용하는) 과 '보통' (4개 드럼을 전부 사용하는) 난이도 사이에서 고를 수 있게 만들 수 있나요?

또한 5번째 드럼을 사용하게 하는 '어려움' 난이도도 추가할 수 있습니다!

## 프로젝트를 저장하세요 { .save }
