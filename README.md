# TypeScript

## 11 22 typescript 정리

- 타입 스크립트 vs 자바 스크립트
    - 타입스크립트 는 자바스크립트 보다 확장된 언어
    - 기능 확장은 아니며, 정적 타입 기능이 추가됨
    - 이때 자바스크립트는 동적 타입 언어, 함수 선언 시점에는 타입이 정해지지 않으며 매개변수가 몇 개인지만 알고 있음, 따라서 이 함수를 어떻게 사용하는지에 대한 정보가 없음
    - 타입스크립트는 브라우저에서 실행되지 않으므로.타입스크립트 컴파일러로 컴파일 과정이 필요하다.
- 자바스크립트의 타입형
    - primitive : number, string, boolean
        
        ```tsx
        표현 형식
        let age: number;
        let name: string; 
        let code: any; # any의 경우 타입을 따로 지정하지 않는다. 일반적인 자바스크립트
        ```
        
    - complex - array, object
        
        ```tsx
        let hobbies: string[]
        let person: {
        	name: string,
        	age: number
        }
        let people: {
        	name: string,
        	age: number
        }[]
        ```
        
 - Type Inference 명시한 타입 표기가 없어도, 타입스크립트는 할당된 값의 자료형을 검사하여 그 타입인 값만 사용함
        
     ```tsx
    let course = 'React'
    course = 1234 # 이럴 시 오류 
     ```
        
 - union type 타입을 정의할 때 여러 개의 타입을 사용가능
        
    ```
    let coures: string|number|boolean
     ```
        
- Type allias 복잡한 타입을 설정하고 재사용
        
    ```tsx
    type Person = {
        name: string,
        age: number
    } # 이는 타스만 있으므로, 컴파일시에 자바스크립트 파일에서는 사라짐
    let people = Person[]
     ```
        
- 함수 - 매개변수에 타입 설정은 필수이며, return 값은 타입추론으로 자동으로 타입이 결정됨, 단 이를 지정할 수도 있음(명시 가능)
     - 함수의 리턴값이 없는 경우를 **void**라고 하며, 항상 함수에서 결합해서 사용, 혹시나 사용하려면 undefined으로 작업해야함



- generic 함수에서 사용되며, 인수의 들어온 값을 정확하게 판단할 필요가 있을 때 사용, 배열이 구성하는 원소와 추가하는 원소가 같은 타입인지 검사
        
     ```tsx
        function insertAt<T>(array:T[], value:T){
        		const newArray = [value, ...array]
        		return newArray
        }
        
     ```