# The Slow Money Game

Design notes for a boxed, physical edition of Slow Money: a family game about money for every generation, and an expansion that turns the Self-Mint workshop into a game played at the kitchen table.

This document gathers everything decided so far. For the wider project plan, see the [Roadmap](ROADMAP.md).

## Part 1: The family game

A boxed physical edition of Slow Money that looks and feels like a family board game.

### Why a game

Money is the subject families most often avoid. A game setting lowers the stakes: the question comes from a card, not from a parent, so nobody feels interrogated. Turn-taking rules (the oldest speaks first about the past, the youngest first about hopes) are about fairness rather than authority. Children join in naturally, and older relatives who would never attend a financial literacy session will happily play a round. The game takes a contentious subject and places it in a setting families already know and trust: cards after Sunday lunch, the tombola at Christmas, the photo album.

### Principles

- **Camouflage the form, not the purpose.** The box says plainly what it is: a game about money for every generation. People come for the game and stay for the conversation. Nothing is taught by stealth.
- **Play, but never score each other.** There are no winners, points or rankings between family members. Competition around family money is exactly what the game is meant to avoid. Scores from The Test stay private.
- **Borrow familiar conventions.** Card suits, tokens, a rulebook and "players and ages" on the side of the box, so nobody needs the idea explained.
- **Things that outlast the box.** The chronicle and the Heirloom Letters are meant to stay with the family for decades.
- **Designed from the pilot.** Contents, card wording and session length are decided by what pilot families actually used, skipped and asked for.

### Contents (draft)

- **Card deck** in suits: Memories, Habits, Hopes, a children's suit and a closing card, with possible further suits for Money Memories questions and Heirloom prompts
- **Ten tokens:** wooden discs marked with the tree-ring coin, and a small mat for the Combined Wage game
- **A slate:** a small chalkboard for the Family Ledger's temporary obligations, wiped clean when settled
- **The chronicle:** a bound notebook with a printed title page, to stay with the family after the box
- **Heirloom Letter envelopes,** possibly with a seal
- **Rulebook:** the ground rules and host sheet, with the ground rules repeated inside the lid
- **QR card** linking to The Test

### On the box

The Slow Money sign on the lid. On the side: a line saying what the game is, players (about 2 to 8), ages (6 and up) and time (about an hour).

## Part 2: The Self-Mint expansion

A future expansion that leads the game from the family strand of Slow Money (where money is learned) into the Coin-tainer strand (what money is). It packages the Self-Mint workshop, not the live ceremony: a full practice run on the real equipment, witnessed by the family, with pen, paper and envelopes in place of steel and wood, and everything destroyed at the end.

### Why it works

The Coin-tainer repo's `type-s-workshop.md` already sets the rules this game follows: practice runs use the real equipment; witnessed entropy is identical in quality to a live mint's; what makes it unusable is only that it was witnessed; no phrase from a collective session is ever funded; and practice materials must be clearly distinct from a real casing. A family game meets every one of these. It is the workshop, packed in a box.

### Equipment and materials

- **Lent by a Self-Mint workshop:** a SeedSigner with firmware already verified (Phase 0 happens in the lending arrangement, never at the kitchen table). This is the only hardware the game needs.
- **Supplied in the box:** eleven custom numbered dice (see the dice specification below), a paper dice strip, four BIP39 word sheets, envelopes with an empty QR grid printed on the outside, word slips, event cards, the rulebook, and a link to the transcription app. This inverts the workshop rule: the workshop lends tools, the box supplies materials.
- **The entropy pills** stay in the real workshop. The game points to them as the next step.

### Basic box contents

- **Four BIP39 word sheets**
- **One dice strip:** a word strip (dice 1–11) and a final strip (dice 1–7)
- **Eleven numbered dice**
- **Rulebook,** including the throwing rules, the phone ritual and the ordinary-dice fallback
- **Envelopes:** each printed on the outside with the 41 × 41 QR grid (fixed parts preprinted) and a box for the 8-character fingerprint. The 12-word slip goes inside, and the flap is signed across when sealed.
- **Word slips:** for writing each word as it is found, then the full phrase
- **Cards:** event cards drawn from the risk register (for example "someone walks into the room", "a word doesn't match at the second check", "the seal is torn"), each giving the right response; a phone ritual card listing its steps in order; and the closing card: *everything minted here was witnessed, and that is why none of it could ever be real.*
- **A card linking to the transcription app**

Not in the box: the SeedSigner, lent by a Self-Mint workshop with verified firmware.

### Choosing words with dice

Each die is a fair coin. Read the top face only: **number = ● = 1, blank = ○ = 0**. Every throw is exactly 50/50, so every word is exactly equally likely.

