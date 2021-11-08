---
layout: post
title:  "Oracle DB 교육 1일차"
date:   2021-03-02
excerpt: "Oracle DB 수업(1)"
tag:
- jekyll 
- moon
- blog
- about
- theme
#feature: http://i.imgur.com/Ds6S7lJ.png
comments: true
---

# Oracle DB 교육 (1일차)

- 교육환경 셋팅. 12.2.0.1 / X E version(18cXE)

  - WS1 - basic - 3 day

  - WS2 - advanced - 2day

- 목표
  - SQL : Structured Query Language 를 배운다.
    - Relational Database data ( 관계형 데이터 베이스 ) acess/manage
    - select / insert / update / delete ( DML )
    - create / alter / drop (DDL)

---

- version

  - 12.2.0.1 버젼 이후 version 배포 명명법이 바뀜 -> 바로 18c

- 이론 내용.
<figure>
    <a href="{{ site.url }}/assets/img/SQL/oracle1.png"><img src="{{ site.url }}/assets/img/SQL/oracle1.png" width="50" height="30"></a>
</figure>

  - DB

    - 정보  : 알게된 모든 사실
    - 데이터 : 업무에 필요한 정보
    - 데이터베이스 : 업무에 필요한 정보를 저장
    - DBMS - 데이터베이스에 저장된 데이터를 관리 및 조회

  - RDB 

    - hierarchical, network DBMS 이후 나옴 

    -  2차원 테이블로 관리하기때문에 사용하기 편리함!

      <figure>
    <a href="{{ site.url }}/assets/img/SQL/oracle2.png"><img src="{{ site.url }}/assets/img/SQL/oracle2.png" width="50" height="30"></a>
    </figure>

    - RDBMS - Oracle, DB2, MySQL  등

  - Data Models

    <figure>
    <a href="{{ site.url }}/assets/img/SQL/oracle3.png"><img src="{{ site.url }}/assets/img/SQL/oracle3.png" width="50" height="30"></a>
    </figure>

    - DB 설계 (Modeling) - Table 생성을 위한 설계
      - 구체적인 업무 설계
      - Entity -  relation - Table
      - attribute                 column
      - relationship           foreign Key 등

  - SQL 용어

<figure>
    <a href="{{ site.url }}/assets/img/SQL/oracle4.png"><img src="{{ site.url }}/assets/img/SQL/oracle4.png" width="50" height="30"></a>
  </figure>

---

- 실습

  - SQL Develper

  - sql*plus

    - 접속 방법 : ora1/[password]@localhost:1521/xepdb1
      - CMD에서 접속할 경우 : sqlplus ora1/oracle_4U@localhost:1521/xepdb1
    - 테이블 확인 : select * from tab;

  - Select 명령어

    - row 단위 접근 후 검색하고자 하는 컬럼 추출
    - select * from dual -> dual 테이블은 모든 user가 불러서 사용할 수 있는 공유 table
    - 대소문자 구분하지 않음.
    - 한줄에 쭉 써도 좋으나, 구분하여 보기 위해 줄바꿈하여 작성 권장.
    -  " ; " 실행하고자 하는 명령어 구분자. ( 여러 명령어를 작성할때 구분하여 실행하기 위함)

  - 타입 특징

    - varchar2 - 문자

    - number - 숫자 / 사칙연산 가능

    - date - 날짜 / 더하기 빼기 가능

    - null 

      - 적용할 수 없는 경우
      - 알려지지 않은 경우

    - Select 절의 실행 순서

      3. SELECT

      1. FROM
      2. WHERE

      4. ORDER BY

-----

- 실습 쿼리 (Alias)

```sql
SELECT department_id depart
    , employee_id as employee
    ,last_name "name"
    ,salary*12 as "A sal"
    FROM employees;
```

<figure>
    <a href="{{ site.url }}/assets/img/SQL/sql1.png"><img src="{{ site.url }}/assets/img/SQL/sql1.png" width="50" height="30"></a>
</figure>

- Concat

```sql
SELECT last_name||commission_pct
    ,last_name
    ,commission_pct
    FROM employees;
```

<figure>
    <a href="{{ site.url }}/assets/img/SQL/sql2.png"><img src="{{ site.url }}/assets/img/SQL/sql2.png" width="50" height="30"></a>
</figure>

```sql
select last_name || ' is a ' || job_id AS detila
    from employees;
```

