### Today I Learned (오늘 내가 배운 것)

Actually. It's just my stuggle of me about becoming developer.

Hope you enjoy :)

### Today I Learnd

-   2020-03-25

1. Flask-login 모듈의 loginManager는
   '''
   @login_manager.user_loader
   def load_user(user_id):
   return User.query.get(user_id)
   '''
   콜백을 통해 해당하는 데이터베이스의 유저를 로드해올 수 있고 HTML 템플릿에서
   current_user 를 자동으로 사용할 수 있게 해준다.
   current_user.is_authenticated = (True or False) 가 주로 사용 된다.

2. flask OAuth 구현하기
   -> OAuth 2.0
   -> flask-dance
   -> flask-OAuth

3. flask-wtf의 form.hidden_tag() 는 토큰을 포함하고 있어서 CSRF 공격을 방어할 수 있게 해준다.
   이떄 app.config['SECRET_KEY']에 SECRET_KEY가 등록되어있어야 한다.

-   2020-03-23

1. Flask-SQLAlchemy는 파이썬에서 가장 흔히 쓰이는 ORM이다.
2. ORM이란 파이썬으로 직접 SQL 신택스를 사용하는것 과 같은 효과를 준다.

-   2020-03-20

1. python class에서 print()함수나 len()함수를 사용하고 싶을 때
   -> print()함수는 class 메서드로
   def **repr**(self):
   return f"title: {self.title}, author: {self.author}"
   와 같은 형식으로 만들면 된다.

    -> len() 함수는 class 메서드로
    def **len**(self):
    return self.pages
    와 같은 형식으로 사용자가 len으로 리턴하고 싶은 값을 주면 된다.

2. python decorator로 wrap 함수를 넘겨주고 치장(?) 한 뒤 새로운 함수를 return한다
   여기서 @decorator_func_name 데코레이터를 wrap 함수 위에 선언하여 간단하게 사용할 수 있다.

3. 아나콘다 가상환경 리스트 알고 싶을 때
   -> conda env list

4. 아나콘다 각 가상환경에 설치된 패키지를 알고 싶을 때
   -> conda activate (env) 로 가상환경 진입 후
   -> (env) conda list

-   2020-03-17

1. node.js 에서 모듈화를 할 때에는 따로 .js 파일을 만든 뒤 exports = {want to exports} 와 같은 형식으로 모듈을 export 한다.
   이후에 require('파일 경로/exports.js') 와 같은 형태로 import 가능!

2. python에서 input()의 시간을 줄이고 싶을 때에는
   import sys
   input() == sys.stdin.readline() # 띄어쓰기와 \n까지 포함된다.
   여러줄을 받고 싶을 때엔 var inputVale = sys.stdin

3. script injection 공격을 막아내기 위해 node.js의 모듈인 sanitized-html을 사용할 수 있다.

4. 쿼리스트링에 ../ 와 같은 file 구조를 탐색하는 문자열 주입을 방지하기 위해 요청받은 쿼리스트링을 parse하여 요청 목적에 맞는 쿼리스트링만을 사용하는 것이 보안에 좋다
   require('path') 모듈에서 parse라는 함수를 사용하여 쿼리스트링을 파싱한다.

5. paper.js 로 어썸한 어트랙티브 인터랙션을 구현할 수 있다.

-   2020-02-25

1. Tuple list에 대해 정렬이 필요한 경우 그냥 sort하면 자동적으로 Tuple에 0번째 요소를 기준으로 정렬된다.
   그 외의 요소도 고려하고 싶은 경우엔 다음과 같이 사용한다
   sorted(tupleList, key = lambda x : (x[0].upper(), int(x[1], ... x[n])))
   -> 이 경우 순서대로 x[0].upper() 된 요소에 따라 정렬을 한 뒤
   -> int(x[1]) 값에 대하여도 정렬을 한다.. n 번째 까지 반복
   -> 안정 정렬(Stable)을 지원한다

-   2020-02-24

1. 튜플 list에서 튜플의 n번째 요소에 대한 max Tuple 찾기
   maxValueOfTupleList = max(tupleList, key = lambda i: i[n])
   -> i[n] 은 내가 정렬하고 max값의 기준을 삼을 Tuple의 열(column)
   -> maxValueOfTupleList는 n번째 요소를 기준으로 찾은 max Tuple이 할당된다.
