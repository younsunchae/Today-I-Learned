# switch문

복수의 `if` 조건문은 `switch`문으로 바꿀 수 있다.

```jsx
switch(x) {
  case 'value1':  // if (x === 'value1')
    ...
    [break]

  case 'value2':  // if (x === 'value2')
    ...
    [break]

  default:
    ...
    [break]
}
```
- `break`문을 만나거나 `switch` 문이 끝나면 코드의 실행은 멈춘다.
- 값과 일치하는 `case`문이 없다면, `default`문 아래의 코드가 실행된다(`default` 문이 있는 경우).
- `case`문 안에 `break`문이 없으면 조건에 부합하는지 여부를 따지지 않고 이어지는 `case`문을 실행한다.

## 💛 여러 개의 case 문 묶기

```jsx
case 3: // (*) 두 case문을 묶음
  case 5:
    alert('계산이 틀립니다!');
    alert("수학 수업을 다시 들어보는걸 권유 드립니다.");
    break;
```

## 💛 자료형의 중요성
```jsx
let arg = prompt("값을 입력해주세요.");
switch (arg) {
  case '0':
  case '1':
    alert( '0이나 1을 입력하셨습니다.' );
    break;

  case '2':
    alert( '2를 입력하셨습니다.' );
    break;

  case 3:
    alert( '이 코드는 절대 실행되지 않습니다!' );
    break;
  default:
    alert( '알 수 없는 값을 입력하셨습니다.' );
}
```
1. 0이나 1을 입력한 경우엔 첫 번째 `alert`문이 실행된다.
2. 2를 입력한 경우엔 두 번째 `alert`문이 실행됩니다.
3. 3을 입력하였더라도 세 번째 `alert`문은 실행되지 않는다. <br />
   앞서 배운 바와 같이 `prompt` 함수는 사용자가 입력 필드에 기재한 값을 문자열로 변환해 반환하기 때문에 숫자 `3`을 입력하더라도 `prompt` 함수는 문자열 '3'을 반환한다. <br />
   그런데 세 번째 `case`문에선 사용자가 입력한 값과 숫자형 `3`을 비교하므로, **형 자체가 다르기 때문에 `case 3` 아래의 코드는 절대 실행되지 않고 `default`문이 실행된다.**

