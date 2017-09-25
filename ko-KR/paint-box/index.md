---
제목: 페인트 박스 
난이도: Scratch 1
언어: ko-KR
stylesheet: scratch
embeds: "*.png"
materials: ["Club Leader Resources/*","Project Resources/*"]
...

# 소개 { .intro }

이 프로젝트에선 페인트 프로그램을 만들어 볼 것입니다!

<div class="scratch-preview">
  <iframe allowtransparency="true" width="485" height="402" src="http://scratch.mit.edu/projects/embed/63473366/?autostart=false" frameborder="0"></iframe>
  <img src="paint-final.png">
</div>

# 1 단계: 연필 만들기 { .activity }

스테이지에 그림을 그릴 수 있는 연필을 만드는 걸로 시작합시다.

## 단계별 체크리스트 { .check }

+ 새 스크래치 프로젝트를 만든 후 고양이 스프라이트를 지워서 빈 프로젝트를 만드세요. 온라인 스크래치 에디터는 <a href="http://jumpto.cc/scratch-new">jumpto.cc/scratch-new</a> 에서 사용할 수 있습니다.

+ 연필 스프라이트를 프로젝트에 넣어주세요.

	![screenshot](paint-pencil.png) 

+ '모양'탭을 클릭 한 후 'pencil-b' 모양은 지워주세요.

	![screenshot](paint-pencil-delete.png) 

+ 남은 모양의 이름을 'pencil-blue' 로 고쳐주고 '색칠하기' 도구로 파란색으로 만들어 주세요.

	![screenshot](paint-pencil-blue.png) 

+ 마우스를 사용해서 그림을 그릴 거니 연필이 마우스를 `무한반복하기` {.blockcontrol}로 따라가야 할 것입니다. 연필 스프라이트에 이 코드를 더해주세요:

```blocks

깃발 클릭했을 때
무한 반복하기
   [mouse pointer v] 위치로 이동하기
end
```

+ 깃발을 클릭해서 마우스를 스테이지 위에서 왔다갔다하게 해보세요. 예상한대로 작동하는 가요?

+ 마우스 포인터를 따라가는게 연필의 심이 아니라 중간 부분이란 걸 보셨 나요?

	![screenshot](paint-center.png)

	이걸 고치려면 연필 스프라이트의 'pencil-blue' 모양으로 가서 '모양 중심 설정'을 클릭 해주세요.

	![screenshot](paint-center-icon.png)

+ 모양에 십자선이 나타날 것입니다. 마우스의 심지 바로 아래부분에 클릭해서 모양의 중심으로 잡아주세요.

	![screenshot](paint-pencil-center.png)

+ '스크립트' 탭을 누르고 연필을 다시 시험해보세요. 방금보다 나은가요?

+ 이제 연필이 `만약` {.blockcontrol} 마우스가 클릭 된 상태라면 그리도록 만듭시다. 연필 스프라이트에 이 코드를 넣어주세요:

	![screenshot](paint-pencil-draw-code.png)	

+ 코드를 다시 시험해보세요. 이번엔 마우스를 클릭해서 움직여보세요. 연필로 그림을 그릴 수 있나요?

	![screenshot](paint-draw.png)

## 프로젝트를 저장해주세요 { .save }

# 2 단계: 색연필 { .activity }

다른 색의 연필을 더해서 색을 고를 수 있게 해봅시다!

## 단계별 체크리스트 { .check }

+ 연필 스프라이트를 누르고 '모양'탭으로 간 후 'pencil-blue'모양을 복제해 주세요.

	![screenshot](paint-blue-duplicate.png)

+ 새 모양의 이름을 'pencil-green'으로 녹색으로 칠해주세요.

	![screenshot](paint-pencil-green.png)

+ 파란색과 녹색 연필 사이에서 고를 때 사용할 두개의 새로운 스프라이트를 만들어 주세요.

	![screenshot](paint-selectors.png)

