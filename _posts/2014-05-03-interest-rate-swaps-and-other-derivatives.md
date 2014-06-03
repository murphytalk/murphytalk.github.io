---
layout: post
category: finance 
tags: [swap, finance, reading-notes]
---
# A Introduction to Swap
{:toc}

There are two categories of swap:
 
1. Coupon swap or Fixed-floating swap or Plain vanilla swap : one stream is fixed rate and the other one is float rate.
1. Basis swap : two floating rates

The attention will be restricted to swaps denominated in USD.

## Conventions

### Swap

1. `30/360` : also called "bond" because this is how bond traders calculates days ususally.
1. `Act/360` : also called "money"
1. `Offer side spread ` : the lowest spread that a dealer is willing to add to the treasury yield to recieve fixed rate.
1. `Bid side spread` : the highest spread that a dealer is willing to add to the treasury yield to pay fixed rate.

**Effective date** : start of swap

----------

Fixed rate can also be expressed as say `T5+21`,means the yield of 5 year on the run Tresury at the time the swap is executed plus a spread of 21 bps.Thus the swap rate,also called the par swap rate,the fixed rate set in the swap when it is first executed such that the trade has 0 net present value to either side,is equal to `T5+21`.

By default the floating side is 3 month LIBOR paid quartly `Act/360`.

Ideally,dealer pofits from bid/ask spread,if he has 2 trades to perfectly offset one anther.

Swap spreads for swap of each of the TRSY benchmarks (2,3,5,7,10 and 30-year bonds) are quoted as a spread to the respective on-the-run TRSY by its maturity.All other swaps,with the exception of the 12-year swap rate,are computed as follows:

1. Linear interpolation between the two adjacent on-the-run TRSY is used to compute an interpolated mid-market TRSY yield from the maturity.
1. The appropriate swap spread for the given maturity is then added to that interpolated mid-market TRSY yield.

12-year swap spread is quoted as a spread to the yieid of the 10-year TRSY.

----------

#### Day count and payment

A good day for USD swap cannot be holiday either in London or in New York.

If a payment were to fall on a bad day,the actual payment date will depend on the following basis:

1. *preceding* the first preceding good day 
1. *following* the next good day 
1. *modified following* if the next good day happens to fall in the subsequent month then fail over to the preceding good day.

### Tresury and bond market

- On-the-run : the most recently issued
- (Single) old : the one issued before on-the-run
- Double-old : the one issued before old
- Bond market *rallies* : rates go down and prices go up
- Bond market *sells off*: rates go up and prices go down

## Pay Frequency and Day Count

Appoximate the swap rate if its fixed leg does not pay semiannually on a 30/360 basis. It can be approximated by treating the fixed rate and pay frequecy as coupon and pay frequecy of a bond,and the future value of 2 types of rate/frequency should equal to each other otherwise there will be arbitrage.

Covert an annual bond swap rate `r1` to an annual money swap rate \\( r_2=360 \times \frac{r_1}{r_2} \\).

It can be generalized : if \\( s\_{xb} \\) is a swap rate paid `x` times per year on a bond basis, and \\( s\_{yb} \\) is the equivalent rate paid `y` times per year on a bond basis, then

$$ s_{yb} \approx  y \times \left[\left(1+\frac{s_{xb}}{x}\right)^{\frac{x}{y}}-1\right] \tag{1.8}$$

And given \\( s\_{yb} \\),we can approximate \\( s\_{ym} \\),the equivalent swap rate paid `y` times on a money basis as

$$ s_{ym} \approx \frac{360}{365} \times s_{yb} \tag{1.9}$$

## Bid and Offer Swap Rates

The bid side swap rate is defined as the fixed rate at which a swap trader is willing to pay fixed and receive fixed.

As a convention, most composite pages show the bid and offer semi bond swap rate as the bid and offer swap spread over the the mid-market Treasury.

    Bid Side Sawp Rate   = Offer Side Treasury + Bid Side Swap Spread    (1.11)
    Offer Side Swap Rate = Bid Side Treasury + Offer Side Swap Spread    (1.12)

The reason :

If a dealer agrees to pay a fixed rate to a client and recieves a floating rate, in his client's position, looking at the fixed leg isolately, it is very much like the client purchased a bond from the dealer (only there won't be a final face value payment).

If the fixed rate goes down, just as when a bond market rallies, the value of the fixed rate leg goes up, the dealer who is paying the fixed rate, he is like just sold a fixed coupon bond, will be underwater. So when the dealer pays a fixed rate, he maybe want to buy Treasury to hedge the risk : since he is a customer   in the treasury market,he has to buy at the offered price,or buy on the offer side,which becomes part of his cost,so his swap price will be the treasury cost plus the bid side swap rate, that is how we come with formula `(1.12)`. 


