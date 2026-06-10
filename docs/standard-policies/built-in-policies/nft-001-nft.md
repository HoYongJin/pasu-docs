---
description: Uncurated Marketplace Requesting NFT Collection Delegation (WARN)
---

# NFT-001: 선별되지 않은 마켓플레이스 컨트랙트의 NFT 컬렉션 위임 요청 시 경고

### Policy Definition (정책 정의)

> Swap할 때 토큰을 수령할 주소가 **제3자의 것**으로 되어 있는 경우, 사용자가 수령할 주소를 검토할 수 있도록 **경고**합니다.

Swap을 할 때&#x20;

#### Scope (적용 범위)

AMM 기반의 DEX에서 Swap할 때 적용됩니다.

#### Audience (대상 사용자)

#### Used Data (판정에 사용될 데이터)&#x20;

#### Policy in Code

{% code title="policy.cedar" %}
```solidity
// Day-1 Safety — NFT 컬렉션 전체 승인(setApprovalForAll) 경고 (순수 Cedar).
// 알려진 마켓플레이스 operator(OpenSea/Blur/LooksRare)는 allowlist 제외 — 그 밖 operator에게 grant(true) 할 때만 경고. operator = context.spender. revoke(false)는 통과.
@id("nft-set-approval-for-all-warn")
@severity("warn")
@reason("컬렉션의 NFT 전체 이동 권한을 잘 알려지지 않은 컨트랙트에 넘기는 중 — 신뢰하는 마켓플레이스가 맞는지 확인하세요")
forbid(principal, action == Token::Action::"NftSetApprovalForAll", resource)
when {
  context.approved == true
  && !([
    "0x1e0049783f008a0085193e00003d00cd54003c71", // OpenSea Seaport conduit
    "0x00000000000111abe46ff893f3b2fdf1f759a8a8", // Blur ExecutionDelegate
    "0x000000000060c4ca14cfc4325359062ace33fe3d"  // LooksRare TransferManager
  ].contains(context.spender))
};
```
{% endcode %}

{% code title="manifest.json" %}
```json
{
  "id": "nft-set-approval-for-all-warn",
  "schema_version": 2,
  "trigger": {
    "where": {
      "action.tag": {
        "eq": "nft_set_approval_for_all"
      }
    }
  }
}
```
{% endcode %}

***

**NFT-001: 선별되지 않은 마켓플레이스 컨트랙트의 NFT 컬렉션 위임 요청 시 경고**\
Wallet Guardians | v.1.0.0 | 26/06/09\
\
&#xNAN;_&#x53;upported Chain: Ethereum_
