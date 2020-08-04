## :runner: Day04

### :page_with_curl: 함수

## 1. 함수선언의 기본 형태
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

## 2. 반환값이 없는 함수
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

## 3. 매개변수가 없는 함수
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

## 4. 매개변수와 반환값이 없는 함수
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

## 5. 함수의 호출 
```swift
sum(a:3, b:5) // 8

printMyName(name:"taetae") // taetae

printYourName(name:"haha") // haha

maximumIntegerValue() // Int의 최댓값

hello() // hello

bye() // bye
```
