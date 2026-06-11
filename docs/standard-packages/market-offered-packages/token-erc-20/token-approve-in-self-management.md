---
description: 여러 dApp을 사용하는 분들을 위한 토큰 보호 패키지
---

# \[Token] Approve in Self Management

### 이 패키지로 막을 수 있는 것

여러 dApp을 사용하면서 승인(approve)을 할 때, 필요한 만큼만, 적당한 기한을 정해서, 한도 내에서만 승인하도록 정책적으로 관리할 수 있도록 구성한 패키지입니다.

* 한 번에 지나치게 많은 금액을 approve하는 경우 경고합니다.
* 만료 기한이 1년 이상 남은 Permit2 승인이 발생하는 경우 경고합니다.
* Permit2 서명 시 무제한으로 허용하도록 요구하는 경우 경고합니다.
* 일일 누적 승인 한도를 초과하는 경우 경고합니다.
* 제재 대상 주소로 토큰 사용 권한을 승인할 때 차단합니다.

### 상세 설명

승인을 자주 수행하는 dApp 사용자가 놓치기 쉬운 '허용 금액', '기한', '한도 관리'를 정책적으로 관리할 수 있도록 구성한 패키지입니다.

### 정책 목록

* approve-usd-cap-warn
* permit2-far-expiration-warn
* permit2-sign-unlimited-warn
* daily-cumulative-approval-cap-warn
* approve-spender-reputation-deny

***

**\[Token] Approve in Self Management**\
Wallet Guardians | v.1.0.0 | 26/06/10\
\
&#xNAN;_&#x53;upported Chain: Ethereum_
