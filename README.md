### Today I Learned (오늘 내가 배운 것)

Actually. It's just my stuggle of me about becoming developer. 

Hope you enjoy :)


### Today I Learnd

- 2020-03-17
1. node.js 에서 모듈화를 할 때에는 따로 .js 파일을 만든 뒤 exports = {want to exports} 와 같은 형식으로 모듈을 export 한다.
   이후에 require('파일 경로/exports.js') 와 같은 형태로 import 가능!

2. python에서 input()의 시간을 줄이고 싶을 때에는 
   import sys
   input() == sys.stdin.readline() # 띄어쓰기와 \n까지 포함된다.
   여러줄을 받고 싶을 때엔 var inputVale = sys.stdin

3. script injection 공격을 막아내기 위해 node.js의 모듈인 sanitized-html을 사용할 수 있다.

4. 쿼리스트링에 ../ 와 같은 file 구조를 탐색하는 문자열 주입을 방지하기 위해 요청받은 쿼리스트링을 parse하여 요청 목적에 맞는 쿼리스트링만을 사용하는 것이 보안에 좋다
   require('path') 모듈에서 parse라는 함수를 사용하여 쿼리스트링을 파싱한다.

- 2020-02-25
1. Tuple list에 대해 정렬이 필요한 경우 그냥 sort하면 자동적으로 Tuple에 0번째 요소를 기준으로 정렬된다.
  그 외의 요소도 고려하고 싶은 경우엔 다음과 같이 사용한다
  sorted(tupleList, key = lambda x : (x[0].upper(), int(x[1], ... x[n])))
  -> 이 경우 순서대로 x[0].upper() 된 요소에 따라 정렬을 한 뒤
  -> int(x[1]) 값에 대하여도 정렬을 한다.. n 번째 까지 반복
  -> 안정 정렬(Stable)을 지원한다

- 2020-02-24
1. 튜플 list에서 튜플의 n번째 요소에 대한 max Tuple 찾기
  maxValueOfTupleList = max(tupleList, key = lambda i: i[n])
  -> i[n] 은 내가 정렬하고 max값의 기준을 삼을 Tuple의 열(column)
  -> maxValueOfTupleList는 n번째 요소를 기준으로 찾은 max Tuple이 할당된다.
