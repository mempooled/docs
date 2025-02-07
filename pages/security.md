import Bleed from 'nextra-theme-docs/bleed';


<Bleed>
<div align="center">
  ![Velocimeter Launch](/dome2.jpg)
  </div>
</Bleed>

&nbsp;

## V2 Contract Addresses

| Contract Name | Contract Address | Network |
| --- | --- | --- |
| FLOW               | [0xB5b060055F0d1eF5174329913ef861bC3aDdF029](https://tuber.build/token/0xB5b060055F0d1eF5174329913ef861bC3aDdF029)   | Canto |
| GaugeFactory       | [0xA7c622Fb04208611b3F7d527249ba9FAa3fDd2a5](https://tuber.build/address/0xA7c622Fb04208611b3F7d527249ba9FAa3fDd2a5) | Canto |
| BribeFactory       | [0x673b71d631DD5d91c4f7a5cA31772a516CFb8Be2](https://tuber.build/address/0x673b71d631DD5d91c4f7a5cA31772a516CFb8Be2) | Canto |
| WrappedBribeFactory| [0xEA9E24a2979D4ACbdB4CCE6608F6C45F9c4421d7](https://tuber.build/address/0xEA9E24a2979D4ACbdB4CCE6608F6C45F9c4421d7) | Canto |
| PairFactory        | [0xF80909DF0A01ff18e4D37BF682E40519B21Def46](https://tuber.build/address/0xF80909DF0A01ff18e4D37BF682E40519B21Def46) | Canto |
| Router             | [0x8e2e2f70B4bD86F82539187A634FB832398cc771](https://tuber.build/address/0x8e2e2f70B4bD86F82539187A634FB832398cc771) | Canto |
| VelocimeterLibrary | [0x7Bb1526A868E2E34DbBc0803Dfff12D9542900E0](https://tuber.build/address/0x7Bb1526A868E2E34DbBc0803Dfff12D9542900E0) | Canto |
| VeArtProxy         | [0xBfd6332aE9c8eD8597E7C29984AAF843ce80b797](https://tuber.build/address/0xBfd6332aE9c8eD8597E7C29984AAF843ce80b797) | Canto |
| VotingEscrow       | [0x8E003242406FBa53619769F31606ef2Ed8A65C00](https://tuber.build/address/0x8E003242406FBa53619769F31606ef2Ed8A65C00) | Canto |
| RewardsDistributor | [0x73278a66b75aC0714c4B049dFF26e5CddF365c85](https://tuber.build/address/0x73278a66b75aC0714c4B049dFF26e5CddF365c85) | Canto |
| Voter              | [0x8e3525Dbc8356c08d2d55F3ACb6416b5979D3389](https://tuber.build/address/0x8e3525Dbc8356c08d2d55F3ACb6416b5979D3389) | Canto |
| Minter             | [0x41dc163DA8E280743585fde657cFC8937b0c7F9B](https://tuber.build/address/0x41dc163DA8E280743585fde657cFC8937b0c7F9B) | Canto |
| Flow Convertor     | [0x63dF314EA0912412ff1cDC5A43585477d08CE5e9](https://tuber.build/address/0x63dF314EA0912412ff1cDC5A43585477d08CE5e9) | Canto |
| Flow Vester        | [0x334ee44fB4d7dC560c51969fE5B9cb5AEfA24519](https://tuber.build/address/0x334ee44fB4d7dC560c51969fE5B9cb5AEfA24519) | Canto |

## Difference from Velocimeter and Velodrome
  - ***Use trading fees as external bribes.***
    In contrast to Velodrome, Velocimeter takes the trading fees of liquidity pools with gauges and sends them
    as external bribes for that respective pool. `USDC` and `FLOW` trading fees directly bribe upcoming
    voters to direct their votes to the `USDC:FLOW` pool. Velocimeter believes this creates a much better
    voting experience as voters clearly can see what they will get, rather than wait to see what trading fees
    they happen to accumulate in the week following their vote.
  - ***Trading fees without gauges.***
    With pairs that don't have a gauge, or have a gauge what was "killed", the trading fees are sent to the [tank](https://tuber.build/address/0x0A868fd1523a1ef58Db1F2D135219F0e30CBf7FB/tokens#address-tabs).

## Differences from Solidly and Velodrome (inherited by Velocimeter)

### Major changes
   
  - ***One vote per epoch.*** In Velocimeter, voters are only allowed to make "active"
    voting decisions (i.e. vote and reset) once per epoch. Voters must wait
    until the next epoch to change their votes. Voters can, however, _cast_
    their votes throughout the epoch.
  - ***Killable gauges.*** To dissuade emissions exploitation via dummy gauges, we're
    allowing the _Velocimeter Council of Velocimetry_ (akin to Curve's Emergency DAO) to kill
    any "bad" gauges. The Council is composed of individuals from varying
    parties meant to serve as a credibly neutral decision-maker for the broader
    ecosystem.

### Minor changes

  - ***Removed the LP boost for voters.*** The boost was removed that voters receive
    when staking their LPs with gauges they voted for. This removes the need
    for a veNFT aggregator (more on this later...).
  - ***Removed negative voting.*** Negative voting was considered zero-sum for
    Solidly, so it was removed.
  - ***Team emissions.*** 3% of new emissions will be sent to a team address, meant
    to cover on-going expenses and future development.

### Small changes

  - ***Modifiable fees.*** Fees on Velocimeter are 0.03% for stable pools and 0.25% for volatile pools.
  - ***Upgradeable veNFT art.*** Self-explanatory

# Security

Velocimeter is a fork of [Velodrome Finance](https://github.com/velodrome-finance) which was adapted from Solidly, which [codebase was open
sourced in full](https://github.com/solidlyexchange/) by Andre Cronje and his team in
March 2022. Since its release in February on Fantom network, no security
incidents related to Solidly smart contracts were reported.

  Before moving forward, we'd like to remind to our users that
  security audits do not eliminate risks completely and that
  every user should read and agree to our
  [legal disclaimer](/legal) before using Velocimeter!
  For security reports, please reach out to us on
  [Discord](https://discord.gg/qpue2s6VfJ), or to the contacts provided on our Github page.


## Audits

Solidly went through a partial (only the AMM part was sent for audit) security
audit in January 30, 2022. The audit was done by PeckShield and did reveal 5
low-severity and 1 informal findings.

The full audit is available for [download from Solidly git
repository](https://github.com/solidlyexchange/solidly/blob/master/audits/e456a816-3802-4384-894c-825a4177245a.pdf).

Velodrome went through a security audit and a peer review as part of the Code4rena bug bouncy contest.
Finally, a full MythX deep scan on Velodrome contracts found just a
handful of false-positive, low-severity issues reported.!


🚨 Velocimeter has NOT gone through any form of audit but rather adopts some from the Velodrome security procedures. The following point of code was changed. 
 - **Removal of Internal Fees** The fees are now directed as external bribes so the need for many contracts became redundant, ie pairFees.sol, internalBribe.sol


### VELODROME Security Procedures

The Code4rena contest results were released on August 8, 2022 and are available [here](https://code4rena.com/reports/2022-05-Velocimeter/). All high- or medium-risk issues were either resolved pre-deploy, except for one known issue (users can claim eligible rewards from ExternalBribe contracts more than once) that's currently being addressed (via a wrapped contract solution). No user funds are at risk from this vulnerability, and protocols who wish to deposit external bribes should get in contact with the core team to discuss alternative solutions. More information about our C4 contest can be found [here](/c4report).

Lastly, we also engaged with Coelacanth ([@ImpossibleNFT](https://twitter.com/impossiblenft)) for an informal full audit. Reports from that audit are available [here](https://github.com/Velocimeter-finance/contracts/tree/master/audits/velo).

## Bug Bounty Programs

Velodrome ran a [bug bounty contest on 23rd to 30th of May 2022 with
awards up to $75,000 on Code4rena](https://code4rena.com/contests/2022-05-Velocimeter-finance-contest).
The main scope of the contest was to cover all the new changes to the new and
the original contracts.

Solidly's bug bounty program was launched in February 2022 on Immunefi.com.
There were no claims for any of the $200,000 rewards ([on their Github](https://github.com/solidlyexchange/solidly/blob/master/SECURITY.md)).


## V1 Contract Addresses (Not Valid Anymore)!

| Contract Name | Contract Address | Network |
| --- | --- | --- |
| FLOW               | [0x2Baec546a92cA3469f71b7A091f7dF61e5569889](https://tuber.build/token/0x2Baec546a92cA3469f71b7A091f7dF61e5569889)   | Canto |
| GaugeFactory       | [0xA472b00DdCf03f099dB954c70133dD6F0c5Fcc26](https://tuber.build/address/0xa472b00ddcf03f099db954c70133dd6f0c5fcc26) | Canto |
| BribeFactory       | [0xa9fa811Cc3BDdF9ba8dAC435f26B77525Eb3B546](https://tuber.build/address/0xa9fa811Cc3BDdF9ba8dAC435f26B77525Eb3B546) | Canto |
| WrappedBribeFactory| [0x3a9238141a4655d0dC907e18BBf9c21b843F09c7](https://tuber.build/address/0x3a9238141a4655d0dC907e18BBf9c21b843F09c7) | Canto |
| PairFactory        | [0xb12aF64E128A1D4489D13314eB4Df81cBCE126aC](https://tuber.build/address/0xb12aF64E128A1D4489D13314eB4Df81cBCE126aC) | Canto |
| Router             | [0x9B2920e72dF6E1A7053bEa7235c65079F5104398](https://tuber.build/address/0x9B2920e72dF6E1A7053bEa7235c65079F5104398) | Canto |
| VelocimeterLibrary | [0x7517df74F63a440D5Fc7c6Ec8BC40560F32079a8](https://tuber.build/address/0x7517df74F63a440D5Fc7c6Ec8BC40560F32079a8) | Canto |
| VeArtProxy         | [0x0B8a83247aa14d4f94f4025db839D87A91817eE9](https://tuber.build/address/0x0B8a83247aa14d4f94f4025db839D87A91817eE9) | Canto |
| VotingEscrow       | [0x990efF367C6c4aece43c1E98099061c897730F27](https://tuber.build/address/0x990efF367C6c4aece43c1E98099061c897730F27) | Canto |
| RewardsDistributor | [0x19E1eef506eE61A58d1AAa11635361bBaE5D0676](https://tuber.build/address/0x19E1eef506eE61A58d1AAa11635361bBaE5D0676) | Canto |
| Voter              | [0xC5B58aE761a77fF16d548dE9b42933c8FBfe4c33](https://tuber.build/address/0xC5B58aE761a77fF16d548dE9b42933c8FBfe4c33) | Canto |
| Minter             | [0x0cEd59FF9BDe47b2F5F0EDD2FdFfA6a0116d91Cd](https://tuber.build/address/0x0cEd59FF9BDe47b2F5F0EDD2FdFfA6a0116d91Cd) | Canto |