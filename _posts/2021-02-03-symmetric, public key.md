---
layout: post
title: 대칭키와 공개키 이해하기
summary: 컴퓨터 보안 대칭키와 공개키의 개념
featured-img: computer-science
categories: [Security, CS]
---

## 대칭키

---

```md
대칭키 : 암호화와 복호화에 같은 암호키(대칭키)를 사용하는 알고리즘
장점 : 동일한 키를 주고받기 때문에, 매우 빠름
단점 : 대칭키 전달과정에서 해킹 위험에 노출될 수 있음
```

## 공개키

---

```md
공개키 : 암호화와 복호화에 사용하는 암호키를 분리한 알고리즘. 복호화에 사용하는 키는 자신만 가지는 비밀키이고, 암호화에 사용하는 키는 공개되어 있는 공개키이다
장점 : 대칭키의 전달과정의 해킹 위험을 해결하였다
단점 : 암복호화가 대칭키에 비해 복잡하다
```

## 공개키 암호화 진행 과정

![img](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FbltNyN%2FbtqtUB5xU23%2FdVJ7TutBubRsOLhzQkeu0K%2Fimg.png)

```md
1. Bob 이 Alice에게 메시지를 보낼 때, Alice 의 공개키로 암호화를 진행한다.
2. Alice는 암호문을 받고, 자신만이 가진 비밀키로 복호화를 한다.
3. 반대로 Alice가 Bod에게 메시지를 보낼 때는, Bob 의 공개키로 암호화를 진행한다.
4. Bob 은 자신의 비밀키로 복호화를 진행한다.
```

## 공개키와 대칭키의 혼합 방식

```md
1. Bob 이 Alice의 공개키로 암호화 통신에 사용할 대칭키를 암호화하고 Alice에게 보낸다.
2. Alice는 암호문을 받고 자신의 비밀키로 복호화를 한다. -> 대칭키 획득
3. Alice는 Bob으로부터 받은 대칭키로 A에게 보낼 평문을 암호화하여 Bob에게 보낸다.
4. 이제 Bob과 Alice 는 전달 위험이 없이 대칭키를 소유하고 있다.
```

### 즉, 대칭키의 전달과정이 위험하다는 단점을 공개키 방식으로 보완함으로써 각 키의 장점을 가질 수 있다. 이 방식이 HTTPS에서 쓰이는 SSL 방식의 핵심 원리이다