<figure>
    <a href="{{ site.url }}/assets/img/SQL/sql3.png"><img src="{{ site.url }}/assets/img/SQL/sql3.png" width="50" height="30"></a>
</figure>

```sql
select last_name || '''s a ' || job_id AS detila
    from employees;
```

<figure>
    <a href="{{ site.url }}/assets/img/SQL/sql4.png"><img src="{{ site.url }}/assets/img/SQL/sql4.png" width="50" height="30"></a>
</figure>

```sql
select last_name || q'['s ]' || job_id AS detila
    from employees;

select last_name || q'('s )' || job_id AS detila
    from employees;
```

<figure>
    <a href="{{ site.url }}/assets/img/SQL/sql5.png"><img src="{{ site.url }}/assets/img/SQL/sql5.png" width="50" height="30"></a>
</figure>

- select 시 값을 입력 하면?

  - departments 의 row는 총 8줄임.

  ```sql
  SELECT sysdate, 1, 'a'
      FROM departments;    
  ```

  <figure>
    <a href="{{ site.url }}/assets/img/SQL/sql6.png"><img src="{{ site.url }}/assets/img/SQL/sql6.png" width="50" height="30"></a>
  </figure>

  - dual table은 1 row attribute를 갖는 table로 oracle에서 만들었음.

  ```sql
  SELECT sysdate
      FROM DUAL;
  ```

  <figure>
    <a href="{{ site.url }}/assets/img/SQL/sql7.png"><img src="{{ site.url }}/assets/img/SQL/sql7.png" width="50" height="30"></a>
  </figure>

- WHERE 절의 사용

  - 기본 "=" 사용 
    - 유의사항 : 대소문자 구분하므로 오타 시 에러가 나지 않고 데이터를 못 찾음.

  ```sql
  select employee_id, salary
      from employees
      where department_id = 90;
      
  select employee_id, salary
      from employees
      where last_name = 'Whalen';
  ```

  - IN 사용

  ```sql
  select *
      from employees
      where manager_id in (100,101,201);
  ```

  - BETWEEN 사용
    - 유의 사항 : 사이 값이므로 항상 BETWEEN 작은 값 AND 큰 값 으로 입력해야 함.

  ```sql
  select employee_id, hire_date, salary
      from employees
      where salary between 2500 and 3500;
  -- 2500 <= salary <= 3500; 
  ```

  - LIKE 사용
    - Pattern을 찾아주는 연산자라고도 함. 
      - first_name이 S로 시작하는 조건

  ```sql
  select first_name
      from employees
      where first_name LIKE 'S%';
  -- Like : % 길이가 0 이상인 문자열 대신    
  ```

  ```sql
  select first_name
      , hire_date
      from employees
      where hire_date like '09%';
  -- date format이 RR/MM/DD 라서 제일 앞 09년도 조건이 나오는 것
  -- where department_id like '9%';
  -- department_id 를 oracle에서 자동으로 문자로 바꿈   
  ```

  - Order By

  ```sql
  -- select 3번째 항목으로 Ascending
  select last_name, job_id, department_id, hire_date
      from employees
      order by 3;
      
  -- 각 컬럼별로 asc, dsc 지정 해줘야함
  select last_name, job_id, department_id, salary
      from employees
      order by department_id desc, salary desc; 
  
  -- null 으 큰값으로 해서 정렬
  select employee_id, commission_pct
      from employees
      order by commission_pct desc;
      
  select employee_id, commission_pct
      from employees
      order by commission_pct asc;
  
  -- null값 먼저 출력 후 asc
  select employee_id, commission_pct
      from employees
      order by commission_pct nulls first;
  ```

  - fetch [first or next] [5 or 5 percent] row [only or with ties]

  ```sql
  select employee_id, commission_pct
      from employees
      offset 4 rows -- 앞에 4줄 건너 뛰고
      fetch first 5 row only; -- 5줄 가져와라
  
  select employee_id, commission_pct
      from employees
      offset 4 rows -- 앞에 4줄 건너 뛰고
      fetch first 5 percent row only; -- 5% 만 가져와라. 1건임
      
  select employee_id, salary
      from employees
      order by salary desc
      fetch first 2 row with ties; -- 2건 가져오는데 동점이면 다 가져와라    
  ```

  - 치환 변수
    - 변수만 바꿔서 실행하는 경우에 효과적임.

  ```sql
  select *
      from employees
      where department_id = &d_id;
  
  select &c_name -- column 명을 입력받아서 보여줌!
      from employees
      where department_id = &d_id;  
  ```

  

