# 🎮 Typing Test Game

콘솔 기반 타자 연습 게임입니다. 사용자 인증, 회원관리, 관리자 기능, 스테이지별 난이도 상승 등 다양한 기능을 제공하는 JDBC 기반 콘솔 게임입니다.

<br>

## 📌 프로젝트 개요
 
**Typing Test Game**은 콘솔 화면에 나타나는 무작위 문자열을 제한 시간 내에 정확하게 입력하는 게임입니다.  
단계가 올라갈수록 문제 수와 난이도가 증가하며, 성공한 최고 스테이지가 최종 점수로 기록됩니다.

### 주요특징 
- ✅ 콘솔 UI 기반 실행
- ✅ 회원가입 / 로그인 시스템
- ✅ 관리자 모드 제공
- ✅ 사용자별 최고 기록 저장
- ✅ JDBC를 활용한 데이터베이스 연동

<br>

## 🕹️ 게임 규칙

1. **문제 출제**: 무작위 문자열(알파벳, 숫자, 특수문자 포함)이 출력됩니다
2. **제한 시간**: 각 단계마다 **20초** 제한
3. **정답 처리**: 정확히 입력하면 통과, 오답 시 재입력 가능
4. **게임 종료**: 시간초과 시 즉시 게임 종료
5. **난이도**: 스테이지 번호만큼 문제 수 증가 (1단계 → 1문제, 2단계 → 2문제)

<br>

## 🧩 단계별 구성

| 단계 | 문제 수 | 문자열 길이 |
|:---:|:------:|:---------:|
| 1   | 1개    | 5자       |
| 2   | 2개    | 5~10자    |
| 3   | 3개    | 5~10자    |
| ... | ...    | ...       |

<br>

## 🛠️ 기술 스택

- **Language**: Java 11+
- **Database**: JDBC (Oracle / MySQL)
- **UI**: Console Based

<br>

## 📁 프로젝트 구조
```
C:.
├─resources
│  ├─driver.properties       # DB 연결 설정
│  └─query.xml               # SQL 쿼리 모음
└─src/com/my/jdbc
   ├─controller
   │   ├─ScoreController.java
   │   └─UserController.java
   ├─game
   │   ├─AdminAdjustment.java
   │   ├─PlayGame.java
   │   └─Rule.java
   ├─model
   │   ├─dao
   │   │   ├─ScoreDao.java
   │   │   └─UserDao.java
   │   └─vo
   │       └─User.java
   ├─run
   │   └─Run.java
   └─view
       └─GameUserMenu.java
```

<br>

## 🚀 실행 방법

1. 프로젝트를 IDE(Eclipse/IntelliJ)로 임포트
2. `resources/driver.properties`에서 DB 연결 정보 설정
3. `src/com/my/jdbc/run/Run.java` 실행
4. 콘솔 메뉴를 따라 게임 시작

<br>

## 🎬 실행 예시

### 🔐 관리자 로그인
```
============ Typing Test ============
1. 로그인
2. 회원 가입
3. 관리자 
메뉴 입력 : 3
관리자키 번호 입력 : 777
인증 성공!

============ 관리자 메뉴 ============
1. 전체 회원 정보 확인
2. 아이디로 회원 찾기
3. 초기화면으로 돌아가기
메뉴 입력 : 1

[회원 목록 출력...]
User [userNo=1, userId=user01, ...]
User [userNo=2, userId=user02, ...]
```

### 🧑 회원 가입
```
========= 회원 추가 ===========
아이디 : user05
비밀번호 : pass05
이름 : 이순신
성별(M,F) : M
나이 : 44
이메일 : user05@naver.com
전화번호 : 01055555555

서비스 요청 성공 : 성공적으로 회원이 추가되었습니다.
```

### 🔓 로그인
```
========= 로그인 ===========
아이디 : user05
비밀번호 : pass05
로그인 성공! 게임 메뉴로 이동합니다.
```

### 🎮 게임 진행
```
========= 단계 1 =========
문제: e*$#C
입력: e*$#C
단계 1 성공!

========= 단계 2 =========
문제 1: 0XbT+
입력: 0XbT+
문제 2: %DN-O
입력: %DN-O
단계 2 성공!

========= 단계 4 =========
문제 1: sAvla
입력: ssssss → 오답
입력: sAvla → 정답
문제 2: G+txw
입력: ggggg → 오답

시간 초과! 실패
게임 종료! 총 성공 단계: 3
```

### 🏆 랭킹 확인
```
========= 전체 랭킹 =========
user01 → 5 stage
user03 → 4 stage
user05 → 3 stage
user02 → 3 stage
```

<br>

## 📚 주요 기능

### 사용자 기능
- 회원 가입 및 로그인
- 개인 정보 수정
- 게임 플레이
- 랭킹 조회
- 게임 규칙 확인

### 관리자 기능
- 전체 회원 정보 조회
- 특정 회원 검색
- 회원 관리

### 게임 시스템
- 스테이지별 난이도 증가
- 실시간 타이머
- 점수 기록 및 저장
- 오답 재입력 기능

<br>

## 📝 License

This project is open source and available under the [MIT License](LICENSE).
