---
description: Maximum Token Approval Requested by Unauthorized Contract (WARN)
---

# TOKEN-001: 선별되지 않은 컨트랙트의 토큰 최대치 승인 요청 시 경고

### Policy Definition (정책 정의)

> **선별되지 않은 컨트랙트**가 ERC-20 승인(Approve)을 요청하는 경우, 사용자가 승인 상대를 확인할 수 있도록 **경고**합니다.

토큰(ERC-20) 사용을 승인하는 것은 Spender(토큰 사용자)에게 허용 금액만큼 내 토큰 사용 권한을 주는 것과 같습니다. 따라서 허가를 받지 않은 컨트랙트나, 광범위하게 쓰이지 않는 컨트랙트가 토큰을 무제한 승인 요청하는 경우 경고를 표시합니다.

#### Scope (적용 범위)

Permit2, Uniswap V2 Router02, Uniswap V3 SwapRouter, Uniwap V3 SwapRouter02, Uniswap Universal Router, 1inch Aggregation Router V5, 1inch Aggregation Router V6, Aave V3 Pool, Cow Protocol GPv2VaultRelayer

#### Audience (대상 사용자)

DEX를 사용하는 모든 사용자

#### Used Data (판정에 사용될 데이터)

ERC-20 Approve일 때, 승인할 토큰의 양(Amount)과 토큰 사용자(Spender)의 주소

#### Policy in Code

{% code title="policy.cedar" %}
```solidity
@id("unlimited-approval-warn")
@severity("warn")
@reason("이 트랜잭션에 서명하면 상대방이 내 토큰을 무제한 사용할 수 있습니다. 신뢰 가능한 상대인지 확인하세요.")
forbid(principal, action == Token::Action::"Erc20Approve", resource)
when {
  context.amount == "0xffffffffffffffffffffffffffffffffffffffffffffffffffffffffffffffff"
  && !([
    "0x000000000022d473030f116ddee9f6b43ac78ba3", // Permit2
    "0x7a250d5630b4cf539739df2c5dacb4c659f2488d", // Uniswap V2 Router02
    "0xe592427a0aece92de3edee1f18e0157c05861564", // Uniswap V3 SwapRouter
    "0x68b3465833fb72a70ecdf485e0e4c7bd8665fc45", // Uniswap V3 SwapRouter02
    "0x66a9893cc07d91d95644aedd05d03f95e1dba8af", // Uniswap Universal Router
    "0x1111111254eeb25477b68fb85ed929f73a960582", // 1inch Aggregation Router V5
    "0x111111125421ca6dc452d289314280a0f8842a65", // 1inch Aggregation Router V6
    "0x87870bca3f3fd6335c3f4ce8392d69350b4fa4e2", // Aave V3 Pool
    "0xc92e8bdf79f0507f65a392b0ab4667716bfe0110"  // CoW Protocol GPv2VaultRelayer
  ].contains(context.spender))
};
```
{% endcode %}

{% code title="manifest.json" %}
```json
{
  "id": "unlimited-approval-warn",
  "schema_version": 2,
  "trigger": {
    "where": {
      "action.tag": {
        "eq": "erc20_approve"
      }
    }
  }
}
```
{% endcode %}

***

**BASIC-001: 선별되지 않은 컨트랙트의 토큰 최대치 승인 요청 시 경고**\
Wallet Guardians | v.1.0.0 | 26/06/09\
\
&#xNAN;_&#x53;upported Chain: Ethereum_

