---
description: Swap Output Destined for a Third-Party Address (WARN)
---

# AMM-001: Swap으로 받을 자산이 제3자에게 갈 시 경고

### Policy Definition (정책 정의)

> Swap할 때 토큰을 수령할 주소가 **제3자의 것**으로 되어 있는 경우, 사용자가 수령할 주소를 검토할 수 있도록 **경고**합니다.

Swap을 할 때&#x20;

#### Scope (적용 범위)

AMM 기반의 DEX에서 Swap할 때 적용됩니다.

#### Audience (대상 사용자)

#### Used Data (판정에 사용될 데이터)

#### Disclaimer (주의 사항)

라우터를 사용하는 DEX를 사용하는 경우,&#x20;

#### Policy in Code

{% code title="policy.cedar" %}
```solidity
```
{% endcode %}

{% code title="manifest.json" %}
```json
```
{% endcode %}

***

**BASIC-002: Swap으로 받을 자산이 제3자에게 갈 시 경고**\
Wallet Guardians | v.1.0.0 | 26/06/09\
\
&#xNAN;_&#x53;upported Chain: Ethereum_