**Dice specification.** Eleven identical black six-sided dice, numbered 1 to 11. Each die carries its own number on three faces; the other three faces are blank, and every numbered face is opposite a blank face. Whichever face lands on top, the die's number is always visible on two of its side faces, so each die can be identified and placed without touching it. Numbers are printed (pad printing, UV printing or hot stamping), not drilled, so the faces stay balanced; if engraved, they are filled flush with paint. 6 and 9 are underlined so they cannot be misread from the side. Numbers were chosen over eleven colours because colours invite argument (pink or light red?) and exclude colour-blind players.

**Fallback with ordinary dice.** Anyone who loses a die, or wants to play with ordinary dice, can use the parity rule instead: **even = ● = 1, odd = ○ = 0**. An ordinary die has three even and three odd faces, so it is also exactly 50/50. The rulebook, word sheets and dice strip all state both rules. The 2,048 BIP39 words are printed in official order on four A4 sheets (`printables/game/slow-money-game-bip39-word-sheets.pdf`), 512 words each, in 32 rows of 16 columns:

- **Sheet:** 2 dice, read left to right (○○ = A, ○● = B, ●○ = C, ●● = D).
- **Row:** 5 dice, matched against the dot pattern printed beside each row.
- **Column:** 4 dice, matched against the dot pattern printed above each column.

That is 11 fair coins per word, which is exactly one BIP39 word.

**Twelve throws, not 128 rolls.** Each word is one throw of all eleven dice, placed by number into the slots of the paper dice strip (`printables/game/slow-money-game-dice-strips.pdf`) and read in number order: dice 1–2 for the sheet, 3–7 for the row, 8–11 for the column. Because each die's position is decided by its number, nobody chooses which die goes where, so the result cannot be steered. The whole seed takes 12 throws: 11 for the words, then one throw of dice 1 to 7 for the final 7 bits of the 12th word, entered on the SeedSigner as coin flips (number = heads, blank = tails). Every bit of randomness comes from the dice; the device only calculates the checksum.

**Throwing rules (for the rulebook).** Anyone can throw any number of dice, in any combination, as long as the strip is completed. Each die is an independent coin, so who throws it, and how many are thrown together, makes no difference. Three rules keep it fair:

1. **Each die fills only its own numbered slot.** Die 7 always goes in slot 7, so nobody ever chooses where a result goes.
2. **Each die is thrown once per word.** Once a slot is filled it stays filled until the word is written down. No second tries.
3. **Only invalid throws are thrown again.** A die that leaves the table or lands leaning has no result and is thrown again. This is decided by where it landed, not by what it showed.

A word is ready when all eleven slots are filled, however the family got there.

**Shared rolling.** Family members take turns, one word each, so everyone contributes to the family's (practice) seed. The youngest throws the final seven dice.

**BINARY.** The wooden BINARY object from the Anonymous Art repo, 11 sliders with no power or electronics, can stand in for the paper strip: set one slider per die, in number order, and read the pattern. Its digital dashboard is for learning before the game (exploring words and their binary), never for entering dice results during it, since that would bring the phone out of its box. The dot patterns are the word's actual 11-bit index in binary, so nobody needs to do arithmetic, and teenagers can discover the binary for themselves. Each word's first four letters are printed bold, since BIP39 words are uniquely identified by them. For the 12th word, 7 more rolls supply the remaining 7 bits and the SeedSigner computes the checksum part.

Four sheets were chosen over two for legibility at every age (two sheets would need tiny print), and over five because the number of sheets must be a power of two for the dice to stay fair.

### A round of play

1. **Roll.** Eleven throws of the eleven numbered dice, one word per throw, taken in turns round the table. Each word is found on the sheets and written on a slip, face down. A twelfth throw of seven dice gives the final bits.
2. **Transcribe and checksum.** Each word is read aloud and entered into the SeedSigner, followed by the seven final bits as coin flips, and the SeedSigner calculates the real 12th word.
3. **Write.** The 12 words are copied onto a paper slip.
4. **Verify twice.** The phrase is checked against the rolled slips, then against the device.
5. **Seal.** The slip goes into the envelope; the minter signs across the flap.
6. **The phone ritual.** Open the box, take out the phone, open the app, scan the xpub QR from the SeedSigner, transcribe it by hand onto the envelope's grid, rescan the drawn grid and confirm the match, close the browser, switch off the phone, and return it to the box. The phone stays in the box at every other moment.
7. **Reset.** Dice back in the box, slips collected for destruction.
8. **Record.** One line in the family chronicle: the date, who practised and who minted. Never the words, never the envelope.
9. **Reset and destroy.** In the deluxe edition, every switch on the switch-row kit is first returned to 0 (see the reset ritual). Then the envelope is torn and burned, or shredded and soaked. Everyone watches. The last card reads: *everything minted here was witnessed, and that is why none of it could ever be real.*