+ 녹색 선택 아이콘을 클릭하면 연필 스프라이트에 메시지가 `방송` {.blockevents} 되어서 모양과 색깔을 바꾸도록 해야합니다.

	그러려면 먼저 녹색 선택 아이콘에 이 코드를 더해주세요:

```blocks

이 스프라이트를 클릭했을 때
[green v] 방송하기
```

	`방송` {.blockevents} 블록을 만들려면 아래쪽 화살표를 누른 후  '새 메시지...'를 골라주세요.

	![screenshot](paint-broadcast.png)

	이제 새 메시지에 'green'이라고 적어줍시다.

	![screenshot](paint-green-message.png)

+ 다음으로 연필 스프라이트가 메시지를 받으면 무엇을 해야하는지 정해줘야 합니다. 연필 스프라이트에 이 코드를 더해주세요:

```blocks

[green v] 수신할 때
모양을 [pencil-green v] (으)로 바꾸기
펜 색깔을 [#00ff00] (으)로 정하기
```

	연필 색을 녹색으로 만들려면 `펜 색깔을 ... 으로 정하기` {.blockpen} 블록에서 색깔 박스를 클릭하고, 녹색 선택 아이콘을 눌러서 연필 색을 녹색으로 맞춰줍니다.

+ 파란색 선택 아이콘 스프라이트에 이 코드를 더해 파란색 연필도 선택 가능하게 해줍시다:

```blocks

이 스프라이트를 클릭했을 때
[blue v] 방송하기
```

...그리고 이 코드를 연필 스프라이트에 더해주세요:

```blocks

[blue v] 수신할 때
모양을 [pencil-blue v] (으)로 바꾸기
펜 색깔을 [#0000ff] (으)로 정하기
```

+ 마지막으로 프로젝트가 시작 됬을 땐 어떤 연필 스프라이트와 모양, 색깔을 사용해야 되는지를 정하고 스크린을 깔끔하게 지우게 만들어줍시다. 이 코드를 연필의 `깃발을 클릭했을 때` {.blockevents} 코드의 시작에 (`무한반복하기` {.blockcontrol} 루프 앞에) 넣어줍시다:

```blocks
지우기
모양을 [blue-pencil v] (으)로 바꾸기
펜 색깔을 [#0000ff] (으)로 정하기
```

	원하신다면 다른 색으로 시작 하셔도 됩니다!

+ 프로젝트를 시험해보세요. 파란색과 녹색 연필 사이에서 선택이 가능한가요?

	![screenshot](paint-pens-test.png)

## 프로젝트를 저장하세요 { .save }

# 3 단계: 실수 했을 때 { .activity .new-page }

누구든지 실수할 수 있습니다. 그러니 '다 지우기' 버튼과 지우개를 프로젝트에 더해봅시다!

## Activity Checklist { .check }

+ 스테이지를 깔끔히 지워줄 버튼을 더해줍시다. 'X-block' 스프라이트를 스테이지에 더해주고 빨간색으로 칠해주세요.

	![screenshot](paint-x.png)

+ 이 버튼을 클릭하면 스테이지를 지워줄 코드를 더해줍시다.

```blocks

이 스프라이트를 클릭했을 때
지우기
```

	스테이지를 지우는데 메시지를 보낼 필요가 없다는 점에 주의하세요. 어떤 스프라이트도 할 수 있으니까요!

+ 또한 지우개를 만들 수 있습니다. 클럽 리더에게 'Resources' 폴더를 받았다면 '모양 파일 업로드하기'를 누르고 'eraser.svg' 이미지를 선택해주세요.

	![screenshot](paint-eraser-costume.png)
	
	eraser.svg 이미지가 없다면 그냥 흰색 연필을 새로 만들어 주세요!

+ 또한 지우개도 새로운 선택 스프라이트로 더해줘야 합니다. 이제 스테이지는 이렇게 생겨야 합니다: 

	![screenshot](paint-eraser-stage.png)

+ 이제 지우개 선택 스프라이트에 이 코드를 넣어서 연필에서 지우개로 바꾸도록 만들어줍시다.

```blocks

이 스프라이트를 클릭했을 때
[eraser v] 방송하기
```

