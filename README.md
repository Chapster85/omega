Omega Network Core integration/staging repository
=================================================

Omega is a cutting edge cryptocurrency, with many features not available in most other cryptocurrencies.
- Anonymized transactions using coin mixing technology, we call it _Obfuscation_.
- Fast transactions featuring guaranteed zero confirmation transactions, we call it _SwiftTX_.
- Decentralized blockchain voting providing for consensus based advancement of the current Masternode
  technology used to secure the network and provide the above features, each Masternode is secured
  with a collateral of 2500 OMEGA.

### Coin Specs
<table>
<tr><td>Algo</td><td>OmegaHash</td></tr>
<tr><td>Block Time</td><td>60 Seconds</td></tr>
<tr><td>Difficulty Retargeting</td><td>Every blocks</td></tr>
<tr><td>Max Coin Supply (PoW Phase)</td><td>20,000,000 OMEGA</td></tr>
<tr><td>Max Coin Supply (PoS Phase)</td><td>Infinite</td></tr>
<tr><td>Premine</td><td>580,000 OMEGA</td></tr>
</table>

### Reward Distribution

<table>
<th colspan=4>PoW Phase</th>
<tr><th>Block Height</th><th>Reward Amount</th><th>Notes</th><th>Duration (Days)</th></tr>
<tr><td>1</td><td>580,000 OMEGA</td><td>Initial Premine</td><td>0 Days</td></tr>
<tr><td>2-100000</td><td>10 - 195 OMEGA</td><td>Open Mining</td><td>Gradually incrementing to prevent instamining</td></tr>
<tr><td>100001-103500</td><td>195 - 10 OMEGA</td><td>Open Mining</td><td>Gradually decreasing to smooth PoS transition</td></tr>

<tr><th colspan=4>PoS Phase</th></tr>
<tr><th>Block Height</th><th colspan=3>Reward Amount</th></tr>
<tr><td>100001+</td><td colspan=3>Check PoS Rewards Breakdown below.</td></tr>
</table>

### PoW Rewards Breakdown

<table>
<th>Block Height</th><th>Masternodes</th><th>Miner</th><th>Budget</th>
<tr><td>2-33000</td><td>80% (156 OMEGA)</td><td>20% (39 OMEGA)</td><td>N/A</td></tr>
<tr><td>33001-66000</td><td>50% (97.5 OMEGA)</td><td>40% (78 OMEGA)</td><td>10% (19.5 OMEGA)</td></tr>
<tr><td>66001-100000</td><td>30% (58.5 OMEGA)</td><td>60% (117 OMEGA)</td><td>10% (19.5 OMEGA)</td></tr>
</table>

### PoS Rewards Breakdown

<table>
<th>Phase</th><th>Block Height</th><th>Reward</th><th>Masternodes & Stakers</th><th>Budget</th>
<tr><td>Phase 1</td><td>259201-302399</td><td>50 OMEGA</td><td>90% (45 OMEGA)</td><td>10% (5 OMEGA)</td></tr>
<tr><td>Phase 2</td><td>302400-345599</td><td>45 OMEGA</td><td>90% (40.5 OMEGA)</td><td>10% (4.5 OMEGA)</td></tr>
<tr><td>Phase 3</td><td>345600-388799</td><td>40 OMEGA</td><td>90% (36 OMEGA)</td><td>10% (4 OMEGA)</td></tr>
<tr><td>Phase 4</td><td>388800-431999</td><td>35 OMEGA</td><td>90% (31.5 OMEGA)</td><td>10% (3.5 OMEGA)</td></tr>
<tr><td>Phase 5</td><td>432000-475199</td><td>30 OMEGA</td><td>90% (27 OMEGA)</td><td>10% (3 OMEGA)</td></tr>
<tr><td>Phase 6</td><td>475200-518399</td><td>25 OMEGA</td><td>90% (22.5 OMEGA)</td><td>10% (2.5 OMEGA)</td></tr>
<tr><td>Phase 7</td><td>518400-561599</td><td>20 OMEGA</td><td>90% (18 OMEGA)</td><td>10% (2 OMEGA)</td></tr>
<tr><td>Phase 8</td><td>561600-604799</td><td>15 OMEGA</td><td>90% (13.5 OMEGA)</td><td>10% (1.5 OMEGA)</td></tr>
<tr><td>Phase 9</td><td>604800-647999</td><td>10 OMEGA</td><td>90% (9 OMEGA)</td><td>10% (1 OMEGA)</td></tr>
<tr><td>Phase X</td><td>648000-Infinite</td><td>5 OMEGA</td><td>90% (4.5 OMEGA)</td><td>10% (0.5 OMEGA)</td></tr>
</table>