Nothing from the game is kept. A surviving envelope, even one showing only the public QR, is the kind of object someone might one day fund by mistake.

### Deluxe edition

The expansion's basic box uses the paper dice strip. A deluxe edition adds objects meant to stay in the house after the game: the switch-row kit (below), the bound chronicle, and possibly a wooden dice tray.

**The switch-row kit: a mini BINARY.** A low-cost kit the family assembles together, a desk-sized cousin of the BINARY object in the Anonymous Art repo.

- **Parts:** a pre-drilled metal panel strip and eleven single-pole panel-mount toggle switches. No battery, no LEDs, no wires, no electronics of any kind.
- **Faceplate:** each switch numbered 1 to 11 to match its die, with the three groups marked: sheet (1–2), row (3–7), column (8–11). 6 and 9 are underlined.
- **Open underneath:** the panel stands raised so its underside can be seen, showing that there is nothing inside. Like CHECKSUM, it has no hidden circuit, and anyone can confirm it by looking.
- **How it is used:** after each throw, the player sets each switch by hand to match its die, then reads the pattern against the word sheet labels. It is the manual setting of each switch that counts: it turns "a word is eleven on/off choices" into something felt in the hands. It replaces the paper strip in the deluxe game; it is not an extra step.
- **Building it is a session in itself:** fitting the switches and numbering the faceplate together, before the first game, is one more practice where the generations make something side by side.

**Reset ritual.** Unlike dice, switches hold their position after the game. Closing a round therefore includes a reset: every switch is returned to 0, one by one, in number order, with the family watching, alongside tearing up the slips. It costs nothing in a practice game, and it is the right habit for any object that has held part of a seed.

### The transcription app

A small browser app on the minter's own phone that bridges the SeedSigner and the pen. It is also useful for real Type S mints, so it belongs in the Coin-tainer repo, with the game pointing to it.

- **Scan:** reads the xpub QR from the SeedSigner screen.
- **Rebuild:** regenerates the same data as a fresh QR with fixed settings (version, error correction and mask), so the fixed parts of the grid (corner squares, timing lines, alignment square, format information) can be preprinted on every envelope and only the data squares are drawn by hand.
- **Tiles:** shows the QR in zoomed sections with coordinates (A1, A2 … C3) matching the printed grid.
- **Verify:** scans the hand-drawn grid and compares it with the original: match or no match.
- **Two flows, one shared verify step:**
  - *Flow 1, trial, game or manual:* scan the xpub, show the tiles, transcribe by hand onto the envelope grid, then verify the inked copy.
  - *Flow 2, real ceremony:* scan the xpub and save it as an image file (the QR at a fixed physical size with the fingerprint beneath, laid out for Face A of the disc). The file is uploaded to the laser computer and engraved after the scrap-MDF test. The phone then verifies the engraved disc against the SeedSigner's display.
  - *Verify (both flows):* scan a reference, scan a copy, and compare the decoded text, whether the copy is ink on paper or a burn in MDF.
- **Guard:** accepts only extended public keys (`xpub`, `ypub`, `zpub` or a key-origin descriptor). Anything shaped like a SeedQR is discarded at once, never displayed or stored, with the warning: *"This was a private key. It has been discarded. Nothing was saved."*
- **Nothing leaves the phone except one public file:** runs entirely in the browser, with no network requests and no history. The only exception is Flow 2's saved image, which contains public data only; it is deleted from the phone and the laser computer once the coin is engraved and verified.

### The live ceremony (Coin-tainer repo, not the game)

In the real Self-Mint ceremony the SeedSigner has two brief display points: first the SeedQR (the private key), scanned by the Seed Hammer controller to engrave the plate; then the xpub QR, scanned by the minter's phone running the app. The phone ritual above applies unchanged, and the phone stays in its box until the SeedQR has been scanned and dismissed. The game rehearses the second display point exactly and describes the first.

A **scrutineer window** is proposed for the workshop's minting space. Anyone may watch through it: they can observe the ceremony sequence and the minter's actions, but not the data. The window sits about 5 metres from the minting table, a distance at which a SeedSigner screen or an engraved plate cannot be read by eye. It also lets observers confirm that the minter is genuinely alone, which could close the open risk in `type-s-ceremony.md` that "you are alone" is a stated precondition the ceremony never verifies.

The minting space has a single point of view, like a DJ and an audience. Every data surface faces the minter: the SeedSigner screen, the pill holder, the slips, the plate and the phone. The window faces the minter, so observers see the minter's face, hands and actions, and only the backs of the devices. A raised front panel on the minting table, above the height of the work surface, hides anything lying flat on the table.

