## :runner: Day02

### :page_with_curl: ex00. 상수와 변수
#### 1. 상수와 변수 선언
- 상수 선언 키워드 : let  
- 변수 선언 키워드 : var
```swift
// 상수 및 변수 선언
let 상수이름:타입 = 값   //차후에 변경이 불가능한 상수 let
var 변수이름:타입 = 값   //차후에 변경이 가능한 변수 var
//타입이 명확하다면 타입 생략가능
let 상수이름 = 값 
var 변수이름 = 값
```
#### 2. 상수 선언 후,값 할당하기
- 선언 후, 변경할 상수나 변수는 반드시 타입을 명시해야한다.
```swift
//상수의 할당
let sum:Int
var inputA:Int = 100
var inputB:Int = 200

//선언 후 첫 할당
sum = inputA + inputB
// 할당된 상수는 이후에 다시 값을 할당할 수 없다.

//변수의 할당
var name:String

name = "taetae"
// 변수는 할당 후에도 다시 값을 할당할 수 있다.
name = "태태"
```
### :page_with_curl: ex01. 기본 데이터 타입
#### 1. Swift의 기본 데이터 타입 종류
- Bool
- Int,UInt
- Float, Double
- Character, String

#### 2. Bool
- True와 False만 값으로 가지는 데이터 타입
```swift
var someBool = true
someBool = false
// 0이나 1로 표현하면 오류가 발생
```

#### 3. Int,UInt
- Int : 정수 타입. 현재는 기본적으로 64bit 정수형
- UInt : 양의 정수 타입. 현재는 기본적으로 64bit 정수형
```swift
var someInt: Int = -100
// 정수 이외 소수 같은 값이 들어오면 오류 발생

var someUInt: UInt = 100
// 양의 정수만 가능, someUInt = someInt 또한 데이터 타입이 다르기 때문에 오류 발생
```

#### 4. Float, Double 
- Float : 실수 타입. 32비트 부동소수형
- Double : 실수 타입. 64비트 부동소수형
```swift
//Float 
var someFloat: Float = 123.456
someFloat = 3

// Double
var someDouble: Double = 123.223
someDouble = 3 

// someFloat = someDouble 데이터 타입이 다르기 때문에 컴파일 오류 발생
```

#### 5. Character, String
- Character : 문자 타입. 유니코드 사용. 큰따옴표("")사용
- String : 문자열 타입. 유니코드 사용. 큰따옴표("") 사용

```swift
//Character
var someCharacter: Character ="🐶"
someCharacter = "가"
someCharacter = "A"
someCharacter = "☺️"
//someCharacter = "abc" 는 문자열이기 때문에 오류 발생

//String
var someString: String = "하하하😆"
someString = someString + "웃으면 복이 와요"
print(someString)
```
:bulb: Tip!
- type(of: 이름)을 사용하면 타입을 알 수 있다.

### :page_with_curl: ex02. Any, AnyObject, nil
- Any : Swift의 모든 타입을 지칭하는 키워드
- AnyObject : 모든 클래스 타입을 지칭하는 프로토콜(특정 역할을 하기 위한 메서드, 프로퍼티, 기타 요구사항등의 청사진)
- nil : '없음'을 나타내는 키워드

#### 1. Any
- Swift의 모든 타입을 지칭
```swift
//Any 
var someAny: Any = 100
someAny = "Any는 어떤 타입도 수용 가능합니다.
someAny = 3.14

// someAny에 Double 형을 넣어 두었더라도 Double 자료형이 아니기 때문에 할당 불가능.
var someDouble: Double  = someAny  //컴파일 오류 발생
// 이 경우 타입을 명시적으로 변환해 주어야 한다.
```

#### 2. AnyObject
- 모든 클래스 타입을 지칭하는 프로토콜
```swift
class SomeClass {}
var someAnyObject: AnyObject = SomeClass()

// AnyObject는 클래스의 인스턴스만 수용 가능하기 때문에 클래스의 인스턴스가 아니면 할당할 수 없다.
someAnyObject = 123.12    // 컴파일 오류발생
```

#### 3. nil
- '없음'을 나타내는 키워드
- 다른 언어의 Null, null, NULL등과 같은 표현
```swift
// someAny는 Any 타입이고, someAnyObject는 AnyObject 타입이기 때문에 nil을 할당할 수 없다.
var someAny: Any = 2020
var someAnyObject: AnyObject = SomeClass()

// nil을 다루는 방법은 옵셔널 파트에서 정리
someAny = nil         // 컴파일 오류발생
someAnyObject = nil   // 컴파일 오류발생
```
