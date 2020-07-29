## :runner: Day01

### :page_with_curl: ex00 명명법
- Camel Case ?  
	합쳐진 부분마다 맨 처음 글자를 대문자로 표기하는 방법
- Lower Camel Case : 각 단어의 첫 문자를 대문자로 표시하되, 이름의 첫문자는 소문자로 적는다.  
	function, method, variable, constant  
	ex) myName, someVariable
- Upper Camel Case : 전체 이름의 첫 문자를 포함한 각 단어의 첫 문자를 대문자로 표시한다. PascalCase라고도 불린다.  
	type (class, struct, enum, extension ...)  
	ex) Person, Day, Point 

### :page_with_curl: ex01 콘솔 로그남기기
- print 함수: 단순 문자열 출력
- dump 함수: 인스턴스의 자세한 설명(description 프로퍼티)까지 출력

### :page_with_curl: ex02 문자열 보간법
- 프로그램 실행 중 문자열 내 변수 또는 상수를 값을 표현하기 위해 사용  
	\\()

'''swift
import Swift

let age: Int = 10
"안녕하세요 ! 저는\(age)살 입니다"
"안녕하세요 ! 저는\(age + 20)살 입니다"

print("안녕하세요 저는\(age + 5)살 입니다.")
print("\n###################\n")
class Person {
	var name: String = "taetae"
	var age: Int = 30
}

let taetae: Person = Person()

print(taetae)
print("\n####################\n")
dump(taetae)
'''
