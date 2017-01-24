---
title: 우주에서 길을 잃다 — 클럽 리더를 위한 노트
language: ko-KR
embeds: "*.png"
... 

#소개:
이 프로젝트에서 아이들은 코드 블록들을 합쳐 간단한 애니메이션을 만드는 방법을 배울 것입니다.

#소재
이 프로젝트에는 Scratch 2 가 사용됩니다. Scratch 2 는 [jumpto.cc/scratch-on](http://jumpto.cc/scratch-on) 에서 온라인으로 사용하거나 [jumpto.cc/scratch-off](http://jumpto.cc/scratch-off) 에서 다운받아 오프라인에서 사용할 수도 있습니다.

이 프로젝트의 완성본은 <a href="http://scratch.mit.edu/projects/26818098/#editor">online</a> 에서 보거나  이 프로젝트의 'Download Project Materials' 링크를 클릭해서 다운로드 할 수 있으며 다음을 포함하고 있습니다:

+ LostInSpace.sb2

또한 이 프로젝트에 필요한 외부소재가 미리 받아져 있는 버전도 사용할 수 있으며 다음 링크에서 사용 하거나 [jumpto.cc/space-resources](http://jumpto.cc/space-resources), downloadable project materials에서 받을 수 있으며 다음을 포함하고 있습니다:

+ LostInSpaceResources.sb2 

#배움 목표
+ 루프:
	+ `반복하기` {.blockcontrol} 루프;
	+ `무한반복하기` {.blockcontrol} 루프.

#도전과제
+ "애니메이션 개선하기" - 프로그램 안의 숫자 바꿔 보기;
+ "자신만의 애니메이션 만들기" - 배운 것을 응용해 새 애니메이션 만들기.

#자주 묻는 질문
+ 아이들이 스프라이트의 위치, 크기와 다른 효과들을 시작할 때 리셋 해야 된다는 걸 다시 생각나게 해줘야 할지 모릅니다. 다음 블록을 애니메이션의 시작에 더해주면 쉽게 가능합니다:

```blocks
	go to x:(0) y:(0)
```

```blocks
	set size to (100)%
```

```blocks
	clear graphic effects
```

+ 'spacship' 스프라이트는 90도 시계방향으로 돌리지 않으면 옆으로 움직일것입니다. 우주선을 돌리는 건 프로젝트의 일부로 나오지만 우주선 대신 다른 스프라이트를 사용해서 문제가 생겼다면 다음을 참조하세요:

	![screenshot](space-rotate.png)
