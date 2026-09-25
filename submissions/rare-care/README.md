# Rare Care

A cozy Tamagotchi / familiar-care game starring your connected Rare Friend inside a deterministic colored shell.

**Builder / contact:** [Jasmin2108](https://github.com/Jasmin2108)  
**Category:** Character Spotlight  
**SDK:** FriendSDK v0.1.2

**What did you build?**  
Rare Care puts your owned Generations NFT in a handheld Tamagotchi in a tiny garden room. You feed, play and rest it with simulated $RAREFRIENDS, and a happy Friend idles better while its wallet jar and preview protocol desk show earnings.

**How does it use Rare Friends?**  
The SDK runtime connects the wallet and verifies a hardwired Generations NFT (generation ≥ 1). The official on-chain 16×16 sprite is the character. Shell color comes from family (or token id). Care spends the SDK Care Snack consumable. A protocol desk reads on-chain generation and uses official hardwire / promote / upgrade tables for a labeled preview of bag, claimable RF + WETH, and token buys.

**Source code**  
https://github.com/Jasmin2108/rare-care

**Playable demo / how to run**  
https://Jasmin2108.github.io/rare-care-preview/

Players still need a hardwired Generations NFT on Robinhood mainnet (4663). Economy stays simulated.

Local run with Node.js 22+:

git clone https://github.com/spokesz/friendsdk.git
cd friendsdk
npm ci
# copy Rare Care sources into games/rare-care
npm run build
npm run dev:game -- games/rare-care --host 0.0.0.0 --port 4173

Open http://localhost:4173 (not http://0.0.0.0:4173). Connect wallet, switch to Robinhood if asked, select your Friend. Preview play needs no RF funding and no signature.

## How do you play?

- Tap the bowl / toy / bed, the A B C buttons, or keys 1/F, 2/P, 3/R.
- Hunger, Mood and Energy decay while idle. All three ≥ 70% starts Collecting. Any need below 20% makes the Friend sad, dims the screen and pauses collecting.
- H Matt's Hats (2 RF, local cosmetic). C Shell Paint (3 RF, session lock). G or Earn opens the protocol desk.
- Settings: mute and reduced motion.

## Costs and rewards

All preview balances, snacks, cosmetics, bag swaps and claims are simulated.

Feed / Play / Rest: 1 Care Snack. Live mapping is 1 RF from the Friend wallet.
Matt's Hats: 2 RF local cosmetic.
Shell Paint: 3 RF session lock.
Care jar drip: local RF while needs are at least 70%.
Hardwire: reads on-chain generation. Playable Friends are already permanent.
Promote: preview generation step with official price, tier reset.
Upgrade: preview tiers 0 to 4 with official prices and weights.
Buy tokens: preview bag at 1 WETH = 1000 RF.
Claim RF / WETH: preview claimable goes into the Friend bag.

Care Snack outcomes (flavor only):
Warm crumb 45% 0.20 RF
Play spark 35% 0.35 RF
Dream mote 15% 0.60 RF
Lucky marble 5% 1.20 RF

Expected snack prize: 0.3625 RF. Maximum prize reserved per snack: 1.2 RF. Care is a net sink.

Live protocol writes cannot be signed from the sandboxed game frame. Use https://rarefriends.com/portfolio for real transactions.

## Checks and known issues

friendsdk check games/rare-care passed when the game was built (expected reward 0.3625 RF, max 1.2 RF).
Automated Playwright / real-wallet browser suite was not run in this checkout.
SDK iframe has no localStorage; needs, hat, paint, bag and claimable persist in memory for the session and decay by elapsed time.
Token Activity is not claimed. No live RF is spent or burned by the preview.
Artwork: official Friend sprites via FriendSDK. Room and shell are original CSS/canvas. Sounds: FriendSDK sound kit.
Official Rare Friends production publication needs a separate review.
