# 4과목: 프로그래밍 언어 활용

## 📌 과목 개요
C, Java, Python 등 프로그래밍 언어의 기본 문법과 활용을 다룹니다.

## 📚 주요 학습 내용

### 1. 서버 프로그램 구현
- **개발 환경 구축**
  - 웹 서버: Apache, Nginx, IIS
  - WAS: Tomcat, WebLogic, JEUS

- **서버 프로그램 구현**
  - MVC 패턴
  - DTO, DAO, VO

### 2. 프로그래밍 언어 활용
- **기본 문법**
  - 변수, 자료형
  - 연산자
  - 제어문 (조건문, 반복문)

- **언어별 특징**
  - C: 절차지향, 포인터
  - Java: 객체지향, JVM
  - Python: 인터프리터, 간결성

- **라이브러리**
  - 표준 라이브러리
  - 외부 라이브러리

### 3. 응용 SW 기초 기술 활용
- **운영체제**
  - 프로세스 vs 스레드
  - 스케줄링 (FCFS, SJF, RR, Priority)
  - 메모리 관리 (페이징, 세그먼테이션)
  - 교착상태 (Deadlock)

- **네트워크**
  - OSI 7계층
  - TCP/IP 4계층
  - IP 주소 체계
  - 프로토콜 (TCP, UDP, HTTP, FTP)

## 🎯 핵심 키워드

### C 언어 기본 문법
```c
// 포인터
int *ptr;
int arr[5];
ptr = arr;  // 배열명은 주소

// 구조체
struct Student {
    char name[20];
    int age;
};

// 파일 입출력
FILE *fp;
fp = fopen("file.txt", "r");
fclose(fp);
```

### Java 기본 문법
```java
// 클래스
public class Student {
    private String name;
    private int age;

    // 생성자
    public Student(String name, int age) {
        this.name = name;
        this.age = age;
    }

    // getter/setter
    public String getName() { return name; }
}

// 상속
class Student extends Person { }

// 인터페이스
interface Drawable {
    void draw();
}
```

### Python 기본 문법
```python
# 리스트
arr = [1, 2, 3, 4, 5]
arr.append(6)

# 딕셔너리
dict = {"name": "홍길동", "age": 20}

# 함수
def sum(a, b):
    return a + b

# 클래스
class Student:
    def __init__(self, name, age):
        self.name = name
        self.age = age
```

### 스케줄링 알고리즘
| 알고리즘 | 설명 | 특징 |
|---------|------|------|
| FCFS | First Come First Served | 선입선출, 비선점 |
| SJF | Shortest Job First | 실행시간 짧은 것 우선 |
| RR | Round Robin | 시간 할당량(Time Quantum) |
| Priority | 우선순위 | 우선순위 높은 것 먼저 |

### OSI 7계층
1. **물리 계층** (Physical): 비트 전송
2. **데이터링크 계층** (Data Link): 프레임, MAC 주소
3. **네트워크 계층** (Network): IP, 라우팅
4. **전송 계층** (Transport): TCP, UDP
5. **세션 계층** (Session): 세션 관리
6. **표현 계층** (Presentation): 암호화, 압축
7. **응용 계층** (Application): HTTP, FTP, SMTP

### 교착상태 발생 조건 (모두 만족해야 발생)
1. **상호 배제** (Mutual Exclusion)
2. **점유와 대기** (Hold and Wait)
3. **비선점** (No Preemption)
4. **순환 대기** (Circular Wait)

## 📝 학습 체크리스트
- [ ] C/Java/Python 기본 문법 숙지
- [ ] 프로세스 스케줄링 알고리즘 이해
- [ ] OSI 7계층 순서 암기
- [ ] TCP vs UDP 차이점 정리
- [ ] 교착상태 조건 4가지 암기
- [ ] 페이징/세그먼테이션 개념 이해

## 💡 암기 팁
- **OSI 7계층**: "물데네전세표응" (물리-데이터링크-네트워크-전송-세션-표현-응용)
- **교착상태**: "상점비순" (상호배제-점유대기-비선점-순환대기)
- **FCFS**: 먼저 온 것부터 (First Come First Served)
- **RR**: 돌아가면서 (Round Robin)

## ⚠️ 실기 연계
- C언어 코드 분석 문제 자주 출제
- Python 간단한 코드 작성 문제 출제 가능
- 알고리즘 개념 문제 출제
