# caip [![npm version](https://badge.fury.io/js/caip.svg)](https://badge.fury.io/js/caip)

CAIP standard utils

## ChainID (CAIP-2)

### Using Classes

```typescript
import { ChainID } from "caip";

const chainId = new ChainID("eip155:1");

// OR

const chainId = new ChainID({ namespace: "eip155", reference: "1" });

// THEN

chainId.toString();
// "eip155:1"

chainId.toJson();
// { namespace: "eip155", reference: "1" }
```

### Using Functions

```typescript
import { ChainID } from "caip";

ChainID.parse("eip155:1");
// { namespace: "eip155", reference: "1" }

// AND

ChainID.format({ namespace: "eip155", reference: "1" });
// "eip155:1"
```

## AccountID (CAIP-10)

### Using Classes

```typescript
import { AccountID } from "caip";

const accountId = new AccountID(
  "0xab16a96d359ec26a11e2c2b3d8f8b8942d5bfcdb@eip155:1"
);

// OR

const accountId = new AccountID({
  address: "0xab16a96d359ec26a11e2c2b3d8f8b8942d5bfcdb",
  chainId: { namespace: "eip155", reference: "1" },
});

// THEN

accountId.toString();
// "0xab16a96d359ec26a11e2c2b3d8f8b8942d5bfcdb@eip155:1"

accountId.toJson();
// { address: "0xab16a96d359ec26a11e2c2b3d8f8b8942d5bfcdb", chainId: { namespace: "eip155", reference: "1" } }
```

### Using Functions

```typescript
import { ChainID } from "caip";

ChainID.parse("0xab16a96d359ec26a11e2c2b3d8f8b8942d5bfcdb@eip155:1");
// { address: "0xab16a96d359ec26a11e2c2b3d8f8b8942d5bfcdb", chainId: { namespace: "eip155", reference: "1" } }

// AND

ChainID.format({
  address: "0xab16a96d359ec26a11e2c2b3d8f8b8942d5bfcdb",
  chainId: { namespace: "eip155", reference: "1" },
});
//"0xab16a96d359ec26a11e2c2b3d8f8b8942d5bfcdb@eip155:1"
```
