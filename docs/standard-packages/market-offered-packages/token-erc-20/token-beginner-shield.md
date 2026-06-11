---
description: DeFi 거래가 익숙하지 않은 분들을 위한 보호 패키지
---

# \[Token] Beginner Shield

### 이 패키지로 막을 수 있는 것&#x20;

Web3 생태계에 입문한지 얼마 되지 않은 분들을 노리는 비정상적인 트랜잭션 발생 시 경고합니다.

* 소각 주소(`0x00..00`, `0x00..dead`)로 토큰을 보내지 않도록 경고합니다.
* 선별된 것 이외의 컨트랙트에 토큰 권한을 무제한으로 승인하지 않도록 경고합니다.
* 토큰 컨트랙트 주소에 토큰을 보내지 않도록 경고합니다.
* 악성으로 알려진 주소에 토큰 사용 권한을 위임하지 않도록, 비정상적인 상호작용이 발생하면 차단합니다.

### 상세 설명

Web3에 갓 입문한 사용자가 첫 승인, 첫 송금, 첫 서명 시에 겪을 수 있는 사고를 방지할 수 있도록 구성한 패키지입니다.

### 정책 목록

* unlimited-erc20-approve-warn
* transfer-to-burn-address-warn
* transfer-to-token-contract-warn
* permit2-sign-unlimited-warn
* approve-spender-reputation-deny

***

**\[Token] Beginner Shield**\
Wallet Guardians | v.1.0.0 | 26/06/10\
\
&#xNAN;_&#x53;upported Chain: Ethereum_
