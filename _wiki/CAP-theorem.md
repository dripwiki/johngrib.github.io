---
layout  : wiki
title   : CAP 정리
summary : 
date    : 2019-10-27 22:43:59 +0900
updated : 2019-11-01 21:40:37 +0900
tag     : 
toc     : true
public  : true
parent  : proverb
latex   : false
---
* TOC
{:toc}

## 인용: 트랜잭션 처리의 원리

> 분산 시스템에서, 데이터 일관성(data consistency), 시스템 가용성(system availability),
네트워크 분할 허용성(network to partition-tolerance) 간의 고유한 균형이 존재한다.
시스템은 이들 세 특성 가운데 두 가지를 제공할 수 있지만, 세 가지 모두는 제공하지 않는다.
이를 CAP 추측(CAP conjecture)이라고 한다.[^bernstein-define]

## 인용: 데이터 중심 애플리케이션 설계

> CAP는 때때로 **일관성(Consistency), 가용성(Availability), 분단 내성(Partition tolerance)이라는 세 개 중 두 개를 고르라**는 것으로 표현된다.
불행하게도 이런 식으로 생각하면 오해의 소지가 있다.
네트워크 분단은 일종의 결함이므로 선택할 수 있는 뭔가가 아니기 때문이다.
네트워크 분단은 좋든 싫든 발생한다.  
네트워크가 올바르게 동작할 때는 시스템이 일관성(선형성)과 완전한 가용성 모두를 제공할 수 있다.
네트워크 결함이 생기면 선형성과 완전한 가용성 사이에서 선택해야 한다.
따라서 CAP는 **네트워크 분단이 생겼을 때 일관성과 가용성 중 하나를 선택하라**는 의미로 보는 게 좋다.
이런 선택을 자주하지 않으려면 더욱 신뢰성 있는 네트워크가 필요하지만 어떤 시점에서는 선택이 불가피하다.  
CAP에 대한 논의에서 **가용성**이라는 단어의 몇 가지 모순된 정의가 있고, 공식적인 정리는 보통의 의미와 부합하지 않는다. 많은 이른바 "고가용성"(내결함성) 시스템들은 실제로 CAP에서의 가용성에 대한 기이한 정의를 만족시키지 않는다. 대체로 CAP 주위에는 많은 오해와 혼란이 있으며 시스템을 더 잘 이해하는 데 도움을 주지 않으므로 CAP는 피하는 게 최선이다.[^martin-cap]


## 참고문헌

* 트랜잭션 처리의 원리 / 필립 A. 번스타인, 에릭 뉴코머 공저 / 한창래 역 / KICC(한국정보통신) / 1판 1쇄 2011년 12월 19일
* 데이터 중심 애플리케이션 설계 / 마틴 클레프만 저/정재부, 김영준, 이도경 역 / 위키북스 / 초판발행 2018년 04월 12일

## 주석

[^bernstein-define]: 트랜잭션 처리의 원리. 9 복제. 340쪽.
[^martin-cap]: 데이터 중심 애플리케이션 설계. 9 일관성과 합의. 335쪽.
