# \[Liquid Staking] Stake & Wrap Amount Guard

### 이 패키지로 막을 수 있는 것

ETH를 스테이킹하고 stETH를 wstETH로 감싸거나 푸는 사용자가, 한 번에 큰 금액을 잘못 다루지 않도록 미리 이상 징후를 파악해 경고합니다.

* 한 번에 큰 금액을 스테이킹하지 않도록 차단합니다.
* 한 번에 큰 금액을 wstETH로 wrap하지 않도록 차단합니다.
* 한 번에 큰 금액을 unwrap하지 않도록 차단합니다.
* stETH가 ETH 대비 할인 중일 때 직접 스테이킹하지 않도록 경고합니다.

### 상세 설명

유동성 스테이킹(Liquid Staking)에서는 큰 금액을 예치하고 랩핑하는 과정이 한 번의 서명으로 이루어져 있어, 한 번의 실수가 곧 큰 손실을 일으킬 수 있습니다. 스테이킹, wrap, unwrap의 금액과 stETH 할인 시점을 검사하는 패키지입니다.

### 정책 목록

* 한 번에 큰 금액(기본 100 ETH 이상)을 스테이킹할 시 차단
* 한 번에 큰 금액(100 stETH 이상)을 wstETH로 wrap할 시 차단
* 한 번에 큰 금액(100 wstETH 이상)을 unwrap할 시 차단
* stETH가 ETH 대비 할인 중일 때 직접 스테이킹할 시 경고

***

**\[Liquid Staking] Stake & Wrap Amount Guard**\
Wallet Guardians | v.1.0.0 | 26/06/11\
\
&#xNAN;_&#x53;upported Chain: Ethereum_
