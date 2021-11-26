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

+ Object Libary
	* command + shift + l

3. IBOutlet, IBAction 인터페이스 객체와 연결

+ IBOutlet 과 인터페이스 빌더 요소 연결
	* 코드로 먼저 IBOutlet을 생성한 후 인터페이스 빌더의 Outlet Inspector를 통해 연결
	* 코드로 먼저 IBOutlet을 생성한 후 인터페이스 빌더에서 View Controller 우클릭 후 팝업에서 연결
	* 인터페이스 빌더에서 코드로 끌어당겨 연결

+ 인터페이스 빌더의 객체를 코드와 연결(IBAction)
	* 인터페이스 빌더의 객체에서 발생한 액션과 코드 연결(IBAction)
		- IBAction으로 객체에서 발생하는 액션을 코드로 연결해 사용자 동작에 상호 작용할 수 있도록 함
	
+ 컨트롤 이벤트와 액션과의 관계
	* UIKit에는 UIButton, UI Stepper 등 UIControl을 상속받은 다양한 컨트롤 클래스가 있다
	* 컨트롤 객체에 발생한 다양한 이벤트 종류를 특정 액션 메서드에 연결할 수 있다
	* 컨트롤 객체에서 특정 이벤트가 발생하면, 미리 지정된 타겟의 액션을 호출하게 된다

+ 컨트롤 이벤트의 종류
	* 컨트롤 이벤트는 UIControl에 Event라는 타입으로 정의되어 있다
	* 컨트롤 객체에 발생할 수 있는 이벤트의 종류
		- touchDown: 컨트롤을 터치했을 때 발생
		- touchDownRepeat: 컨트롤을 연속으로 터치 할 때 발생
		- touchDragInside: 컨트롤 범위 내에서 터치한 영역을 드래그 할 때 발생
		- touchDragOutside: 터치 영역이 컨트롤 바깥쪽에서 드래그 할 때 발생
		- touchDragEnter: 터치 영역이 컨트롤의 일정 여역 바깥쪽으로 나갔다가 다시 들어왔을 때 발생
		- touchDragExit: 터치 영역이 컨트롤의 일정 영역 바깥쪽으로 나갔을 때 발생
		- touchUpInside: 컨트롤 영역 안쪽으로 터치 후 뗐을때 발생
		- touchUpOutside: 컨트롤 영역 안쪽에서 터치 후 컨트롤 밖에서 뗐을 때 발생
		- toutchCancel: 터치를 취소하는 이벤트(touchUp 이벤트가 발생하지 않음)
		- valueChanged: 터치를 드래그 및 다른 방법으로 조작하여 값이 변경되었을때 발생
		- primaryActionTriggered: 버튼이 눌릴때 발생하는 이벤트(IOS보다는 tvOS에서 사용)
		- editingDidBegin: UITextField에서 편집이 시작될 때 호출되는 이벤트
		- editingChanged: UITextField에서 값이 바뀔 때마다 호출되는 이벤트
		- editingDidEnd: UITextField에서 외부객체와의 상호작용으로 인해 편집이 종료되었을 때 발생하는 이벤트
		- editingDidEndOnExit: UITextField의 편집상태에서 키보드의 return 키를 터치했을 때 발생하는 이벤트
		- allTouchEvents: 모든 터치 이벤트
		- allEditingEvents: UITextField에서 편집작업의 이벤트
		- applicationReserved: 각각의 애플리케이션에서 프로그래머가 임의로 지정할 수 있는 이벤트 값의 범위
		- systemReserved: 프레임워크 내에서 사용하는 예약된 이벤트 값의 범위
		- allEvnets: 시스템 이벤트를 포함한 모든 이벤트


