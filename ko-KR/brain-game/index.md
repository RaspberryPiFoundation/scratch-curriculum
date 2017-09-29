---
제목: 뇌 게임
난이도: Scratch 2
언어: ko-KR
stylesheet: scratch
embeds: "*.png"
materials: ["Club Leader Resources/*"]
...

# 소개 { .intro }

이 프로젝트에선 30초 안에 최대한 많은 답을 맞춰야 하는 시간 제한 퀴즈 게임을 만들 것입니다.

<div class="scratch-preview">
  <iframe allowtransparency="true" width="485" height="402" src="http://scratch.mit.edu/projects/embed/42225768/?autostart=false" frameborder="0"></iframe>
  <img src="brain-final.png">
</div>

# 1 단계: 질문 만들기 { .activity }

플레이어가 대답해야 할 질문들을 만드는 것으로 시작합시다.

## 단계별 체크포인트 { .check }

+ 새 스크래치 프로젝트를 시작 한 후 고양이 스프라이트를 지워서 빈 프로젝트를 만드세요. 온라인 스크래치 에디터는 <a href="http://jumpto.cc/scratch-new">jumpto.cc/scratch-new</a> 에서 사용할 수 있습니다.

+ 게임에 사용할 캐릭터와 배경을 정하세요. 좋아하는 대로 고르면 됩니다! 예를 들자면:

	![screenshot](brain-setting.png)	

+ `number 1` {.blockdata} 과 `number 2` {.blockdata} 라는 두개의 변수를 만드세요. 이 변수들은 곱해질 두 번호들을 저장할 것입니다.

	![screenshot](brain-variables.png)

+ 캐릭터에 코드를 더해 이 변수들을 `2부터 12 사이의 난수` {.blockoperators} 로 만들 것입니다.

```blocks

깃발 클릭했을 때
[number 1 v] 에 ((2) 부터 (12) 사이의 난수) 저장하기
[number 2 v] 에 ((2) 부터 (12) 사이의 난수) 저장하기
```

+ 그 후 플레이어에게 답을 구하여 맞는지 틀린 지 알려줄 수 있습니다.

```blocks

깃발 클릭했을 때
[number 1 v] 에 ((2) 부터 (12) 사이의 난수) 저장하기
[number 2 v] 에 ((2) 부터 (12) 사이의 난수) 저장하기
((number 1) 와 ([x] 와 (number 2) 결합하기) 결합하기) 묻고 기다리기
만약 <(대답) = ((number 1) * (number 2))> 라면
   [yes! :)] 을(를) (2) 초동안 말하기
아니면
   [nope :(] 을(를) (2) 초동안 말하기
end
```

+ 프로젝트르 시험해서 한개의 답을 바르게, 한 개는 틀리게 대답해보세요.

+ 이 코드 주위에 `무한 반복하기` {.blockcontrol} 루프를 더해서 플레이어가 계속해서 질문을 받도록 만드세요.

+ 스테이지에 `time` {.blockdata}이란 변수를 사용해 타이머를 만드세요. 도움이 필요하다면 '풍선'프로젝트의 6단계에 타이머를 만드는 방법이 들어있습니다!

+ 프로젝트를 다시 시험해보세요 - 시간이 다 다를 때까지 질문을 물어봐야 할 것입니다.

## 프로젝트를 저장하세요 { .save }

##도전과제: 모양 바꾸기 {.challenge}
플레이어의 답에 따라 캐릭터의 모양을 바꾸게 할 수 있나요?

![screenshot](brain-costume.png)

## 도전과제: 점수 더하기 {.challenge}
게임에 점수를 더할 수 있나요? 맞는 답 마다 1점씩 더하면 됩니다. 조금 심술궂다면 질문이 틀릴 때마다 점수를 0으로 리셋 해버릴 수도 있습니다!

## 프로젝트를 저장하세요 { .save }

# 2 단계: 게임 여러 번 하기 { .activity .new-page}

게임에 'play' 버튼을 더해서 여러 번 시도해 볼 수 있도록 만듭시다.

## 단계별 체크리스트 { .check }

