input이나 output 둘 중 하나라도 없으면 작동이 안되는 것 같다. 확실하진 않지만 시도해본 결과 그렇다.

================

아웃풋 중복 불가 >> 같은 아웃풋에 대해 여러개 콜백함수 사용불가

"In the callback for output(s):
  no_use_w_input.value
Output 0 (no_use_w_input.value) is already in use.
Any given output can only have one callback that sets it.
To resolve this situation, try combining these into
one callback function, distinguishing the trigger
by using `dash.callback_context` if necessary."


