### MusicPlayer
1. Xcode
+ command + shift + Y -> Debug 창 띄우기
+ command + R -> App 실행
+ command + . -> App 중지	
+ ctrl + option + commadn + return(enter) -> Assistant

2. 프로젝트 이미지 추가하기
+ 에셋 카탈로그
	* Assets.xcassets 라는 폴더가 자동으로 생성된다.
	* 프로젝트에서 사용되는 다양한 에셋을 관리하며, 이를 에셋 카탈로그라고 한다.
+ 에셋 카탈로그 구성
	* Asset catalog
	* Group
	* Asset
	* Asset name
	* Asset files
	* Attributes
	* Asset variations: 에셋 파일들의 집합

+ 앱 시닝
	* 앱 시닝(app thinning) 이란
		- 애플리케이션이 디바이스에 설치될 때 앱 스토어와 운영체제가 그 디바이스의 특성에 맞게 설치하도록 하는 설치 최적화 기술
		- 이를 통해 설치용량을 최소화하고 다운로드의 속도를 향상시킬 수 있다
		- 앱 시닝의 기술 구성요소는 슬라이싱(slicing), 비트코드(bitcode), 주문형 리소스(on-demand resource)가 있다
	* 슬라이싱(slicing)이란
		- 애플리케이션이 지원하는 다양한 디바이스에 대한 여러 조각의 애플리케이션 번들(app bundle)을 생성하고 디바이스에 알맞는 조각을 전달하는 기술
		- 개발자가 애플리케이션 전체 버전을 Connect에 업로드 하게 되면, 앱 스토어에는 각 디바이스 특성에 다양한 버전의 조각들이 생성된다
		- 사용자가 애플리케이션을 설치할때 전체 버전이 아닌 슬라이싱된 조각들 중 사용자의 디바이스의 가장 최합한 조각이 다운로드되어 설치된다
		- 에셋 카탈로그에서 관리하는 이미지들은 자동으로 적용이 된다
	
+ 빠른 검색
	* shfit + command + o

