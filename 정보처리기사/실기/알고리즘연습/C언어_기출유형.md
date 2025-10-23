# C언어 기출 유형 정리

## 📌 포인터

### 기본 포인터
```c
#include <stdio.h>

int main() {
    int a = 10;
    int *p;
    p = &a;

    printf("%d\n", a);    // 10
    printf("%d\n", *p);   // 10
    printf("%d\n", &a);   // 주소값
    printf("%d\n", p);    // 주소값

    *p = 20;
    printf("%d\n", a);    // 20

    return 0;
}
```

### 포인터 연산
```c
#include <stdio.h>

int main() {
    int arr[5] = {10, 20, 30, 40, 50};
    int *p = arr;

    printf("%d\n", *p);       // 10
    printf("%d\n", *(p+1));   // 20
    printf("%d\n", *(p+2));   // 30

    p++;
    printf("%d\n", *p);       // 20

    return 0;
}
```

## 📌 배열

### 1차원 배열
```c
#include <stdio.h>

int main() {
    int arr[5] = {1, 2, 3, 4, 5};

    // 배열 출력
    for(int i = 0; i < 5; i++) {
        printf("%d ", arr[i]);  // 1 2 3 4 5
    }

    // 배열 합
    int sum = 0;
    for(int i = 0; i < 5; i++) {
        sum += arr[i];
    }
    printf("%d\n", sum);  // 15

    return 0;
}
```

### 2차원 배열
```c
#include <stdio.h>

int main() {
    int arr[2][3] = {{1, 2, 3}, {4, 5, 6}};

    for(int i = 0; i < 2; i++) {
        for(int j = 0; j < 3; j++) {
            printf("%d ", arr[i][j]);
        }
        printf("\n");
    }
    // 출력:
    // 1 2 3
    // 4 5 6

    return 0;
}
```

## 📌 문자열

### 문자열 기본
```c
#include <stdio.h>
#include <string.h>

int main() {
    char str1[] = "Hello";
    char str2[20] = "World";

    printf("%s\n", str1);           // Hello
    printf("%d\n", strlen(str1));   // 5

    // 문자열 복사
    strcpy(str2, str1);
    printf("%s\n", str2);           // Hello

    // 문자열 연결
    strcat(str1, str2);
    printf("%s\n", str1);           // HelloHello

    // 문자열 비교
    int result = strcmp(str1, str2);
    printf("%d\n", result);         // 0이면 같음

    return 0;
}
```

### 문자열 처리
```c
#include <stdio.h>

int main() {
    char str[] = "Hello World";

    // 문자 하나씩 출력
    for(int i = 0; str[i] != '\0'; i++) {
        printf("%c ", str[i]);
    }
    // H e l l o   W o r l d

    return 0;
}
```

## 📌 반복문

### for 문
```c
#include <stdio.h>

int main() {
    // 기본 for문
    for(int i = 0; i < 5; i++) {
        printf("%d ", i);  // 0 1 2 3 4
    }

    // 역순
    for(int i = 5; i > 0; i--) {
        printf("%d ", i);  // 5 4 3 2 1
    }

    // 짝수만
    for(int i = 0; i < 10; i += 2) {
        printf("%d ", i);  // 0 2 4 6 8
    }

    return 0;
}
```

### while 문
```c
#include <stdio.h>

int main() {
    int i = 0;
    while(i < 5) {
        printf("%d ", i);  // 0 1 2 3 4
        i++;
    }

    return 0;
}
```

### do-while 문
```c
#include <stdio.h>

int main() {
    int i = 0;
    do {
        printf("%d ", i);  // 0 1 2 3 4
        i++;
    } while(i < 5);

    return 0;
}
```

## 📌 조건문

### if 문
```c
#include <stdio.h>

int main() {
    int score = 85;

    if(score >= 90) {
        printf("A\n");
    } else if(score >= 80) {
        printf("B\n");  // 출력
    } else if(score >= 70) {
        printf("C\n");
    } else {
        printf("F\n");
    }

    return 0;
}
```

### switch 문
```c
#include <stdio.h>

int main() {
    int num = 2;

    switch(num) {
        case 1:
            printf("One\n");
            break;
        case 2:
            printf("Two\n");  // 출력
            break;
        case 3:
            printf("Three\n");
            break;
        default:
            printf("Other\n");
    }

    return 0;
}
```

## 📌 함수

### 기본 함수
```c
#include <stdio.h>

int add(int a, int b) {
    return a + b;
}

int main() {
    int result = add(10, 20);
    printf("%d\n", result);  // 30

    return 0;
}
```