+ 플레이어가 클릭해서 새 게임을 시작할 수 있는 'Play' 버튼 스프라이트를 만드세요. 자신이 직접 그리거나 스크래치 저장소에서의 스프라이트를 수정해서 만들 수 있습니다.

	![screenshot](brain-play.png)

+ 이 코드를 버튼에 넣어주세요

```blocks

깃발 클릭했을 때
보이기

이 스프라이트를 클릭했을 때
숨기기
[start v] 방송하기
```

	이 코드는 프로젝트가 시작 됬을 때 'play' 버튼을 보여줍니다. 버튼을 클릭하면 숨겨지고 게임을 시작하라는 메시지를 방송합니다.

+ 캐릭터의 코드를 깃발을 눌렀을 때가 아닌 `start' {.blockevents} 메시지를 받을때 게임이 시작하도록 수정해야 합니다.

	`깃발을 클릭했을 때` {.blockevents} 코드를  `start 을 받았을 때` {.blockevents}로 바꿔 넣으세요.

	![screenshot](brain-start.png)

+ 녹색 깃발을 클릭하고 play 버튼을 클릭해서 시험해보세요. 게임이 버튼을 누를 때 까지 시작하지 않는게 보입니다.

+ 타이머가 게임이 시작 했을 때가 아닌 깃발을 눌렀을 때부터 내려가는게 보이나요? 

	![screenshot](brain-timer-bug.png)

	이 문제를 고칠 수 있겠나요?

+ 스테이지를 클릭해서 `모두 멈추기` {.blockcontrol} 블록을 `end` {.blockevents} 메시지를 받았을 때로 바꾸세요.

	![screenshot](brain-end.png)

+ 이제 버튼에 게임이 끝날 때 마다 다시 보이도록 코드를 넣습니다.

```blocks

[end v] 수신할 때
보이기
```

+ 또한 캐릭터가 게임 끝에 질문을 하는 걸 멈추도록 해야합니다:

```blocks

[end v] 수신할 때
[스프라이트에 있는 다른 스크립트 v] 멈추기
```

+ play버튼을 몇 번 게임을 하면서 시험해보세요. 각 게임의 끝에 play버튼이 다시 나타나는 걸 볼 수 있습니다. 시험하는 걸 더 간단하게 하려면 각 게임 시간을 줄여서 더 빠르게 시험할 수 있습니다.

```blocks
[time v] 에 [10] 저장하기
```

+ 또한 마우스를 play버튼 위에 올려놓으면 어떻게 보이는지도 바꿀 수 있습니다.

```blocks

깃발 클릭했을 때
보이기
무한 반복하기
   만약 <[마우스의 포인터 v] 에 닿기?> 라면
      [어안 렌즈 v] 효과 (30) 로 정하기
   아니면
      [어안 렌즈 v] 효과 (0) 로 정하기
   end