+ 연필이 이 메시지를 받으면 연필 모양을 지우개로 바꾸고 연필 색을 스테이지 색과 같게 만들어서 지우개를 만들 수 있습니다!

```blocks

[eraser v] 수신할 때
모양을 [eraser v] (으)로 바꾸기
펜 색깔을 [#FFFFFF] (으)로 정하기
```

+ 프로젝트를 시험해서 스테이지를 다 지우거나 지우개로 지울 수 있는지 확인해주세요.

	![screenshot](paint-erase-test.png)

+ 연필엔 또 한가지의 문제가 있습니다 - 스테이지의 어디에도, 심지어 선택 아이콘 옆에도, 그릴 수 있다는 점입니다!

	![screenshot](paint-draw-problem.png)

	이 문제를 고치려면 연필이 마우스가 클릭 됬을 때나 _또는_ 마우스의 y좌표가 -110 (`mouse y`{.blocksensing}`> -120` {.blockoperators})보다 클 때 그려지게 만들어야 합니다. 연필의 `만약` {.blockcontrol} 코드를 이렇게 바꾸세요:

	![screenshot](pencil-gt-code.png)

+ 프로젝트를 시험해보세요. 이제 선택 아이콘 가까이엔 그릴 수 없을 것입니다.

	![screenshot](paint-fixed.png)

## 프로젝트를 저장하세요 { .save }

# 4 단계: 연필 굵기 바꾸기 { .activity .new-page }

사용자가 여러가지 크기의 연필을 사용할 수 있게 만들어 봅시다.

## 단계별 체크리스트 { .check }

+ 첫번째로 'width'라고 이름 지은 새 변수를 더해주세요. 어떻게 하는지 모르겠다면 '풍선' 프로젝트를 돌아보는게 도움이 될 것입니다.

+ 이 코드를 연필의 코드의 `무한반복하기` {.blockcontrol} 루프 __안쪽에__ 넣어주세요:

```blocks
펜 굵기를 (width) (으)로 정하기
```

	이제 연필의 굵기는 `width` 변수의 값으로 맞춰질 것입니다.

+ 이 변수에 있는 숫자는 스테이지 위의 벼수 디스플레이에 오른쪽 클릭한 후 '슬라이더'를 골라서 바꿀 수 있습니다.

	![screenshot](paint-slider.png)

	변수 아래의 슬라이더를 드래그 해서 변수의 값을 바꿀 수 있습니다.

	![screenshot](paint-slider-change.png)

+ 프로젝트를 시험해서 연필 굵기를 바꿀 수 있는지 확인해보세요.

	![screenshot](paint-width-test.png)

	원하신다면 'width'의 최소값과 최대값을 정해 둘 수 있습니다. 그러려면 변수 디스플레이를 다시 오른쪽 클릭 하신 후 '슬라이더 최대값과 최소값 설정하기'를 눌러주세요'. 최소값과 최대값을 1에서 20같이 좀더 현실적 값으로 바꿔주세요.

	![screenshot](paint-slider-max.png)

	만족할때 까지 'width'변수를 바꿔주세요.

## 프로젝트를 저장하세요 { .save }

## 도전과제: 바로가기 { .challenge }
키보드로 선택 바로가기를 만들 수 있나요? 예를 들자면:

+ b = 파란색 연필로 바꾸기
+ g = 녹색 연필로 바꾸기
+ e = 지우개로 바꾸기
+ c = 화면 전체 지우기

또한 연필 굵기를 화살표로 바꿀 수 있게도 만들 수 있습니다!

## 프로젝트를 저장해주세요 { .save }

## 도전과제: 더 많은 연필 { .challenge }
빨간색, 노란색과 검은색 연필을 프로그램에 더할 수 있겠 나요? 필요한 이미지들은 모두 'Resources' 폴더에서 찾으실 수 있습니다. 이 연필 들에도 키보드 바로가기를 더해주는 걸 잊지 마세요!

이제 이 연필들로 그림을 그려볼 수 있겠 나요?

![screenshot](paint-final.png)
