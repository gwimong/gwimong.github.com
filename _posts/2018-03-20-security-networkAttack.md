---
layout: post
title:  "First post"
date:   2018-03-26 11:40:18 +0800
categories: test
tags: test HTML CSS
author: Park GwiMong
mathjax: true
---

### 네트워크 기반 공격


## 서비스 거부(Dos) 공격
시스템을 악의적으로 공격해 해당 시스템의 자원을 부족하게 하여 원래 의도됙 용도로 사용하지 못하게 하는 공격.
특정 서버에 수많은 접속 시도를 하도록 만들어 다른 이용자가 정상적인 서비스를 이용 할 수 없도록 만든다.

* DDos 
	+ 다수의 분산된 시스템을 이용하여 Dos 공격하는 기술
	+ 대부분의 Dos 공격은 DDos 형태인 경우가 많다.

* [ICMP](https://ko.wikipedia.org/wiki/ICMP) Flooding
	+ Ping Flooding : <br>
		공격 대상에 압도적인 수의 Ping 패킷을 보내면 공격 대상이 된 Host는 Ping 패킷을 처리하느라 다른 패킷들을 처리 할 수 없게 된다.
	+ SYN Flooding : <br>
		TCP/SYN 패킷의 Flood를 보내면서 대개 송신자의 주소를 위조한다.<br>
		공격 대상이 된 Host는 TCP/SYN 패킷을 수신하면, 해당 패킷의 송신자 주소로부터 응답을 기다리게 된다. <br>
		하지만 해당 TCP/SYN의 송신자 주소는 위조된 주소이므로 응답 패킷을 보내주지 않는다.<br>
		이러한 변조된 TCP/SYN 패킷으로 인해 공격 대상 Host의 접속 수용 범위를 벗어나게 되면 공격이 지속되는 동안 정당한 요청에 응답할 수 없게 된다.
	+ Smurfing : <br>
		Broadcast 주소로 ICMP_REQUEST 패킷을 보내면 같은 네트워크에 있는 시스템들은 ICMP_REQUEST 패킷에 대한 응답(ICMP_ECHO_REPLY)을 공격 대상 Host에게 보낸다. <br>
* [UDP](https://ko.wikipedia.org/wiki/UDP) Flooding
	+ 공격 대상 Host에 가상의 UDP 패킷을 연속적으로 보내서, 서버의 부하 및 네트워크 오버로드를 발생시크는 공격.
	+ 조치방법 : 불필요한 UDP 서비스 차단.
* Teardrop Attack
	+ 데이터의 송수신과정에서 데이터의 송신한계를 넘으면 분할하여 fragment number를 붙여 송신하고, 수신측에서는 fragment number로 재좁하여 데이터를 수신한다.
	+ 이 때 fragment number를 변조하여 공격 대상 Host가 해당 IP 패킷을 재조합하지 못하고, 이로 인한 시스템의 장애가 발생하도록 유도함.
* Ping of Death
	+ 규격 크기 이상의 ICMP Request를 보내는 공격
	+ IP 패킷을 재조합할 때 Buffer Overflow 및 시스템 충돌이 발생.
* Land Attack
	+ 목적지와 출발지가 모두 공격 대상 Host의 주소인 IP 패킷을 공격 대상 Host에 보내는 공격
	+ 공격 대상 Host는 해당 패킷에 대한 reply 패킷을 자신에게 보내고, 그 패킷에 대한 응답을 또 다시 자신에게 보내면서 무한 루프에 빠지게 된다.

##

