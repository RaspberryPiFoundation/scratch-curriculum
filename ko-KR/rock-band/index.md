---
제목: 락 밴드
난이도: Scratch 1
언어: ko-KR
stylesheet: scratch
embeds: "*.png"
materials: ["Club Leader Resources/*"]
...

# 소개 { .intro }

이 프로젝트에선 나만의 악기를 코드 하는 방법을 배울 것입니다!

<div class="scratch-preview">
  <iframe allowtransparency="true" width="485" height="402" src="http://scratch.mit.edu/projects/embed/26741186/?autostart=false" frameborder="0"></iframe>
  <img src="band-final.png">
</div>

# 1 단계: 스프라이트 { .activity }

무언갈 움직이게 하려면 움직일 '무언가'가 필요하겠죠. 스크래치에선 이 '무엇'을 __스프라이트__라고 부릅니다.

## 단계별 체크리스트 { .check }

+ 먼저 스크래치 에디터를 여세요. 스크래치 에디터는 <a href="http://jumpto.cc/scratch-new">jumpto.cc/scratch-new</a>에서 온라인으로 사용할 수 있고 이렇게 생겼습니다:

	![screenshot](band-scratch.png)

+ 고양이 스프라이트는 스크래치의 마스코트입니다. 지금은 필요 없으니 오른쪽 클릭을 한 후 '삭제' 를 눌러서 지워버리죠.

	![screenshot](band-delete.png)

+ 다음으로 '저장소에서 스프라이트 선택'을 눌러서 스크래치에 있는 모든 스프라이트 리스트를 열어 봅시다.

	![screenshot](band-sprite-library.png)

+ 드럼 스프라이트가 보일 때까지 스크롤을 내린 후 드럼을 클릭하고 '확인'을 눌러서 프로젝트에 더해주세요.

	![screenshot](band-sprite-drum.png)

+ '축소'아이콘을 누른 후 드럼을 몇 번 눌러서 좀 작게 만들어 주세요.

	![screenshot](band-shrink.png)

## 프로젝트를 저장하세요 { .save }

'파일'을 클릭 한 후 '저장하기'를 눌러서 프로젝트를 저장해주세요.
그 후 파일 이름을 Band로 저장해주세요.

![screenshot](band-save.png)
![screenshot](band-save1.png)


# 2 단계: 스테이지 { .activity }

__스테이지__는 프로젝트가 살아나는 왼쪽의 공간입니다. 진짜 스테이지처럼 공연장이라고 생각해주세요! 

## 단계별 체크리스트 { .check }

+ 지금 스테이지는 텅 비었고 재미 없어 보입니다! '저장소에서 배경 선택'을 눌러서 배경을 더해줍시다.

	![screenshot](band-stage-choose.png)

+ 목록에서 '실내' 를 눌러 주시고 스테이지 배경을 고른 후 '확인'을 눌러주세요. 

	![screenshot](band-backdrop.png)

+ 스테이지는 이런 모습이 됩니다:

	![screenshot](band-stage.png)

# 3 단계: 드럼 만들기 { .activity }

드럼을 치면 소리가 나도록 코드 해봅시다.

## 단계별 체크리스트 { .check }

+ 코드 블록은 '스크립트'탭에서 찾을 수 있고 색으로 분류 되어 있습니다!

	드럼 스프라이트를 클릭 하고 이 두 블록을 오른쪽의 코드 공간으로 드래그 해 주세요. 블록들이 연결 되 있는지 확인하세요 (레고 처럼요):

	![screenshot](band-code.png)

+ 드럼을 클릭해서 작동하는지 확인해보세요!

+ 또한 새 모양을 만들어서 드럼을 클릭했을 때의 모양을 바꿀 수도 있습니다. '모양' 탭을 누르면 드럼 이미지가 보일 것입니다.

	![screenshot](band-drum-costume.png)

+ 드럼 모양에 오른쪽 클릭 한 후 '복제'를 클릭해서 모양을 하나 더 만들어주세요.

	![screenshot](band-drum-duplicate.png)

