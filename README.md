# 알고리즘 공부

## 1) 시간 초과 방지
'input()'을 사용하면 시간 초과가 뜰 수 있음  
'sys.stdin.readline()'을 사용함으로써 시간 초과 방지  
'sys.stdin.readline()'을 사용하기 위해선 'import sys'를 맨 위에 써줘야 함  
<br>

## 2) EOFerror
- sys를 사용하는 방법
<pre>
import sys
lines = sys.stdin.readlines()
for line in lines:
    A, B = map(int, line.split())
    print(A + B)
</pre>

- EOFError 예외 처리
<pre>
while True:
    try:
        A, B = map(int, input().split())
        print(A + B)
    except EOFError:
        break
</pre>  
<br>

## 3) ctrl + r
pycharm에서 변수명 한 번에 바꾸기