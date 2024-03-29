
---

## 목차

[[#1. 작업 레이아웃의 설정과 이해]]

[[#2. 리소스의 이해]]

[[#3. 게임 오브젝트와 컴포넌트]]

[[#4. 게임 오브젝트 배치]]

[[#5. 컴포넌트 수정]]

[[#6. 공굴리기 만들기]]

[[#7. 완성된 씬 저장하기]]

---

## 1. 작업 레이아웃의 설정과 이해

>유니티 엔진이 가진 기본적인 기능과 조작법에 대한 설명.
>
>View는 유니티에서 제작하는 과정을 실행하는 곳으로, 창의 형태를 띄므로 Window라고도 부른다.

### 1. 레이아웃 변경

![[1_1_1.default_layout.png]]

- 처음 프로젝트를 생성하면 위와 같은 레이아웃 화면이 나온다.
- \[Window] - \[Layouts]를 눌러보면 5개의 레이아웃이 있다.
- Default 레이아웃은 Scene View와 Game View를 동시에 볼 수 없어 설정을 2 by 3로 바꿔주자.

![[1_1_2.layouts_setting_change.png]]

![[1_1_3.default_2by3_windows.png]]

- 기본 세팅은 Hierachy와 Project, Inspector 창이 가로로 모여있다.
- Project 창을 Hierarchy 창 아래로 드래그해 아래와 같이 만들어주자.

![[1_1_4.change_2by3_windows.png]]

- 스크립트 작성 시 오류 확인을 위해 Console View를 추가해주자.
	- \[Window] - \[General] - \[Console]
- 위 경로대로 클릭한다면 Console View가 외부 창으로 나올 것이다.
- Game View 옆에 드래그 해서 보기 편하게 만들자.

![[1_1_5.add_console_view.png]]

- 마지막으로 Project View 창을 우클릭한 뒤 One Column Layout으로 바꿔주자.

![[1_1_6.project_view_layout.png]]

- 그러면 최종적으로 아래와 같은 화면이 된다.

![[1_1_7.final_window.png]]

- 다른 View들도 Console View를 추가할 때처럼 해준다면 추가할 수 있다!

### 2. 씬 뷰(Scene View)

- 씬 뷰는 현재 씬에 배치되어 있는 오브젝트들을 보여주고 위치, 각도, 크기 등을 변경할 수 있는 곳이다.
- 아래는 씬 뷰 우측 상단 아이콘에 대한 설명이다.

![[1_2_1.scene_view.png]]

1. 씬에서 보는 방법을 설정하는 부분.
	- 와이어프레임(WireFrame) 등으로 바꿔 버텍스(Vertex, 꼭짓점)와 엣지(Edge, 가장자리 선)만 보이게 할 수 있음.
	- 알파 채널(Alpha Channel)로 바꿔 투명도만 흑백으로 표시하는 기능.
2. 2D/3D로 변경하는 부분.
	- 2D에서는 쓸 일이 없으나, 3D에선 UI를 다룰 캔버스 영역이 2D이므로 전환해야 할 수도 있다.
3. 조명을 키거나 끄는 곳
4. 기즈모 필터링
	- 기즈모(Gizmo)란 게임 제작 시 X, Y, Z축으로 향하는 화살표 혹은 파란 꼭짓점처럼 제작 가이드라인 역할을 하는 아이콘이다.
	- 기즈모를 필터링해 특정 종류의 기즈모만 보이게 할 수 있다.
- 아래는 좌측에 세로로 존재하는 편집 툴에 대한 설명이다. 위에서부터 순서대로 설명하겠다.

 ![[1_2_2.scene_view_edit_tool.png]] ^SceneViewEditTools
 
1. Hand Tool
	- 단축키는 Q.
	- 화면을 드래그하여 움직일 때 사용한다.
2. Move Tool
	- 단축키는 W.
	- 선택한 오브젝트를 X, Y축(3D는 Z까지)으로 이동하는 기능.
	- 화살표의 촉 부분을 클릭하여 드래그하면 움직일 수 있다.
3. Rotate Tool
	- 단축키는 E.
	- 선택한 오브젝트의 각도를 각 축으로 회전하는 기능.
	- 빨간 선이 X, 초록 선이 Y, 파란 선이 Z축(RGB => XYZ)이다.
	- 2D에서는 깊이 다루지 않아 보통 3D에서 Z축 회전을 사용한다.
4. Scale Tool
	- 단축키는 R.
	- 선택한 오브젝트의 크기를 조절하는 기능.
	- 선 끝의 정육면체를 드래그해 각 축의 크기를 조절할 수 있다.
	- 가운데 회색 면을 드래그할 경우 모든 축을 동시에 같은 크기로 조절할 수 있다.
5. Rect Tool
	- 단축키는 T.
	- 선택한 오브젝트의 크기와 위치를 동시에 조절할 수 있다.
	- 2D 게임에서 매우 유용하며, Canvas내 UI 편집에 특화되어있다.
6. 종합
	- 단축키는 Y.
	- 위에 설명한 모든 기능을 동시에 편집할 수 있다.
### 3. 게임 뷰(Game View)

- 씬 뷰에서 편집한 것들이 실제 게임에서 동작하는 것을 보여주는 역할을 한다.

![[1_3_1.game_view.png]]

1. Display
	- 현재 디스플레이 번호.
	- 보통 하나만 사용한다.
2. 해상도
	- 현재 게임 카메라 해상도.
	- 구동되는 기기의 차이나 PC의 경우 유저가 해상도를 변경하는 경우가 있어 여러 해상도로 바꿔 테스트 하는 것이 좋다!
	- 보통 16:9 비율로 1920\*1080 또는 2560\*1440으로 테스트 하는 것이 좋다.
	- 세로의 경우 가로 세로를 반대로 하면 된다.
3. Scale
	- 화면의 배율.
	- 1x가 기본이다.
	- 배율을 수정한다고 해서 실제 게임에 반영되지는 않는다.
	- 테스트 중 작아서 관찰하기 힘든 오브젝트를 볼 때 쓴다.
4. Enter Play Mode
	- 테스트 시 게임 화면을 정하는 용도.
	- Play Focused의 경우 현재 주어진 창에서 그대로 플레이 한다.
	- Play Maximized의 경우 창을 화면 최대로 키워준다.
	- Play Unfocused의 경우 플레이 모드 실행 시 게임 뷰 탭이 자동으로 선택되지 않는다.
### 4. 콘솔 뷰(Console View)

- 스크립트의 오류, 경고 등을 보여주는 창이다.
- 스크립트에서 명령어 Debug.Log( ) 사용 시 괄호 안의 메시지를 콘솔 뷰에서 출력할 수 있다.

 ![[1_4_1.console_view.png]]
 
1. Clear
	- 콘솔 뷰에 표시된 오류, 경고, 로그의 모든 메시지를 지운다. 
2. Collapse
	- 같은 메시지의 경우 합치고, 우측에 겹친 개수를 표시한다.
### 5. 하이어라키 뷰(Hierarchy View)

>사진(하이어라키 내부 모습과 부모, 자식, 검색 표시)

- 유니티 오브젝트 간 상하(부모;Parant, 자식;Child) 관계를 표시한다.
- 현재 씬 내에 있는 오브젝트의 목록을 보거나 상하 관계를 설정할 수 있다.
- 상단의 검색 기능을 통해 이름으로 검색할 수 있다.

### 6. 프로젝트 뷰(Project View)

>사진(프로젝트 내부 모습)

- 게임 내에 존재하는 것이 아닌 프로젝트에 포함된 파일(이미지, 사운드, 스크립트 등)을 보여주는 뷰.
- 프로젝트에 존재할 뿐 씬이나 하이어라키에 배치하지 않는 한 게임 내에 들어가지 않는다.
- 게임을 빌드(최종 결과물 완성)할 경우 사용하지 않은 파일은 완성본에 들어가지 않는다.
- 검색 또한 가능하다.

### 7. 인스펙터 뷰(Inspector View)

>사진(인스펙터 내부 사진진)

- 선택한 오브젝트 또는 리소스의 정보를 보여주고 값을 수정하는 창.
- 제일 많이 보며 선택한 오브젝트에 따라 내용이 달라진다.

### 8. 메뉴 탭

- 뷰는 아니지만, 메뉴의 역할을 간단히 짚고 넘어가자.

 ![[1_8_1.menu.png]]
 
1. File
	- 씬을 열거나 저장한다.
	- 프로젝트 1을 열거나 저장한다.
	- 빌드에 대한 설정을 하거나 빌드한다.
2. Edit
	- 여러 편집 항목이 있다.
	- Project Settings가 항목에 포함되어 있다.
		- 프로젝트 시간, 물리법칙 등 설정 가능.
	- Window의 경우 Preferences 항목이 이 탭에 있다.
		- 스크립트 에디터(Visual Studio, Mono Develop 등)의 설정을 이곳에서 바꿀 수 있다.
3. Assets
	- 에셋 패키지를 새로 만들거나 불러올 수 있다.
4. GameObject
	- 하이어라키 뷰에서 선택된 것을 기준으로 새로운 게임 오브젝트를 선택한 형식으로 새로 만든다.
5. Component
	- 하이어라키 뷰에서 선택된 것을 기준으로 새로운 컴포넌트를 해당 오브젝트에 새로 추가한다.
6. Windows
	- 레이아웃에 선택한 항목의 뷰를 추가하거나 뺄 수 있다.

---

## 2. 리소스의 이해

>게임에서 보통 이미지나 사운드 등 게임에 필요한 파일

### 1. 리소스(에셋) 불러오기

- 리소스를 유니티에선 에셋(Asset)이라고도 부른다.
- 프로젝트 뷰에서 리소스를 관리할 수 있다.
- 프로젝트 뷰 빈 곳에 마우스 우클릭 후 \[Import New Asset]을 눌러 파일을 넣을 수 있다.
- 파일을 드래그 앤 드롭해 추가할 수 있다.
- 해당 파일은 자동으로 프로젝트의 \[Assets] 폴더 내에 복사된다.

### 2. 씬(Scene)

- .unity 확장자를 가진 파일.
- 게임 내에서 씬을 담고 있다.
- 포괄적인 의미를 담고 있다.
	- 스토리가 있는 게임은 스토리를 하나의 장면으로 실행하는 의미로 사용 가능.
	- 스테이지를 하나씩 클리어 하는 게임은 하나의 스테이지를 씬으로 사용 가능.
	- 극단적으로 하나의 씬만 써서 게임을 완성할 수도 있다.
- 별도로 값을 저장하는 스크립트가 없으면 씬을 넘어갈 때마다 스크립트가 가지고 있던 변수 내 값이 사라진다.
	- 별도의 스크립트가 없으면 캐릭터 HP가 50일 때 씬이 넘어가면 변수 선언 값(ex. 100)으로 돌아간다.
	- 변수를 저장하는 것은 게임 제작 파트에서 설명한다.

### 3. 스크립트(Script)

- 게임 내 오브젝트들이 움직이며 게임을 돌아가게 한다.
- 게임 제작에 있어 가장 중요한 부분.
- '\#' 글씨가 적힌 종이 아이콘이나 자바스크립트의 경우 'JS'라고 적힌 아이콘.
	- 스크립트 이름이 GameManager일 경우 톱니바퀴 모양을 띈다.
- 내부에는 C# 코드가 들어있다.

### 4. 프리팹(Prefab)

- 한 오브젝트를 여러 번 쓸 때, 해당 오브젝트를 프리팹에 저장해 복사 가능.
- 하이어라키 뷰에서 프로젝트 뷰로 프리팹을 만들고 싶은 오브젝트를 드래그 앤 드롭할 때 만들어진다.

### 5. 모델(Model)

- 3D 모델 파일.
- .fbx, .obj 등을 확장자로 가진다.
- 3D 작업 프로그램(Blender, 3DMax, Maya 등)에서 작업한 결과물을 활용할 수 있다.

### 6. 스프라이트(Sprite)

>사진(2D 그림 파일)

- 2D 그림.
- 한 장만 쓸 때는 정지된 그림의 역할을 한다.
- 동일한 크기의 연속된 이미지가 있다면 그림 한 장이 애니메이션의 한 프레임 역할로 쓸 수 있다.
	- 아래 애니메이션 스프라이트 만들기에서 자세히 볼 수 있다.
- PNG, JPG 외에도 포토샵에서 지원하는 PSD파일도 사용할 수 있다.
- 스프라이트 에디터에서 그림을 수정하는 기능은 없지만, 유니티에서 사용하기 위한 여러가지 편집 기능이 있다.

#### 애니메이션 스프라이트 만들기

>사진(애니메이션 프레임)

- 여러 장의 그림이 있을 경우 분할해 낱개 그림으로 만들 수 있다.

>사진(Slide 탭 내부부)

- 그림 선택 -> 'Sprite Mode'를 'Multiple'로 변경 -> \[Sprite Editer] 버튼 누르기
	- 적용을 하지 않았다는 창이 뜨면 \[Apply] 버튼을 눌러 적용
- 에디터가 실행되면 상단 \[Slice] 버튼 누르고 Type을 Automatic으로 바꾸기
	- \[Slice] 버튼을 누르면 이미지가 자동으로 분할됨
	- 이미지가 균등한 사이즈가 아니거나 기타 이유로 분할을 실패하면 Type을 'Grid by Cell Size' 또는 'Grid by Cell Count'로 바꾸면 크기, 개수 기준으로 수동 분할 가능.

#### UI 패널 만들기

- 게임 내에 창을 만드는 기능.
- 같은 이미지가 창의 크기가 다름에도 깨지지 않고 확대/축소된다.

>사진(패널 원본 이미지)

- 위 사진의 점선 부분처럼 하나의 이미지를 9등분해 모서리 4개 영역 제외 나머지 부분만 확대/축소하는 기능을 사용하므로 가능.

>사진(패널 크기 여러개)

- 위 그림은 점선 그림을 원본으로 해 확대/축소한 패널이다.
- 이러한 이미지 타입(Image Type)을 'Slide'라 한다.
	- 유니티 내에서 설정하지 않으면 사용불가.
- Slide 타입을 만드는 방법은 다음과 같다.
	- 패널로 만든 오브젝트 선택
	- 스프라이트 에디터를 실행
	- 4 방향 가장자리에 있는 초록색 점을 드래그해 9 등분 한다.
		- 정확히 9 등분 보단 대충 모서리, 가장자리, 가운데를 나누는 느낌으로 하자.
	- 이 상태로 종료하면 \[Apply] 버튼을 누르면 적용된다.
- 패널 오브젝트에서 Slide 타입으로 바꾸는 방법은 이후 UI 파트에서 다루도록 하겠다.

>사진(Slide 분할 완료 사진진)

### 7. 폰트(Font)

- UI에서 텍스트(Text) 사용 시 필요한 리소스.
- 원하는 서체를 가져오면 사용할 수 있다.
- 저작권에 유의하자.
- 사용법은 UI 파트에서 다루겠다.

### 8. 사운드(Sound)

- WAV, MP3 파일 등으로, 배경음(BGM), 효과음 등에 사용한다.
- 유니티 내부 편집은 불가능하지만, 스테레오(Stereo) 또는 모노(Mono)로 변경은 가능하다.
- \[Window] - \[Audio] - \[Audio Mixer] 탭에서 믹싱은 가능하다.

>사진(오디오 믹서)

>사진(오디오 믹서 내부)

### 9. 애니메이션(Animation)과 애니메이터(Animator)

- 애니메이션은 그림 여러 장을 이어 하나의 움직임으로 보이게 만드는 기법이다.
- 게임 내 캐릭터의 움직임이나 컷 신(Cut Scene) 재생에 쓰인다.

>사진(애니메이션 클립 아이콘)

- 위와 같은 애니메이션 클립 파일이 모여 하나의 애니메이션을 이룬다.
- 과거엔 애니메이션 컴포넌트가 따로 있었으나, 현재에는 사용을 추천하지 않는다.
	- 다만, 과거 제작한 프로젝트를 참고하거나 사용할 때를 대비해 Legacy로 남겨두었다. 사용법은 아래와 같다.
		- 사용할 애니메이션 클립을 선택한다.
		- 인스펙터 뷰 우측 상단 메뉴 버튼(세로 점 3개)을 눌러 \[Debug] 탭을 선택한다.
		- Legacy를 체크한다.

>사진(Debug 및 Legacy 사진)

>사진(애니메이터 컨트롤러 아이콘)

- 애니메이터 컨트롤러는 유니티 애니메이터 컴포넌트를 다루기 위한 리소스다.

>사진(애니메이터 뷰)

- 애니메이터 컨트롤러 내용은 애니메이터 뷰에서 편집 가능하다.
- 상태 머신(State Machine)으로 각 클립 간 연결로 직관적인 애니메이션 제어가 가능하다.
- 2D 3D 모두 사용 가능하다.
	- 2D는 스프라이트를 제어한다.
	- 3D는 모델을 제어한다.
### 10. 매테리얼(Material)

>사진(매테리얼 아이콘)

- 게임 내에서 물체(오브젝트)의 재질을 표현하는데 쓰인다.

>사진(매테리얼에 따른 오브젝트의 질감 차이)

- 특정 텍스처(Texture) 그림을 넣어 타일, 벽돌, 나무 바닥 등의 표현도 가능하다!

>사진(매테리얼 설정 화면)

1. Shader
	- 렌더링 할 때 효과를 주는 부분.
	- 기본적으론 Standard를 사용하지만, 조작을 통해 카툰 렌더링 등 다른 표현도 가능해진다.
2. Albedo
	- 매터리얼의 색상 조절.
3. Metallic, Smoothness
	- 금속 느낌 및 매끈함에 대한 설정.
4. Tiling
	- 그림을 타일처럼 여러 장으로 나눈다.
	- 수치가 높을수록 여러 장으로 나뉜다.
5. Normal Map
	- 실제 모델을 움푹 파게 될 경우 많은 폴리곤이 소요되므로 파인 것처럼 보이도록 깊이의 느낌을 주는 그림.
	- 3 차원(X, Y, Z축) 표현이다.
6. Height Map(Bump Map)
	- Normal Map과 비슷하지만 높낮이만 표현해 한 차원 낮은 정보를 표현한다.
7. Secondary Map
	- 매핑을 하나 이상 더해줘 좀 더 디테일한 매핑을 할 수 있게 해준다.


---

## 3. 게임 오브젝트와 컴포넌트

>게임 오브젝트란 유니티 내에서 게임을 만들 때 표현하는 다양한 사물, 인물, UI, 카메라, 조명, 지형 등을 아우르는 총칭.

### 1. 게임 오브젝트

- 모든 존재는 하나의 객체로 표현된다.
- 프로젝트 내 씬은 그 게임 오브젝트들이 모여있는 공간이다!
- 게임 오브젝트는 앞서 소개한 씬 뷰, 하이어라키 뷰에서 자유롭게 배치하고 위치, 각도, 크기 등을 조절할 수 있다.
- 게임 오브젝트는 하나 이상의 컴포넌트를 포함한다.

### 2. 컴포넌트

- 게임 오브젝트가 가진 기능.
	- 게임 오브젝트가 사람이라면, 컴포넌트 없는 게임 오브젝트는 식물인간과 같다...
- 게임 오브젝트는 씬 공간 어딘가에는 반드시 위치해야 하므로 위치 정보 없이 생성은 불가능하다.
	- 따라서, 위치 정보를 포함하는 트랜스폼(Transform) 컴포넌트(UI의 경우 렉트 트랜스폼;Rect Transform)를 반드시 포함해야 한다.
	- 트랜스폼 컴포넌트는 제거할 수 없다.
- 게임 오브젝트에 컴포넌트를 추가하는 방법은 두 가지가 있다.
	1. 메뉴 탭에서 추가.
		- 하이어라키 또는 씬 뷰에서 컴포넌트를 추가할 게임 오브젝트를 선택
		- \[Menu] 탭에서 \[Component] 탭으로 들어가 종류를 찾아 클릭.
	2. 검색
		- \[Add Component] 버튼을 클릭.
		- 검색 탭에서 검색해 클릭
- 이하는 자주 사용하는 컴포넌트이다.

#### 렌더러(Renderer)

- 스프라이트, 메쉬(Mash), 라인(Line), 트레일(Trail), 캔버스(Canvas) 등이 있다.
- 눈에 보이도록 하는 과정을 실행한다.
- 렌더러 컴포넌트를 비활성화 하면 그 오브젝트는 표시되지 않는다.
- 3D는 매테리얼 교체, 색상, 재질, 투명도 등 조정 가능.
- 2D는 스프라이트 렌더러로 색상 조절 및 뒤집기(Flip) 등 기능 지원.
- 더 자세한 것은 게임 제작 파트에서 설명.

#### 콜라이더(Collider)

>사진(콜라이더 경계)

- 물체의 충돌을 검사.
- 주황색 실선이 콜라이더의 경계에 표시된다.
- ***오브젝트가 그려진 부분과 콜라이더 경계는 다르다!!!***
- 콜라이더 영역을 수정해 실제 물체보다 크게 만들거나 작게 만들어 다양한 응용이 가능하다.

>사진(콜라이더 확장으로 공중에 뜬 물체)

- 뒤에 설명할 리지드바디(Rigidbody)를 적용하면 물리현상이 적용돼 중력의 영향을 받는다.
	- 콜라이더 경계를 확장해 물체를 공중에 띄울 수 있다!!

#### 리지드바디(Rigidbody)

- 물리 현상을 구현.
- 중력으로 아래로 떨어지거나 여러 물체가 콜라이더 경계에서 충돌했을 때 작용/반작용으로 튕겨나가는 역할
- 2D의 경우 리지드바디 2D(Rigidbody 2D)를 사용해야 한다.

#### 오디오 소스(Audio Source)

- 소리가 나게 하는 컴포넌트.
- 효과음이나 배경음 등 오디오 클립을 넣으면 해당 음원을 오디오 소스 위치에서 재생.
	- 스피커와 비슷하다.
- 메인 카메라(Main Camera) 오브젝트 안에 오디오 리스너(Audio Listener) 컴포넌트가 한 줄 존재한다.
	- 사람의 귀 역할을 한다.
	- 오디오 소스에 가까이 접근하면 소리가 커지고 멀어지면 작아진다.

#### 스크립트(Script)

- 이미 존재하는 스크립트와 직접 만든 스크립트가 있다.
- 이미 존재하는 스크립트
	- 스탠다드 에셋(Standard Asset) 내에 존재하는 스크립트와 에셋 스토어(Asset Store)에서 받은 스크립트를 모두 칭한다.
- 직접 만든 스크립트
	- 프로젝트 뷰에서 마우스 오른쪽 버튼 혹은 Create 버튼을 눌러 C\# Script를 눌러 생성한다.

- 유니티 C\# 스크립트는 생성될 때 지은 이름이 곧 클래스의 이름이 된다.
	- 파일 이름을 바꿀 때 클래스 이름도 바꿔야 한다!
	- 클래스명은 띄어쓰기가 불가능하다.
		- 스크립트 이름도 띄어쓰기가 있으면 안 된다!

---

## 4. 게임 오브젝트 배치

>씬 뷰 위에 있는 도구 툴을 사용해 편집할 수 있다.
>도구 툴 설명은 [씬 뷰의 도구 툴](#^SceneViewEditTools)을 참고하.

### 1. 게임 오브젝트 생성

- 여러 방법으로 가능하다. 이하는 가장 기본적인 하이어라키 뷰에서 생성하는 방법이다.
	- 하이어라키 뷰에서 \[Create] 버튼 클릭 또는 빈 곳이나 게임 오브젝트를 마우스 우클릭
	- Create Empty 아래 메뉴는 모두 게임 오브젝트이다.
		- 목적에 맞는 게임 오브젝트를 생성하자!
	- 게임 오브젝트의 상하(부모-자식) 관계가 잘못 되면 해당 오브젝트를 드래그해 관계나 위치 조정이 가능하다.

- 그림이나 3D 모델을 즉시 게임 오브젝트로 생성하는 방법
	- 해당 파일의 프로젝트 뷰를 선택해 드래그 앤 드롭을 하면 된다.

### 2. 게임 오브젝트 위치 조절

- 처음 게임 오브젝트를 생성하면 씬 뷰 화면 가운데 쯤 위치한다.
- 위치, 크기, 각도를 초기화하는 방법은 아래와 같다.
	- 인스펙터 뷰 화면을 띄운다.
	- 트랜스폼 컴포넌트 오른쪽 \[Setting] 버튼을 눌러 \[Reset] 버튼을 클릭한다.
	- \[Reset]은 다른 컴포넌트에서도 있으며, 해당 컴포넌트를 초기 상태로 만든다.
- 방법은 아래에서 소개하겠다.

### 3. 씬 뷰에서 편집

- 핸드 툴(단축키 \[Q])로 클릭 후 드래그 하면 화면을 상하좌우로 움직일 수 있다.
- 2D에서는 필요 없지만, 3D에서는 화면 회전이 필요하다.
	- 3D에서 마우스 우클릭 유지하며 드래그 하면 회전할 수 있다!
- 마우스 우클릭 유지하며 WASD 키를 누르면 자유 시점으로 화면을 움직일 수 있다.
	- 3D에서 현재 씬 뷰에서 보는 각도로 카메라를 조정하는 방법은 이하와 같다.
		- 카메라 선택
		- \[Ctrl] + \[Shift] + \[F]를 누른다.

### 4. 인스펙터 뷰에서 편집

- 위치, 각도, 크기를 조정할 수 있다.
- 씬 뷰에서 대략적인 위치를 잡고 인스펙터 뷰에서 정밀하게 조정하자.

---

## 5. 컴포넌트 수정

>변수 타입에 따라 다르다.

### 1. 숫자 타입

>사진(인스펙터 뷰 Transform 컴포넌트)

- 트랜스폼 컴포넌트 Position, Rotation, Scale의 X, Y, Z 값이 대표적이다.
- 직접 입력할 수도 있고, 이름을 눌러 좌우 화살표를 클릭 후 드래그로 빠르게 조정할 수 있다.

### 2. 문자열 타입

>사진(인스펙터 뷰 Text 컴포넌트)

- UI의 Text 컴포넌트의 Text, 스크립트의 String 타입이 대표적이다.
- 컴포넌트 내에서 문자열을 입력 받을 때 사용한다.
- 직접 작성하면 된다.

### 3. 색 타입

>사진(인스펙터 뷰 Color 컴포넌트)

- 렌더러 컴포넌트의 Color 변수, 매테리얼 Albedo 등이 대표적이다.
- 색이 보이는 칸을 클릭하면 컬러 피커(Color Picker)가 나와 색을 선택할 수 있다.
	- 투명도도 지원한다. 하단의 A를 조정하면 된다.
- 스포이드로 색을 복사할 수도 있다.

### 4. 체크박스 타입

>사진(인스펙터 뷰 check box 컴포넌트)

- Boolean 타입으로도 불린다.
	- 즉, 두 가지 값만 있다!
- 대표적으로 스프라이트 렌더러의 Flip, 리지드바디의 Use Gravity가 있다.

### 5. 슬라이더 타입

>사진(인스펙터 뷰 slider 컴포넌트)

- 최대, 최솟값이 존재하는 숫자 타입에서 쓰인다.
- 오디오 소스 컴포넌트의 Volume이 대표적이다.

### 6. 컴포넌트 타입

- 컴포넌트 변수 항목 중 'None( )'이라 적힌 칸이 있다.
- ( ) 안에 적힌 컴포넌트를 넣어야 동작한다.
	- None(Transform)이면 하이어라키 뷰에서 필요한 컴포넌트가 있는 오브젝트를 드래그 앤 드롭 해야한다.
- 더 자세한 설명은 게임 제작에서 다룬다.

---

## 6. 공굴리기 만들기

>간단한 물리를 적용해 공을 경사에 따라 굴려보자!

### 1. 프로젝트 생성

- 2D(혹은 2D 코어)로 프로젝트를 만들자!

### 2. 바닥 만들기

- 스프라이트 생성 기능을 이용해 사각형과 원 스프라이트를 만들자.
	- 프로젝트 뷰에서 \[Create] 버튼을 누르거나 빈 공간을 우클릭해 \[2D] - \[Sprites] - \[Square/Circle]을 누르면 된다.

![[6_2_1.make_project_sprites.png]]

- 하이어라키 뷰에서 게임 오브젝트를 만든다.
	- \[Create] - \[2D Object] - \[Splites] - \[Square]

![[6_2_2.make_hierarchy_splite_square.png]]

-  생성된 Square를 눌러 이름을 Floor로 바꾸자.
	- 직관적인 이름을 설정해 가시성을 높이는 것이 좋다. 다른 코드에서도!

![[6_2_3.inspector_sprite_renderer_sprite.png]]

- Square로 생성했으므로 인스펙터의 스프라이트 렌더러 컴포넌트를 확인하면 Sprite이 Square로 되어있다.
	- 우측 동그라미 버튼을 누르면 다른 Sprite로 쉽게 변경할 수 있다!

![[6_2_4.locate_floor_game_obj.png]]

- 앞서 설명한 대로 씬 뷰 카메라 정 중앙에 Floor 게임 오브젝트가 있고, 게임 뷰 정 중앙에 있는 것을 볼 수 있다.

![[6_2_5.inspector_view_of_floor_obj.png]]

- 인스펙터 창 Color를 눌러 RGB를 모두 0으로 설정하면 검은색이 된다.
- 인스펙터 창 제일 아래에 \[Add Component] 버튼을 눌러 Box Collider 2D를 찾아 누른다.
	- 2D가 없는 것은 3D다. 잘 구분하자!
-  정상적으로 Collider가 추가됐으면 아래와 같이 Scene View에서 Floor object 겉에 주황색 실선이 생긴다.
	- Inspector View에서 Box Collider Component의 \[Edit Collider] 버튼을 누르면 파란 점을 움직여 영역을 조절할 수 있다!

![[6_2_6.collider_area_of_floor_obj.png]]

- 이제 Floor를 Scene View에서 여러 개 만들어 이전에 설명했던 Hand Tool, Rotate Tool, Rect Tool 등을 적절히 활용해 맵을 만들어 보자.
	- Rect Tool로 Floor object를 누른 후 \[Ctrl] + \[C], \[Ctrl] + \[V]로 복붙할 수도 있지만, Floor object를 누른 후  \[Ctrl] + \[D]를 누르면 즉시 복사 된다!

![[6_2_7.sample_map.png]]

### 3. 공 만들기

![[6_3_1.ball_obj_inspector.png]]

- Floor를 만들었을 때와 같이 Splite object를 만들어 준다.
	- Square 대신 Circle을 고르고, 이름은 Ball로 하자.
	- 공의 크기는 적절하게 설정해주자. \[Shift]를 누른 체 드래그하면 비율을 유지하며 크기 조정이 가능하다.
	- 색깔도 구분 가능한 색으로 설정한다.

![[6_3_2.circle_collider_2d.png]]

- Floor와 마찬가지로 Collider를 추가해준다.
	- 원 형태이므로 Circle Collider 2D를 선택해야 한다.

![[6_3_3.rigidbody_2d.png]]

- Floor와 달리 중력의 영향(물리 법칙)을 받아야 하므로 \[Add Component]를 누른 후 'Rigidbody 2D'를 추가해준다.

### 4. 배경색 바꾸기

![[6_4_1.backround_color_ctl.png]]

- 배경 색은 Main Camera 게임 오브젝트를 선택한 후, inspecter View의 Camera에 'Background' 항목을 조정하면 된다.
	- 상단 사진의 왼쪽 화살표가 Main Camera 게임 오브젝트이고, 우측 화살표가 Background다.
	- 눈이 아프지 않고 구분이 가능하도록 적절히 조정해주자.

![[6_4_2.play_button.png]]

- 화면 상단의 중앙부에 있는 재생 버튼을 눌러 실제 움직임을 확인한다.
- ***테스트 플레이 도중 값을 변경하면 변경 사항이 저장되지 않는다.***
	- 재생 버튼을 한 번 더 눌러 테스트 플레이를 종료하고 조정해주자.

---

## 7. 완성된 씬 저장하기

- \[File] - \[Save As Scene Template...]를 눌러 씬을 저장할 수 있다.
	- 자주 저장하는 습관을 갖자.

![[7_1.not_saved.png]]

- 화면 최상단 플랫폼의 표기 옆에 조그만하게 '\*'가 있다면 마지막 저장 후 변경 사항이 있다는 뜻이다.