end
```

	![screenshot](brain-fisheye.png)

## 프로젝트를 저장하세요 { .save }

## 도전과제: 시작 스크린 {.challenge}
게임의 시작 스크린이 될 다른 배경을 더해 넣을 수 있나요?  `start을(를) 받았을 때` {.blockevents}블록 과 `end을(를) 받았을 때` {.blockevents}블록을 사용해서 배경을 바꾸게 할 수 있습니다.

또한 다음 블록을 이용해 캐릭터와 타이머도 보였다 안보이게 할 수 있습니다:

```blocks
[time v] 변수 보이기
```
```blocks
변수 [time v] 숨기기
```

![screenshot](brain-startscreen.png)

## 프로젝트를 저장하세요 { .save }

# 3 단계: 그래픽 더하기 { .activity .new-page}

캐릭터가 `yes! :)` 와 `nope :(` 만 얘기하게 하지 말고 플레이어가 어떻게 하고 있는지 보여줄 그래픽을 더해줍시다.

+ 'tick' 과 'cross' 라는 모양이 포함된 'Result' 라는 스프라이트를 만듭시다.

	![screenshot](brain-result.png)

+ 캐릭터의 코드를 바꿔서 플레이어에게 답을 알려주는 대신 `correct` {.blockevents} 와 `wrong` {.blockevents} 메시지를 방송하게 만듭시다.

	![screenshot](brain-broadcast-answer.png)

+ 이제 이 메시지를 사용해서 'tick' 이나 'cross' 모양을 보여주게 만들 수 있습니다. 이 코드를 'Result' 스프라이트에 넣어주세요:

	![screenshot](brain-show-answer.png)	

+ 게임을 다시 시험해 보세요. 질문에 대답이 맞을 때 마다 tick이 보이고 틀릴땐 cross가 보일 것입니다!

	![screenshot](brain-test-answer.png)

+ `correct(을)를 받았을 때` {.blockevents} 와 `wrong을(를) 받았을 때` {.blockevents} 의 코드가 거의 비슷하다는 걸 느끼셨나 요? 새로운 기능을 더해 코드를 바꾸기 더 간단하게 만듭시다.

	'Result' 스프라이트에서 `추가블록` {.blockmoreblocks}을 누르고 '블록 만들기'를 클릭하세요. `animate` {.blockmoreblocks}라는 새 기능을 만들어주세요.

	![screenshot](brain-animate-function.png)

+ 이제 애니메이션 코드를 이 새 애니메이션 기능에 넣고 기능을 두 번 사용하기만 하면 됩니다:

	![screenshot](brain-use-function.png)

+ 이제 tick 이나 cross 를 더 짧거나 긴 시간동안 보여주고 싶다면 코드에 단 한가지만 바꾸면 됩니다. 시도해 보세요!

+ 단순히 tick 과 cross를 보여주는 대신 애니메이션 기능을 바꿔서 그래픽이 점점 뚜렷해지게 할 수 있습니다.

```blocks

정의하기 [animate]
[반투명 v] 효과 (100) 로 정하기
보이기
(25) 번 반복하기
   [반투명 v] 효과를 (-4) 만큼 바꾸기
end
숨기기
```

## 프로젝트를 저장하세요 { .save }

## 도전과제: 개선된 애니메이션 {.challenge}
그래픽 애니메이션을 개선할 수 있겠 나요?  tick 과 cross 를 점점 뚜렷해지는 것 뿐만 아니라 점점 흐렸 해지게 코드 할 수도 있습니다. 또는 다른 멋진 효과를 사용해보세요:

![screenshot](brain-effects.png)

## 프로젝트를 저장하세요 { .save }

## 도전과제: 음향효과와 배경음악 {.challenge}
게임에 음악효과와 배경음악을 넣을 수 있나요? 예를 들자면:

+ 플레이어가 답을 맞추거나 틀릴 때 마다 소리 넣기;
+ 타이머에 째깍거리는 소리 넣기;
+ 시간이 다 되면 특정한 소리 나오게 하기;

```blocks
(10 v) 드럼 (0.1) 박자로 연주하기
```

+ 또한 배경음악을 계속해서 루프해서 나오게 만들 수 있습니다 (도움이 필요하다면 '록 밴드' 프로젝트의 4 단계를 돌아보세요). 

## 프로젝트를 저장하세요 { .save }

## 도전과제: 10점까지 경쟁 {.challenge}
게임을 바꿔서 30초 안에 최대한 많은 답을 맞추는게 아닌 최대한 빠르게 10문제를 맞추게 만들 수 있나요?

이렇게 바꾸려면 타이머 코드만을 수정하면 됩니다. 어느 부분을 바꿔야 하는지 알 수 있겠 나요?

```blocks

[start v] 수신할 때
[time v] 에 (30) 저장하기
<(time) = [0]> 까지 반복하기
   (1) 초 기다리기
   [time v] 을(를) (-1) 만큼 바꾸기
end
[end v] 방송하기
```

## 프로젝트를 저장하세요 { .save }

## 도전과제: 도움말 스크린 {.challenge}
도움말 스크린을 넣어서 플레이어에게 게임을 진행하는 방법을 알려줄 수 있나요? 'Instructions'버튼과 또다른 배경이 필요할 것입니다. 

![screenshot](brain-instructions.png)

또한 메인 메뉴로 다시 데려가 줄 'Back' 버튼도 필요할 것입니다.

```blocks
[main menu v] 방송하기
```

## 프로젝트를 저장하세요{ .save }
