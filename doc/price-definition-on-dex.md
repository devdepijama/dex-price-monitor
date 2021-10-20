# Price definition of a DEX
A liquidity pool is a smart contract that holds funds for two different tokens. Let's pick PACOCA and BNB as an example.
There's a PACOCA-BNB contract that holds both funds.

The current price for a liquidity pool holding  an asset is defined by the product expression:

AmountOf(PACOCA).AmountOf(BNB) = k

When the pool is created, the constant k is defined depending on the initial offer of both tokens.
Let's say that when PACOCA-BNB liquidity pool was created values were set like:

- AmountOf(PACOCA) = 100
- AmountOf(BNB) = 100

Therefore, k = 100.100 = 10000.
This k value should hold forever.

A liquidity pool provides the following operations:

- A) Exchange (swap) token A for token B and vice-versa. (PACOCA -> BNB and BNB -> PACOCA, for example)
- B) Provide liquidity to the pool.

When someone swaps BNB for PACOCA, BNB tokens are added to the pool and PACOCA tokens are removed.
Since the k value should hold, we have the following:

(TokensOnPool(BNB) + AmountOf(BNB)) * (TokensOnPool(PACOCA) - AmountOf(PACOCA)) = 10000
(100 + AmountOf(BNB)) * (100 - AmountOf(PACOCA)) = 10000

Let's say we want to swap 10 BNBs, therefore:
110*(100 - AmountOf(PACOCA)) = 10000
AmountOf(PACOCA) = 100 - (10000/110) => 9,09

That means that if someone inserts 10BNB into the pool to maintain the k value, the total amount of PACOCA should be 9,09.
Since there's 10 initially, it means that inserting 10 BNBs will translate into removing 0.91 PACOCA to "compensate" the k factor equation.