+ UIButton
	* 버튼과 메서드 연결 방법
		- addTarget(_:action:for:) 메서드 사용
		- 인터페이스 빌더에서 연결 @IBAction

	* 버튼과 연결되는 메서드 형식
		- func doSomething()
		- func doSomething(sender: UIButton)
		- func doSomething(sender: UIButton, forEvent event: UIEvent)

	* 버튼의 상태
		- 버튼의 상태는 5가지로 표현된다
		- default, highlighted, focused, selected, disabled
		- 버튼의 상태는 조합된 상태일 수 있다
	* 버튼의 주요 프로퍼티
		- enum UIButtonType: 버튼의 유형
		- 버튼의 유형에 따라 기본적인 외형과 동작이 달라진다
		- 한번 생성된 버튼의 유형은 이후 변경 불가
		- 가장 많이 사용하는 유형은 Custom 과 System 이지만 다른 유형( Detail Disclosure, Info Light, Info Dark, Add Contct)도 있음
		- var titleLabel: UILabel?: 버튼 타이틀 레이블
		- var imageView: UIImageView?: 버튼의 이미지 뷰
		- var tintColor: UIColor!: 버튼 타이틀과 이미지의 틴트 칼라
	* 버튼 주요 메서드
		- func setTitle(String?, for: UIControlState) : 특정 상태의 버튼의 문자열 설정
		- func title(for: UIControlState) -> String? : 특정 상태의 버튼의 문자열 반환
		- func setImage(UIImage?, for: UIControlState): 특정 상태의 버튼 이미지 설정
		- func image(for: UIControlState): 특정 상태의 버튼 이미지 반환
		- func setBackgroundImage(UIImage?, for: UIControlState): 특정 상태의 백그라운드 이미지 설정
		- func backgroundImage(for: UIControlState) -> UIImage : 특정 상태의 백그라운드 이미지 반환
		- func setTitleColor(UIColor?, for: UIControlState): 특정 상태의 문자열 색상 설정
		- func setAttributedTitle(NSAttributedString?, for: UIControlState) : 특정 상태의 attributed 문자열 설정

+ UILabel
	* 주요 프로퍼티
		- var numberOfLines: 문자를 나태내는 최대 라인 수
			+ 문자열을 모두 표시하는 데 필요한 만큼 해을 사용하려면 0으로 설정. 기본값은 1
			+ 설정한 문자열이 최대 라인 수를 초과하면 lineBreakMode 프로퍼티의 값에 따라 적절히 잘라서 표현
			+ adjustsFontSizeToFitWidth 프로퍼티를 활용하면 폰트 사이즈를 레이블의 넓이에 따라 자동으로 조절해줌
		- var baselineAdjustment: UIBaselineAdjustment: 문자열이 Autoshrink 되었을 때의 수직 정렬 방식
			+ Align Baseline: 문자가 작아졌을 떄 기존 문자열의 기준선에 맞춤
			+ Align Center: 문자가 작어졌을 때 작아진 문자의 중앙선에 맞춤
			+ None: 문자가 작아졌을 때 기존 문자열의 위쪽 선에 맞춤
		- var lineBreakMode: NSLineBreakMode: 레이블의 경계선을 벗어나는 문자열에 대응하는 방식
			+ Character wrap: 여러 줄 레이블에 주로 적용되며, 글자 단위로 줄 바꿈을 겨정
			+ Word wrap: 여러 줄 레이블에 주로 적용되며, 단어 단위로 줄 바꿈 결정
			+ Trucate head: 한 줄 레이블에 주로 적용되며, 앞쪽 테스트를 자르고 ...으로 표시
			+ Trucate middle: 한 줄 레이블에 주로 적용되며, 중간 텍스트를 자르고 ...으로 표시
			+ Trucate tail: 한 줄 레이블에 주로 적용되며, 끝쪽 텍스트를 자르고 ...으로 표시(기본값)

+ UISlider
	* 주요 프로퍼티
		- var minimumValue: Float, var maximumValue: Float: 슬라이더 양 끝단값
		- var value: Float: 슬라이더 현재 값
		- var isContinuous: Bool: 슬라이더 연속적인 값 변화에 따라 이벤트 역시 연속적으로 호출할 것인지 여부
		- var minumumValueImage: UIImage?, var maximumValueImage: UIImage?: 슬라이더 양끝단의 이미지
		- var thumbTintColor: UIColor?: thumb의 틴트 색상
		- var minimumTrackTintColor: UIColor?, var maximumTrackTintColor: UIColor?: thumb를 기준으로 앞쪽 트랙과 뒤쪽 트랙의 틴트 색상


