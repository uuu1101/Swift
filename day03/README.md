## :runner: Day03

### :page_with_curl: 컬렉션 타입(Array, Dictionary, Set)
- Array : 순서가 있는 리스트 컬렉션
- Dictionary : 'Key'와 'Value'의 쌍으로 이루어진 컬렉션
- Set : 순서가 없고, 멤버가 유일한 컬렉션

### 1. Array
- 멤버가 순서(index)를 가진 리스트 형태의 컬렉션 타입
- 여러가지 리터럴 문법을 활용할 수 있어 표현 방법이 다양하다.
#### ex01. Array 선언 및 생성
```swift
//Array 선언 및 생성
var integers: Array<Int> = Array<Int>()

// 동일한 표현 
// var integers: Array<Int> = [Int]()
// var integers: Array<Int> = []
// var integers: [Int] = Array<Int>()
// var integers: [Int] = [Int]()
// var integers: [Int] = []
// var integers = [Int]()
```

#### ex02. Array 활용
```swift
integers.append(1)
integers.append(100)

//Int 타입이 아니므로 Array에 추가할 수 없음
//integer.append(101.1)  // 실수(Double, float) 타입

print(integers) //[1, 100]

//멤버 포함 여부 확인 
print(integers.contains(100) // true
print(integers.contains(99) // false

//멤버 교체
integers[0] = 99

//멤버 삭제 
integers.remove(at:0)
integers.removeLast()
integers.removeAll()

//멤버 수 확인
print(integers.count)

// 인덱스를 벗어나 접근하려면 인셉션 런타임 오류발생
// integers[0]
```

#### ex03. 불변 Array:let을 사용하여 Array 선언
```swift
let immutableArray = [1,2,3]

// 수정이 불가능하므로 멤버를 추가하거나 삭제할 수 없다.
//immutableArray.append(4)
//immutableArray.removeAll()
```

### 2. Dictionary
- '키'와 값의 쌍으로 이루어진 컬렉션 타입
- Array와 비슷하게 여러가지 리터럴 문법을 활용할 수 있어 표현 방법이 다양하다.

#### ex01. Dictionary의 선언과 생성
```swift
// Key가 String 타입이고 Value가 Any인 빈 Dictionary 생성
var anyDictionary: Dictionary<String, Any> = [String: Any]()

//위와 동일한 표현
// var anyDictionary: Dictionary <String, Any> = Dictionary<String, Any>()
// var anyDictionary: Dictionary <String, Any> = [:]
// var anyDictionary: [String: Any] = [String, Any]()
// var anyDictionary: [String: Any] = [:]
// var anyDictionary = [String: Any]()
```

#### ex02. Dictionary 활용
```swift
// 키에 해당하는 값 할당
anyDictionary["someKey"] = "value"
anyDictionary["anotherKey"] = 100

print(anyDictionary) // ["someKey": "value", "anotherKey": 100]

// 키에 해당하는 값 변경
anyDictionary["someKey"] = "dictionary"
print(anyDictionary) ["someKey": "dictionary", "anotherKey": 100]

// 키에 해당하는 값 제거
anyDictionary.removeValue(forKey: "anotherKey")
anyDictionary["someKey"] = nil
print(anyDictionary)
```

#### ex03. 불변 Dictionay:let을 사용하여 Dictionary 선언
```swift
let emptyDictionary: [String: String] = [:]
let initalizedDictionary: [String:String] = ["name":"taetae", "gender":"male"]

// 불변 Dictionary이므로 값 변경 불가
// emptyDictionary["Key"] = "value"

// 키에 해다항하는 값을 다른 변수나 상수에 할당하고자 할 때는 옵셔널과 타입 캐스팅으로 다뤄야함.
// "name"이라는 키에 해당하는 값이 없을 수 있으므로 String 타입의 값이 나올 것이라는 보장이 없다.
// 컴파일 오류 발생
// let someValue: String = initalizedDictionary["name"]
```

### 3. Set
- 중복되지 않는 멤버가 순서없이 존재하는 컬렉션
- Array, Dictionary와 다르게 축약형이 존재하지 않음

#### ex01. Set 생성 및 선언
```swift
var integerSet: Set<Int> = Set<Int>()

// insert: 새로운 멤버 입력
// 동일한 값은 여러번 insert해도 한번만 저장된다.
integerSet.insert(1)
integerSet.insert(20)
integerSet.insert(99)
integerSet.insert(99)
integerSet.insert(99)
integerSet.insert(100)

print(integerSet) // {100, 99, 20, 1}

//contains: 멤버 포함 여부 확인
print(integerSet.contains(1) //true
print(integerSet.contains(2) //false

// remove : 멤버 삭제
integerSet.remove(99) // {100, 20, 1}
integerSet.romeveFirst() // {20, 1}

//count : 멤버 개수
integerSet.count // 2
```

#### ex02. Set의 활용 
- 멤버의 유일성이 보장되기 때문에 집합 연산에 활용하면 유용.
```swift
let setA: Set<Int> = [1, 2, 3, 4, 5]
let setB: Set<Int> = [3, 4, 5, 6, 7]

// 합집합
let union: Set<Int> = setA.union(setB)
print(union) // [2, 4, 5, 6, 7, 3, 1]

// 합집합 오름차순 정렬
let sortedUnion: [Int] = union.sorted()
print(sortedUnion) // [1, 2, 3, 4, 5, 6, 7]

// 교집합
let intersection: Set<Int> = setA.intersection(setB)
print(intersection) // [5, 3, 4]

// 차집합
let subtracting: Set<Int> = setA.subtracting(setB)
print(subtracting) // [2, 1]
```