Because the data is hidden by the layout rather than by behaviour, no camera rule is needed. Filming through the window can even become a feature: a public record of the ceremony's conduct that can never contain its data. What remains is to keep reflective surfaces out of the minter's side of the room: no glass, mirrors or glossy finishes on the wall behind the minter, where the screen's image could bounce back towards the window.

**Silent verification.** Once the window faces the minter, the voice and the lips become a data channel: a microphone would carry spoken seed words, and a zoomed camera could in principle read them from lip movements. In the live ceremony, the read-aloud steps (transcription and verification) become silent: the minter points to each word in the pill holder, then to the matching word on the device or plate. The window is sound-isolating. Reading aloud stays in the workshop's practice runs and in the game, where everything is witnessed and destroyed anyway.

**The 100th mint.** With the layout in place, the ceremony becomes a performance in its own right. The proposal is a one-off livestream of the 100th mint, from a camera mounted in the window: video only, no audio, showing the full sequence and none of the data. It marks the point at which the protocol has proven itself through repetition, and it belongs to Slow Theatre as much as to the Coin-tainer.

These changes need to be written into `type-s-ceremony.md` (steps 3 and 6 for silent verification, steps 5, 8, 12 and 13 for the two display points, plus the minting space and risk register) in the Coin-tainer repo.

### Open items

**The game**

- [ ] **Roles:** who reads, who checks, who watches, and how the minter role rotates round the table.
- [ ] **Event cards:** write them from the risk register in `type-s-ceremony.md`.
- [ ] **Rulebook,** including age guidance for handling the SeedSigner.
- [ ] **Default destruction method,** with a fire-free alternative.
- [ ] **Tile layout** for the 41 × 41 grid: how many sections and how they are labelled.
- [ ] **Testnet or mainnet** for the game. Testnet keys (`vpub`/`tpub`) could never hold real bitcoin, a second safety net behind destruction, but the flow then differs slightly from the real ceremony. The app's guard would need to accept testnet keys if chosen.
- [x] **BIP39 word sheets:** four A4 sheets with dice-pattern labels and the dice order.
- [x] **Dice method:** 12 throws of eleven numbered dice, shared round the table.
- [x] **Dice specification:** eleven black dice numbered 1 to 11, the number on three faces and blank on three, each number opposite a blank, printed not drilled, 6 and 9 underlined; parity fallback for ordinary dice.
- [ ] Order sample dice and check them: number placement and legibility from the side, and a simple fairness test (for example 200 throws per die, expecting roughly 100 numbers).

**Transcription app and the live ceremony (Coin-tainer repo)**

- [x] **SeedSigner xpub QR output type.** Confirmed from the SeedSigner source code: choosing BlueWallet as the coordinator gives a single static QR containing a key-origin descriptor, for example `[73c5da0a/84h/0h/0h]zpub…` (about 131 characters, including the 8-character fingerprint). SeedSigner encodes it with low error correction (level L), which gives a **41 × 41 grid (QR version 6)**. The envelope template and the app use the same 41 × 41 grid. The app fixes the mask pattern so the fixed parts (three corner squares, timing lines, one alignment square and format information) can be preprinted; its drawn grid may therefore differ from the device's screen square by square while encoding exactly the same text, which is what the verify step checks. The app also shows the fingerprint, to be written beneath the grid as in the real Type S coin.
- [ ] **Confirm the laser export file type.** The laser machine has not been chosen yet. Once it is, the laser software decides the file format (for example SVG, DXF or PNG) and the physical size of the QR: at 41 × 41, each square needs to be at least about 0.8 mm, so roughly 35 to 40 mm across including the white margin.
- [ ] Add the file transfer to the real ceremony's phone ritual: when the file is uploaded to the laser computer, and when it is deleted from both.
- [ ] Record in `type-s-ceremony.md` how the real ceremony supplies the 12th word's final 7 bits.
- [ ] Design the minting space: a single point of view with every data surface facing the minter, the window facing the minter at about 5 metres, a raised front panel on the table, and no reflective surfaces behind the minter.
- [ ] Update `type-s-ceremony.md` in the Coin-tainer repo to match, including silent verification at steps 3 and 6.
- [ ] Make the window sound-isolating.
- [ ] Plan the 100th-mint livestream: window-mounted camera, video only, no audio.

### Principles

- **Sold and played separately.** The base game stays neutral about what kind of money a family uses. The expansion is an invitation for families who want to go further, never a requirement.
- **Same ground rules.** Every generation present, nobody has to share numbers, and it stops when it stops being kind.
- **Built on the Self-Mint work.** Equipment, protocol and safety come from the Coin-tainer materials, not reinvented here.

## Game printables

Files in `printables/game/`.

- [x] BIP39 word sheets, four A4 pages with the dice order, in `printables/game/`
- [x] Dice strip: two word strips and one final strip, to cut out
- Envelope template with the preprinted 41 × 41 grid and fingerprint box
