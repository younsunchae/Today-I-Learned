### ✏️ 동반객체
특정 유형에 연결되지만 특정 객체에 연결되지는 않는 변수나 함수를 정의하는 메커니즘을 제공 <br/>
자바의 static 키워드를 사용하는 것과 유사하다. <br/>

```kotlin
class LoginFragment : Fragment() {

    ...

    companion object {
        private const val TAG = "LoginFragment"
    }
}
```
`LoginFragment`의 각 인스턴스에 `String`에 고유한 인스턴스가 필요하지 않으므로 동반 객체에서 정의해야 한다.

<br/>

### ✏️ 속성 위임
과도한 중복코드를 피하기 위해 사용
```kotlin
private val viewModel: LoginViewModel by viewModels()
```
앱 전체에서 재사용할 수 있는 일반적인 구현을 제공 <br/>
<br/>

### ✏️ 상호 운용성
`NullPointerException`이 발생할 가능성을 낮추고 null 검사의 횟수도 줄인다.<br/>
<br/>
### ✏️ 플랫폼 유형
`String!`는 String 과 String? 을 표시할 수 있고 컴파일러로 두 유형 중 하나의 값을 할당할 수 있다.<br/>
`@NonNull` 변수가 null이 될 수 없다는 것을 표시할 때 사용
```kotlin
public class Account implements Parcelable {
    public final @NonNull String name;
    ...
}
```
<br/>
 ```kotlin
 val account = Account("name", "type")
val accountName = account.name!!.trim()
```

`!!`는 왼쪽에 있는 모든 것을 null이 아닌 것으로 취급하므로 `name`을 null이 아닌 `String`으로 취급한다.<br/>
하지만 NullPointerException이 다시 발생될 수 있으므로
`?.`을 사용한다
```kotlin
val account = Account("name", "type")
val accountName = account.name?.trim()
```
안전 호출 연산자 `?.`을 사용하면 `name`이 null이 아닌 경우 `naem?.trim()`의 결과가 앞이나 뒤에 공백이 없는 이름값이고 
null이면 결과도 null이니 에러를 발생시킬 수는 없지만 null 값이 전달되므로<br/>
`?:`을 사용하여 즉시 null  사례를 처리한다.

```kotlin
val account = Account("name", "type")
val accountName = account.name?.trim() ?: "Default name"
```