### 재귀 함수
```c
#include <stdio.h>

// 팩토리얼
int factorial(int n) {
    if(n <= 1) return 1;
    return n * factorial(n - 1);
}

// 피보나치
int fibonacci(int n) {
    if(n <= 1) return n;
    return fibonacci(n - 1) + fibonacci(n - 2);
}

int main() {
    printf("%d\n", factorial(5));   // 120
    printf("%d\n", fibonacci(7));   // 13

    return 0;
}
```

## 📌 구조체

### 기본 구조체
```c
#include <stdio.h>

struct Student {
    char name[20];
    int age;
    float score;
};

int main() {
    struct Student s1;

    strcpy(s1.name, "홍길동");
    s1.age = 20;
    s1.score = 85.5;

    printf("이름: %s\n", s1.name);    // 홍길동
    printf("나이: %d\n", s1.age);     // 20
    printf("점수: %.1f\n", s1.score); // 85.5

    return 0;
}
```

### 구조체 배열
```c
#include <stdio.h>

struct Student {
    char name[20];
    int score;
};

int main() {
    struct Student students[3] = {
        {"홍길동", 90},
        {"김철수", 85},
        {"이영희", 95}
    };

    for(int i = 0; i < 3; i++) {
        printf("%s: %d\n", students[i].name, students[i].score);
    }

    return 0;
}
```

## 📌 자주 나오는 알고리즘

### 최대값/최소값
```c
#include <stdio.h>

int main() {
    int arr[5] = {3, 7, 2, 9, 5};
    int max = arr[0];
    int min = arr[0];

    for(int i = 1; i < 5; i++) {
        if(arr[i] > max) max = arr[i];
        if(arr[i] < min) min = arr[i];
    }

    printf("최대값: %d\n", max);  // 9
    printf("최소값: %d\n", min);  // 2

    return 0;
}
```

### 정렬 (버블 정렬)
```c
#include <stdio.h>

int main() {
    int arr[5] = {5, 2, 8, 1, 9};
    int n = 5;

    // 버블 정렬
    for(int i = 0; i < n-1; i++) {
        for(int j = 0; j < n-i-1; j++) {
            if(arr[j] > arr[j+1]) {
                int temp = arr[j];
                arr[j] = arr[j+1];
                arr[j+1] = temp;
            }
        }
    }

    // 출력
    for(int i = 0; i < n; i++) {
        printf("%d ", arr[i]);  // 1 2 5 8 9
    }

    return 0;
}
```

### 검색 (선형 검색)
```c
#include <stdio.h>

int main() {
    int arr[5] = {3, 7, 2, 9, 5};
    int target = 9;
    int found = -1;

    for(int i = 0; i < 5; i++) {
        if(arr[i] == target) {
            found = i;
            break;
        }
    }

    if(found != -1) {
        printf("찾은 위치: %d\n", found);  // 3
    } else {
        printf("없음\n");
    }

    return 0;
}
```

## 📌 자주 틀리는 유형

### 1. 증감 연산자
```c
int a = 5;
printf("%d\n", a++);  // 5 (후위 증가: 출력 후 증가)
printf("%d\n", a);    // 6

int b = 5;
printf("%d\n", ++b);  // 6 (전위 증가: 증가 후 출력)
printf("%d\n", b);    // 6
```

### 2. 포인터와 배열
```c
int arr[3] = {10, 20, 30};
int *p = arr;

printf("%d\n", arr[0]);   // 10
printf("%d\n", *arr);     // 10
printf("%d\n", *p);       // 10
printf("%d\n", *(p+1));   // 20
```

### 3. 논리 연산자
```c
int a = 5, b = 10;
printf("%d\n", a && b);   // 1 (둘 다 참)
printf("%d\n", a || b);   // 1 (하나라도 참)
printf("%d\n", !a);       // 0 (부정)
```

### 4. 비트 연산자
```c
int a = 5;  // 0101
int b = 3;  // 0011

printf("%d\n", a & b);   // 1 (AND: 0001)
printf("%d\n", a | b);   // 7 (OR:  0111)
printf("%d\n", a ^ b);   // 6 (XOR: 0110)
printf("%d\n", ~a);      // -6 (NOT)
printf("%d\n", a << 1);  // 10 (왼쪽 시프트)
printf("%d\n", a >> 1);  // 2 (오른쪽 시프트)
```

## 💡 실전 팁

1. **출력 형식** 정확히
   - %d: 정수
   - %f: 실수
   - %c: 문자
   - %s: 문자열

2. **세미콜론(;)** 빠뜨리지 않기

3. **중괄호 {}** 짝 맞추기

4. **배열 인덱스** 0부터 시작

5. **포인터 연산** 주의

## ⚠️ 시험에서 자주 나오는 패턴

- 포인터 값 추적
- 배열과 포인터 관계
- 증감 연산자 (++, --)
- 반복문 실행 횟수
- 재귀 함수 결과
- 문자열 처리