+ AVFoundation
	* 다양한 Apple 플래폼에서 사운드 및 영상 미디어의 처리, 제어 가져오기 및 내보내기 등 광범위한 기능을 제공하는 프레임워크
	* 주요 기능
		- 미디어 재생 및 편집
		- 디바이스 카메라와 마이크를 이용한 영상 녹화 및 사운드 녹음
		- 시스템 사운드 제어
		- 문자의 음성화
	* AVAudioPlayer Class
		- AVAudioPlayer 클래스는 파일 또는 메모리에 있는 사운드 데이터를 재생하는 기능을 제공한다
	* AVAudioPlayer 주요 기능
		- 파일 또는 메모리에 있는 사운드 재생
		- 파일 재생 시간 길이의 제한없이 사운드 재생
		- 여러 개 사운드 파일 동시 재생
		- 사운드의 재생 속도 제어 및 스테레오 포지셔닝
		- 앞으로 감기와 뒤로 감기 등의 기능을 지원해 사운드 파일의 특정 지점 찾기
		- 현재 재생 정보 데이터 얻기
		- 사운드 반복재생 기능
	* 주요 프로퍼티
		- var isPlaying: Bool: 사운드가 현재 재생되고 있는지 아닌지 여부
		- var volume: Float: 사운드의 볼륨값, 최소 0.0 ~ 최대 1.0
		- var rate: Float: 사운드의 재생 속도
		- var numberOfLoops: Int: 사운드 재생 반복 횟수
			+ 기본값은 0으로 사운드 1회 재생 후 자동 종료
			+ 양수값으로 설정시 설정값+1 회 재생
			+ 음수값으로 설정시 stop메소드가 호출 될떄까지 무한 재생
		- var duration: TimeInterval: 사운드의 총 재생 시간(초 단위)
		- var currentTime: TimeInterval: 사운드의 현재 재생 시각(초 단위)
		- protocol AVAudioPlayerDelegate: 사운드 재생완료, 재생 중단 및 디코딩 오류에 응당할 수 있는 프로토콜
	* 주요 메서드
		- func init(contentOf: URL): 특정 위치에 있는 사운드 파일로 초기화
		- func init(data: Data): 메모리에 올라와 있는 데이터를 이용해 초기화
		- func play(): 사운드 재생
		- func play(atTime: TimeInterval): 특정 지점에서 재생
		- func puase(): 사운드 일시 정지
		- func stop(): 사운드 재생 정지
+ Timer
  + Timer 클래스는 일정한 시간 가격이 지나면 지정된 메시지를 특정 객체로 전달하는 기능을 제공
  + Timer의 특징
    + 타이머는 런 루프(run loops)에서 작동
    + 타이머를 생성할 때 반복 여부를 지정
      + 비 반복 타이머: 한 번 실행된 다음 자동으로 무효화
      + 반복 타이머: 동일한 런 루프에서 특정 TimeInterval 간격으로 실행, 반복되는 타이머 기능을 정지하려면 invalidate() 메소드를 호출하여 무효화 해야함
  + Timer 주요 프로퍼티
    + var isValid: Bool: 타이머가 현재 유효한지 아닌지 여부
    + var fireDate: Date: 다음에 타이머가 실행될 시각
    + var timeInterval: TimeInterval: 타이머의 실행 시간 간격(초 단위)

+ Cocoa Touch란?
  + 코코아 터치 계층(Cocoa Touch Layer)
    + 코코아라는 단어는 Objective-C 런타임을 기반으로 하고, NSObject를 상속받는 모든 클래스 또는 객체를 가르킬 때 사용
    + 코코아터치 또는 코코아는 iOS 또는 macOS의 전반적인 기능을 활용해 애플리케이션을제작할 떄 사용하는 프레임워크 계층
    + 코코아 터치는 핵심 프레임워크인 UIKit 과 Foundation을 포함
    + iOS Application <-> Cocoa Touch[ UIKit, Foundation, CoreData, MapKit, CoreAnimation, etc] <-> Hardware
+ UIKit 이란?
  + UIKit은 iOS 애플리케이션 개발시 사용자에게 보여질 화면을 구성하고 사용자 액션에 대응에 관련된 다양한 요소를 포함
  + 사용자 인터페이스를 구현하고 이벤트를 관리하는 프레임워크
  + 제스처 처리, 애니메이션, 그림 그리기, 이미지 처리, 텍스트 처리 등 사용자 이벤트 처리를 위한 클래스를 포함
  + 테이블뷰, 슬라이더, 버튼, 텍스트 필드, 얼럿 창 등 애플리케이션 화면을 구성하는 요소 포함
  + UIResponder에서 파생된 클래스나 사용자 인터페이스에 관련된 클래스는 메인 스레드(혹은 메인 디스패치 큐)에서만 사용 해야 한다.
  + UIKit은 iOS와 tvOS 플랫폼에서 사용
  + 기능별 요소
    + 사용자 인터페이스
      + View and Control: 화면에 콘텐츠 표시
      + View Controller: 사용자 인터페이스 관리
      + Animation and Haptics: 애니메이션과 햅틱을 통한 피드백 제공
      + Window and Screen: 뷰 계층을 위한 윈도우 제공
    + 사용자 액션
      + Touch, Press, Gesture: 제스처 인식기를 통한 이벤트 처리 로직
      + Drag and Drop: 화면 위에서 드래그 앤 드롭 기능
      + Peek and Pop: 3D 터치에 대응한 미리 보기 기능
      + Keyboard and Menu: 키보드 입력을 처리 및 사용자 정의 메뉴 표시