+ 새 모양('drum2' 라고 이름 지어졌습니다)을 클릭 한 후 선 도구를 사용해서 드럼에서 소리가 나는 것처럼 만드세요.

	![screenshot](band-drum-hit.png)

+ 드럼 모양들의 지금 이름은 별로 의미가 없어. 테스트 박스에 두 드럼 모양들을 'not hit'과 'hit'으로 새로 이름 지어주세요.

	![screenshot](band-drum-name.png)

+ 이제 두가지 드럼 모양이 생겼으니 어느 때 어느 모양이 보일지 선택할 수 있습니다! 이 두 블록들을 드럼의 코드에 더해 넣어 주세요:

	![screenshot](band-looks.png)

	모양을 바꾸는 코드 블록은 '형태' {.blocklooks} 란에 있습니다.

+ 드럼을 다시 쳐 보세요. 드럼을 클릭하면 이제 마치 드럼을 두드린 것처럼 보일 것입니다!

## 프로젝트를 저장하세요 { .save }

##도전과제: 드럼 개선하기 { .challenge }

+ 드럼을 클릭했을 때 나는 소리를 바꿀 수 있나요?

![screenshot](band-drum-sound.png)

+ 또한 드럼이 스페이스 바를 눌러도 소리가 날 수 있게 할 수 있나요? 이 '이벤트' {.blockevents} 블록을 써야 합니다:

```blocks

[스페이스 v] 키 눌릴 때
```

이미 있는 코드는 오른쪽 클릭 한 후 '복제'를 눌러서 복제할 수 있습니다.

![screenshot](band-duplicate-code.png)

## 프로젝트를 저장하세요 { .save }

# 4 단계: 가수 만들기 { .activity .new-page }

밴드에 노래를 부를 가수를 만들어 줍시다!

## 단계별 체크리스트 { .check }

+ 스테이지에 가수와 마이크 스프라이트를 더해주세요.

	![screenshot](band-singer-mic.png)

+ 이 가수가 노래를 부를 수 있게 만들려면 스프라이트에 소리를 더해야 합니다. 가수를 선택하고 '소리' 탭을 누르신 후 '저장소에서 소리 선택'을 클릭하세요.

	![screenshot](band-import-sound.png)

+ 왼쪽의 '보컬'란을 선택하면 스프라이트에 알맞은 소리를 선택할 수 있을 것입니다.

	![screenshot](band-choose-sound.png)

+ 이제 소리를 더했으니 가수 에게 이 코드를 넣어주세요:

```blocks

이 스프라이트를 클릭했을 때
[singer1 v] 끝까지 재생하기
```

+ 가수를 클릭했을 때 노래를 부르는가 확인 해 주세요.

## 프로젝트를 저장해주세요 { .save }

##도전과제: 가수의 모양 바꾸기 { .challenge }
가수를 클릭했을 때 노래를 부르는 듯한 모양으로 바꿀 수 있나요? 도움이 필요하다면 위의 드럼 만드는 방법을 참조하세요.

![screenshot](band-singer-final.png)

이 새로운 코드가 작동하는지 꼭 확인하세요!

## 프로젝트 저장하기 { .save }

##도전과제: 나만의 밴드 만들기 { .challenge }
지금까지 배운 기술들을 활용해 나만의 밴드를 만들어 봅시다! 어떤 악기라도 만들 수 있지만 활용 가능한 소리와 악기 스프라이트를 보고 잘 생각해 보세요.

![screenshot](band-ideas.png)

말도 안되는 악기라도 괜찮습니다. 예를 들자면 머핀으로 만든 피아노 라던지요!

![screenshot](band-piano.png)

저장소의 스프라이트를 사용해도 되지만 직접 스프라이트를 그려도 좋습니다.

![screenshot](band-draw.png)

마이크가 있다면 직접 소리를 녹음하거나 웹캠으로 악기가 쳐지게 만들 수 잇습니다!

![screenshot](band-io.png)

## 프로젝트를 저장하세요 { .save }
