## :runner: Day05
- **조건문과 반복문**

### :page_with_curl: ex00. 조건문
- if-else
- switch

#### 1. if-else 구문
 - **if-else 구문의 기본 형태**
 - if만 단독으로 사용해도되고, else, else if 와 조합해서 사용 가능하다.
 - if 뒤의 조건 값에는 Bool 타입의 값만 위치해야 한다.
 - 조건을 감싸는 소괄호는() 선택사항이다.
   * swift의 조건에는 항상 Bool 타입이 들어와야 한다. *
```swift
if 조건 {
  /* 실행 구문 */
} else if
  /* 실행 구문 */
} else {
  /* 실행 구문 */
}
```
- **if-else의 사용**

```swift
let someInteger = 100

if someInteger < 100{
  print("100 미만")
} else if someInteger > 100 {
  print("100 초과")
} else { 
  print("100")
}  // 100
```

#### 2. switch 구문
 - 스위프트의 switch 구문은 다른언어에 비해 굉장히 강력한 힘을 발휘한다.
 - 기번적으로 사용하던 정수타입의 값만 비교하는 것이 아니라 대부분의 스위프트 기본 타입을 지원하며, 다양한 패턴과 응용이 가능.
 - 스위프트의 다양한 패턴은 [Swift Programming Langyarge Reference의 패턴](https://docs.swift.org/swift-book/index.html)에서 확인할 수 있다.
 - 각각의 case 내부에는 실행가능한 코드가 반드시 위치해야 한다.
 - 매우 한정적인 값(ex. enum의 case 등)이 비교값이 아닌 한 default 구문은 반드시 작성해야 한다.
 - 명시적 break를 하지 않아도 자동으로 case마다 break 됨.
 - fallthrough 키워드를 사용하여 break를 무시할 수 있다.
 - 쉼표(,)를 사용하여 하나의 case에 여러 패턴을 명시할 수 있다.  
 
 -  **switch 구문의 기본 형태**
 ```swift 
 switch 비교값 { 
 case 패턴:
  /* 실행 구문 */
 default:
  /* 실행 구문 */
 }
 ```
 
 - **switch 구문의 사용**
 
```swift
// 범위 연산자를 활요하면 더욱 쉽고 유용하다
switch someInteger {
case 0:
  print("zero")
case 1..<100:
  print("1 ~ 99")
case 101...Int.max:
  print("over 100")
default:
  print("unknow")
}  //100

// 정수 외의 대부분의 기본 타입을 사용할 수 있습니다
switch "taetae" { 
case "tony":
  print("tony")
case "lina":
  print("lina")
case "glory":
  print("glory")
case "taetae":
  print("taetae")
default:
  print("unknown")
} // taetae
```

### :page_with_curl: ex01. 반복문
 - for-in
 - while
 - repeat-while
 
 #### 1. for-in 구문
 - 기존 언어의 for-each 구문과 유사하다.
 - Dictionary의 경우 이터레이션 아이템으로 튜플이 들어온다.[Reference](https://docs.swift.org/swift-book/LanguageGuide/TheBasics.html)의 tuples 부분 참조.
 - 이터레이션 아이템 ?
 - for-in 구문 기본 형태
 ```swift
 for item in iterms {
 /* 실행 구문 */
 }
 ```
 - **for-in 구문의 사용
 
 ```swift
 var integers = [1, 2, 3]
 let people = ["taetae":10, "tony":15, "lina": 12]
 
 for integer in integers {
  print(integer)
 }
 
 // Dictionary의 item은 key와 value로 구성된 튜플 타입이다.
 for (name,age) in people {
  print("₩(name): ₩(age)")
 }
 ```
 
 #### 2. while 구문
 - **while 구문의 기본 형태**
 ```swift
 while 조건 {
 /* 실행 구문 */
}
```
 - **while 구문의 사용**
 
 ```swift
 while integers.count > 1 {
  integers.removeLast()
 }
 ```
 
 #### 3. repeat-while 구문
 - 기존 언어의 do-while 구문과 형태/동작이 유사하다.
 - **repeat-while 구문의 기본 형태**
 
 ```swift
 repeat {
  /* 실행 구문 */
  } while 조건
 ```
 
 - **repeat-while 구문의 사용**
 
 ```swift
 repeat {
  integers.removeLast()
  } while.integers.count > 0
  ```