+ Foundation이란?

  + Foundation은 iOS 애플리케이션의 운영체제 서비스와 기본 기능을 포함하는 프레임워크

  + 원시 데이터 타임(String, Int, Double), 컬렉션 타입(Array, Dictionary, Set) 및 운영체제 서비스를 사용해 애플리케이션의 기본적인 기능을 관리하는 프레임 워크

  + 데이터 타입, 날짜 및 시간 계산, 필터 및 정렬, 네트워킹 등의 기본 기능을 제공

  + iOS뿐만 아니라 macOS, watchOS, tvOS등 모든 애플 SDK에서 사용

  + Foundation에서 제공하는 데이터 타입 및 컬렉션 타입의 대부분은 Objective-C 언어의 기능에서 지원하지 않는 것이기 때문에 언어기능을 보완하기 위한 구현이며, Swift에서는 이에 해당하는 데이터 타입과 기능 대부분을 Swift 표준 라이브러리에서 제공함

  + Foundation 기능별 요소

    + 기본
      + Number, Data, String: 원시 데이터 타입 사용
      + Collection: Array, Dictionary, Set 등과 같은 컬렉션 타입 사용
      + Date and Time: 날짜와 시간을 계산하거나 비교하는 작업
      + Unit and Measurement: 물리적 차원을 숫자로 표현 및 관련 단위 간 변환 기능
      + Data formatting: 숫자, 날짜, 측정값 등을 문자열로 변환 또는 반대 작업
      + Filter and Sorting: 컬렉션의 요소를 검사하거나 정렬하는 작업
    + 애플리케이션 지원
      + Resources: 애플리케이션의 에셋과 번들 데이터에 접근 지원
      + Notification: 정보를 퍼뜨리거나 받아들이는 기능 지원
      + App Extenttion: 확장 애플리케이션과의 상호작용 지원
      + Error and Exceptions: API와의 상호작용에서 발생할 수 있는 문제 상황에 대처할 수 있는 기능 지원

    + 파일 및 데이터 관리
      + File System: 파일 또는 폴더를 생성하고 읽고 쓰는 기능 관리
      + Archives and Serialization: 속성 목록, JSON, 바이너리 파일들을 객체로 변환 또는 반대 작업 관리
      + iCloud: 사용자의 iCloud 계정을 이용해 데이터를 동기화 하는 작업 관리
    + 네트워킹
      + URL Loading System: 표준 인터넷 프로토콜을 통해 URL과 상호작용하고 서버와 통신하는 작업
      + Bonjour: 로컬 네트워크를 위한 작업

    + UIKit에서도 import Foundation 사용함

