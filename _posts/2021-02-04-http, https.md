---
layout: post
title: http 와 https 이해하기
summary: http, https 의 정의와 차이점
featured-img: computer-science
categories: [Security, CS]
---

## HTTP와 HTTPS

```md
HTTP : 인터넷 상에서 클라이언트와 서버가 자원을 주고 받을 때 사용하는 통신 규칙

HTTPS : 인터넷 상에서 정보를 암호화하는 SSL 프로토콜을 사용해 클라이언트와 서버가 자원을 주고 받을 때 사용하는 통신 규칙

=> 텍스트 통신 과정에서 HTTP는 암호화를 하지않고 보내서 보안 문제가 있지만, HTTPS는 공개키 암호화 방식으로 암, 복호화를 진행하기 때문에 이를 해결할 수 있다.
```

---

## HTTPS를 위한 SSL 방식

```md
1. 애플리케이션 서버를 만드는 측은 HTTPS를 사용하기 위해 공개키와 개인키를 만든다.
2. 신뢰할 수 있는 CA기업을 선택하고, 그 기업에게 내 공개키 관리를 부탁하며 계약을 한다.
3. CA 기업은 해당 의뢰자측의 이름, 서버 공개키, 공개키 암호화 방법을 담은 인증서를 만들고, 해당 인증서를 CA기업의 개인키로 암호화해서 서버측에 제공한다.
4. 서버측은 암호화된 인증서를 갖게 되고, 서버는 서버의 공개키로 암호화된 HTTPS 요청이 아닌 요청이 오면, 이 암호화된 인증서를 클라이언트에게 건네준다.
5. 클라이언트가 A서버에 정보를 요청할 때, HTTPS 요청이 아니면 서버가 이 암호화된 인증서를 클라이언트에게 건내준다.
6. 클라이언트는 받은 인증서를 브라우저가 가지고 있는 CA 공개키를 통해 해독한 뒤 서버측의 공개키를 얻는다. 
7. 이를 통해 서로 공개키를 얻었으므로, 이제 HTTPS 통신이 가능해진다.

※ CA(Certificate Authority) : 공개키를 저장해주는 신뢰성이 검증된 민간기업
※ CA 기업의 공개키는 브라우저가 이미 알고있다. (세계적으로 신뢰할 수 있는 기업으로 등록되어 있기 때문에, 브라우저가 인증서를 탐색하여 해독이 가능한 것)
```
