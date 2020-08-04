## :runner: Day04

### :page_with_curl: 함수 기본

#### 1. 함수선언의 기본 형태
```swift
func 함수이름(매개변수이름:매개변수타입, 매개변수이름:매개변수타입 ...) -> 반환타입 {
	// 함수 구현부 //
  return 반환값
}

// 예)
// sum이라는 이름을 가지고 
// a , b 라는 Int 타입의 매개변수를 가지며
// Int 타입의 값을 반환하는 함수

func sum(a:Int, b:Int) -> Int{
  return a + b
}
```

#### 2. 반환값이 없는 함수
```swift
func 함수이름(매개변수이름:매개변수타입, ...) -> Void{
	// 함수 구현부 //
  return
}

// 예)
func printMyName(name: String) -> Void{
  print(name)
}

// 반환 값이 없는 경우, 반환 타입(Void)을 생략해 줄 수 있다.
func printYourName(name: String){
  print(name)
}
```

#### 3. 매개변수가 없는 함수
```swift
func 함수이름() -> 반환타입{
	// 함수 구현부 //
  return 반환값
}

//예)
func maximumIntegerValue() -> Int{
  return Int.max
}
```

#### 4. 매개변수와 반환값이 없는 함수
```swift
func 함수이름() -> Void{
	//함수 구현부//
  return
}

// 함수 구현이 짧은 경우
// 가독성을 해치지 않는 범위에서
// 줄바꿈을 하지 않고 한줄에 표현해도 무관하다.

func hello() -> Void {print("hello")}

//반환 값이 없는 경우, 반환 타입(Void)을 생략해 줄 수 있다.

func 함수이름(){
	// 함수 구현부//
  return
}

func bye() {print("bye")}
```

#### 5. 함수의 호출 
```swift
sum(a:3, b:5) // 8

printMyName(name:"taetae") // taetae

printYourName(name:"haha") // haha

maximumIntegerValue() // Int의 최댓값

hello() // hello

bye() // bye
```

### :page_with_curl: 함수 고급 

#### 1. 매개변수 기본 값
- 매개변수에 기본적으로 전달될 값을 미리 지정해 둘 수 있다.
- 기본값을 갖는 매개변수는 매개변수 목록 중 뒤쪽에 위치하는 것이 좋다.

```swift
func 함수이름(매개변수이름: 매개변수타입, ...) -> 반환타입{
	//함수 구현부//
  return 반환값
}

func greeting(friend: String, me: String ="taetae"){
  print("Hello ₩(friend)! I'm ₩(me)")
}

// 매개변수 기본값을 가지는 매개변수는 호출시 생략가능
greeting(friend: "haha") // Hello haha! I'm taetae
greeting(friend: "john", me: "eric") // Hello john! I'm eric
```

#### 2. 전달인자 레이블 (Argument Label)
- 함수를 호출 할 때 함수 사용자의 입장에서 매개변수의 역할을 좀 더 명확하게 표현하고자 할 때 사용.
- 전달인자 레이블은 변경하여 동일한 이름의 함수를 중복으로 생성가능.

```swift
func 함수이름(전달인자 레이블 매개변수이름: 매개변수타입, ...) -> 변환타입{
	// 함수 구현부 //
  return
}

// 함수 내부에서 전달인자를 사용할 때에는 매개변수 이름을 사용한다.
func greeting(to friend: String, from me: String) {
  print("Hello ₩(friend)! I'm ₩(me)")
}

// 함수를 호출할 때에는 전달인자 레이블을 사용해야 한다.
greeting(to:"haha", from:"taetae") // Hello haha! I'm taetae
```

#### 3. 가변 매개변수 
- 전달 받을 값의 개수를 알기 어려울 때 사용한다.
- 가변 매개변수는 함수당 하나만 가질 수 있다.
- 기본값이 있는 매개변수와 같이 가변 매개변수 역시 매개변수 목록 중 뒤쪽에 위치하는 것이 좋다.

```swift
//func 함수이름(매개변수이름: 매개변수타입, 전달인자 레이블 매개변수2이름: 매개변수2타입...) -> 반화타입{
	// 함수 구현부//
//return
//}

func sayHelloToFriend(me: String, friends: String...) -> String{
  return "Hello ₩(friends)! I'm ₩(me)!"
}

print(sayHelloToFriends(me: "taetae", friends: "haha", "eric", "wing"))
// Hello ["haha", "eric", "wing"]! I'm taetae!

print(sayHelloToFriends(me: "taetae"))
// Hello []! I'm taetae!
```

- 반환값이 없는 함수, 매개변수 기본 값, 전달인자 레이블, 가변 매개변수 등 모두 섞어서 사용가능

#### 4. 데이터 타입으로서의 함수 
- 스위프트는 함수형 프로그래밍 패러다임을 포함하는 다중 패러다임 언어이므로 스위프트의 함수는 일급객체이다. 그래서 함수를 변수, 상수 등에 할당이 가능하고 매개변수를 통해 전달할 수도 있습니다.
- **함수의 타입표현** : 반환 타입을 생략할 수 없습니다.

```swift
(매개변수1타입, 매개변수2타입 ...) -> 반환타입
```

- **함수타입 사용**

```swift
var someFunction:(String, String) -> Void = greeting(to:from:)
someFunction("eric", "taetae") // Hello eric! I'm taetae

someFunction = greeting(friend:me:)
someFunction("eric", "taetae") // Hello eric! I'm taetae

// 타입이 다른 함수는 할당할 수 없다. > 컴파일 오류 발생
// someFunction = sayHelloToFrieds(me: friends:)


func runAnother(funtion: (String,String) -> Void) {
  function("jenny", "mike")

//Hello jenny! I'm mike
runAnother(function:greeting(friend:me:))

//Hello jenny! I'm mike
runAnother(function:someFunction)

** **스위프트 전반적인 문법에서 띄어쓰기를 신경써야할 때가 많다.**
