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
<br> 

## 4) .strip()를 사용하는 이유
<pre>
import sys

N = int(input())
for i in range(N):
    1) word = list(sys.stdin.readline())
    2) word = list(sys.stdin.readline().strip())
    print(word)

결과 1)  
['A', 'C', 'D', 'K', 'J', 'F', 'O', 'W', 'I', 'E', 'G', 'H', 'E', '\n']  
['O', '\n']  
['A', 'B']  

결과 2) \n를 없애기 위해  
['A', 'C', 'D', 'K', 'J', 'F', 'O', 'W', 'I', 'E', 'G', 'H', 'E']  
['O']  
['A', 'B']  
</pre>  
<br>

## 5) join
배열 안에 있는 원소들 합쳐서 한 단어로 만들 수 있음
<pre>
answer = ['AAA', 'BBB', 'CCC']
print("".join(answer))

결과)  
AAABBBCCC
</pre>  
<br>

## 6) Stack (출처 : https://wikidocs.net/192069)
- 마지막에 쌓아 올린 자료를 먼저 꺼냄
- 후입선출(Last In First Out) 구조
<pre>
- push(x): 자료 x를 넣는 작업, 연결 리스트의 appendleft와 같다.
- pop(): 자료를 꺼내는 작업, 연결 리스트의 popleft와 같다.
- peek(): 마지막에 넣은 자료를 확인하는 작업으로 pop과 비슷하지만, 값을 제거하지 않음
- is_empty(): 빈 스택인지 확인하는 작업
<hr>
class Stack:
    def __init__(self):
        self.top = None

    def push(self, data):
        node = Node(data)
        if self.top is None:
            self.top = node
        else:
            node.next = self.top
            self.top = node

    def pop(self):
        if self.top is None:
            return None
        node = self.top
        self.top = node.next
        return node.data

    def peek(self):
        if self.top is None:
            return None
        return self.top.data

    def is_empty(self):
        return self.top is None
</pre>  
<br>

## 7) 알파벳 배열로 나타내기
<pre>
from string import ascii_lowercase

alphabet = list(ascii_lowercase)
print(alphabet)

결과)  
['a', 'b', 'c', 'd', 'e', 'f', 'g', 'h', 'i', 'j', 'k', 'l', 'm', 'n', 'o', 'p', 'q', 'r', 's', 't', 'u', 'v', 'w', 'x', 'y', 'z']  
</pre>
<br>