+ 오토레이아웃이란?
  + 디바이스 사이즈에 구애받지 않고 시각적으로 동일한 화면을 구현하는데 가장 편리하고 권장되는 방법
  + 뷰의 제약 사항을 바탕으로 뷰 체계 내의 모든 뷰의 크기와 위치를 동적으로 계산
  + 외부 변경(External Changes)
    + 외부 변경은 슈퍼뷰의 크기나 모양이 변경될 때 발생, 각가의 변화와 함께 사용 가능한 공간을 가장 잘 사용할 수 있도록 뷰 체계의 레이아웃을 업데이트해줘야 함
    + 외부 변경이 발생하는 경우
      + 사용자가 아이패드의 분할뷰(Split VIew)를 사용하거나 사용하지 않는 경우(IOS)
      + 장치를 회전하는 경우(iOS)
      + 활성화콜(active call)과 오디오 녹음 바가 보여지거나 사라지는 경우(iOS)
      + 다른 크기의 클래스를 지원하기 원하는 경우
      + 다른 크기의 스크린을 지원하기 원하는 경우
  + 내부 변경(Internal Changes)
    + 내부 변경은 사용자 인터페이스의 뷰의 크기 또는 설정이 변경되었을 때 발생
    + 내부 변경이 발생하는 경우
      + 애플리케이션의 변경에 의해 콘텐츠가 보여지는 경우
      + 애플리케이션이 국제화를 지원하는 경우
      + 애플리케이션이 동적 타입을 지원하는 경우
  + 오토레이아웃의 속성
    + Width: 정렬 사각형의 너비
    + Height: 정렬 사격형의 높이
    + Top: 정렬 사각형의 상단
    + Bottom: 정렬 사각형의 하단
    + Baseline: 텍스트의 하단
    + Horizontal: 수평
    + Vertical: 수직
    + Leading: 리딩, 텍스트를 읽을 때 시작 방향
    + Trailing: 트레일링, 테스트를 읽을 때 끝 방향
    + CenterX: 수평 중심
    + CenterY: 수직 중심
  + 안전 영역(Safe Area)
    + 안전 영역은 콘텐츠가 상태바, 네비게이션바, 툴바, 탭바를 가리는 것을 방지하는 영역
    + 표준 시스템이 제공하는 뷰들은 자동으로 안전 영역 레이아웃 가이드를 준수하게 되어 있다
    + 기존의 상/하단 레이아웃 가이드(Top/Bottom Layout Guide)를 대체하며, 하위 버전에도 호환하여 작동
    + UIView 클래스의 var safeAreaLayoutGuide: UILayoutGuide로 접근
  + 제약(Constraint)
    + 제약은 뷰 스스로 또는 뷰 사이의 관계를 속성을 통하여 정의
    + 제약은 방정식으로 나타낼 수 있다
    +  A View < ---- 8 ----> B View
      + B.Leading = 1.0 x A.Trailing + 8.0
      + B: item1
      + Leading: Attribute1
      + 1.0: Multiplier
      + A: item2
      + Trailing: Attribute2
      + 8.0: Constant
    + 고유 컨텐츠 크기(Intrinsic Content Size)
      + 뷰의 고유 컨텐츠 크기는 뷰가 갖는 원래의 크기로 생각할 수 있다
      + 예를 들어 레이블의 고유 컨텐츠 크기는 레이블의 텍스트의 크기이고, 이미지의 고유 컨텐츠 크기는 이미지 자체 크기이다
    + 제약 우선도(Constraint Priorities)
      + 오토레이아웃은 뷰의 고유 컨텐츠 크기를 각 크기에 대한 한 쌍의 제약을 사용하여 나타냄
      + 우선도가 높을수록 다른 제약보다 우선적으로 레이아웃에 적용
      + 같은 속성의 다른 제약과 경합하는 경우, 우선도가 낮은 제약은 무시
        + 컨텐츠 허깅 우선도(Content hugging priority): 컨텐츠 고유 사이즈보다 뷰가 커지지 않도록 제한, 다른 제약사항보다 우선도가 높으면 뷰가 컨텐츠 사이즈보다 커지지 않는다
        + 컨텐츠 축소 방지 우선도(Content compression resistance priority): 컨텐츠 고유 사이즈보다 뷰가 작아지지 않도록 제한, 다른 제약사항보다 우선도가 높으면 뷰가 컨텐츠 사이즈보다 작아지지 않는다
    + 레이아웃 마진
      + 뷰에 컽네츠 내용을 레이아웃할 때 사용하는 기본 간격(default spacing)
        + 레이아웃 마진 가이드(Layout Margin Guide): 레이아웃 마진에 따라 형성되는 사각의 프레임 영역
    + 앵커(Anchor)
      + 오토레이아웃을 Programmatically식으로 구현하여 제약(Constraint)을 만들기 위해 사용
      + translatesAutoresizingMaskIntoConstrains
        + 오토레이아웃이 도입되기 전 뷰를 유연하게 표현할 수 있도록 오토리사이징 마스크를 사용하였음
        +  오토레이아웃을 사용하게 되면 기존의 오토리사이징 마스크가 가지고 있던 제약조건이 자동으로 추가되기 때문에 충돌하게 될 가능성 있음
        + 해당 값을 false로 설정한 뒤 오토레이아웃을 적용해 주어야 함
        + 인터페이스 빌더에서 오토레이아웃을 사용할 경우 해당 값이 자동으로 false로 설정
