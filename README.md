# Typing Test Game

## 🎮 개요
Typing Test Game은 **콘솔 기반의 타자 연습 게임**입니다.  
화면에 나타나는 무작위 문자열을 제한 시간 내에 정확히 입력하는 것이 목표이며, 난이도와 단계가 점점 상승합니다.  
JSP/Java 프로젝트 구조를 기반으로 **객체지향적 설계**와 **데이터 관리(DB 연동)** 기능을 포함하고 있습니다.

---

## 📝 주요 기능

### 1. 게임 규칙
- 화면에 나타나는 문자열을 제한 시간 내 정확히 입력
- 문자열 구성: 알파벳 대/소문자, 숫자, 특수문자
- 게임은 여러 단계(Stage)로 진행, 단계별 문제 수 증가
- 각 단계 제한 시간: 20초 (변경 가능)
- 정확히 입력해야 통과, 오답 시 재입력 가능
- 제한 시간 초과 시 게임 종료
- 클리어 단계 수가 최종 점수로 기록

**자세한 룰 클래스:** `src/com/my/jdbc/game/Rule.java`

---

### 2. 단계 및 문제 구성
| 단계 | 문제 수 | 문자열 길이 |
|------|----------|------------|
| 1    | 1        | 5          |
| 2    | 2        | 5~10       |
| 3    | 3        | 5~10       |
| ...  | ...      | ...        |

---

### 3. 데이터 관리
- 사용자 정보 및 점수 관리: `User.java`, `ScoreDao.java`, `UserDao.java`
- 점수, 사용자 기록 DB 연동 가능
- SQL 쿼리 파일: `resources/query.xml`

---

## 🛠️ 프로젝트 구조
C:.
├─bin
├─resources
│ ├─driver.properties # DB 연결 설정
│ └─query.xml # SQL 쿼리 모음
└─src
└─com/my/jdbc
├─controller
│ ├─ScoreController.java # 점수 관련 요청 처리
│ └─UserController.java # 사용자 관련 요청 처리
├─game
│ ├─AdminAdjustment.java # 관리자 게임 설정
│ ├─PlayGame.java # 게임 진행 로직
│ └─Rule.java # 게임 규칙 출력
├─model
│ ├─dao
│ │ ├─ScoreDao.java # 점수 DB 접근
│ │ └─UserDao.java # 사용자 DB 접근
│ └─vo
│ └─User.java # 사용자 VO 클래스
├─run
│ └─Run.java # 게임 시작 진입점
├─service
│ ├─ScoreService.java # 점수 비즈니스 로직
│ └─UserService.java # 사용자 비즈니스 로직
└─view
└─GameUserMenu.java # 콘솔 메뉴 UI

## 🚀 실행 방법
1. 프로젝트를 IDE(Eclipse, IntelliJ 등)로 임포트
2. DB 설정 파일(`resources/driver.properties`) 수정
3. `Run.java` 실행
4. 콘솔 메뉴에 따라 게임 시작

---

## 💡 사용 클래스
- **Run.java** : 게임 시작 진입점
- **PlayGame.java** : 게임 로직, 점수 계산
- **Rule.java** : 게임 규칙 출력
- **GameUserMenu.java** : 콘솔 메뉴 UI
- **ScoreDao/UserDao** : DB 연동
- **ScoreService/UserService** : 비즈니스 로직 처리

---

## 📌 기술 스택
- Java 11 이상
- JDBC (DB 연동)
- 콘솔 UI 기반
