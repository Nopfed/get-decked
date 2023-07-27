# Get Decked!

A silly, open-source card game about putting on equipment and fighting.

## Description

This game is intended to be fun, silly and fantastic. There is no rule that can't be broken. Cards will take precedence over the core system rules, and when all else fails, as long as all players agree on an outcome, that's the outcome that happens.

The main objective is to be the last player standing, fully equipped in gear.

Choose a species to play as and build a deck around that species, perhaps themed around a certain type of character class (Warrior, Mage, Rogue, etc.). Species will differ in how they don their armor and weapons, such as requiring a different total number of items, multiple items of the same type, or some slots completely empty. In general, most classes start with the same basic setup of equipment slots, but they might be modified in some ways.

## How to play

Each player has 20 life points and two decks: one for equipment and one for fighting/interacting with opponents. 

Each turn, fill your hand up to 5 cards by drawing from either deck (do not draw unless you have < 5 cards in hand). During your turn you can equip gear or play attack cards in any order (but the order may be specified on the cards for certain interactions). Your turn is finished when you have no more cards to play or interact with on the playing field, or when you choose not to play any more cards (pass the turn). Some cards may be played during another player's turn, denoted somewhere on the card (usually this will only be attack cards and not equipment cards).

The goal is to equip all of your gear and be the last player standing. The order in which you do so is up to you. **TODO: This needs playtesting to find the right balance of gameplay.**

## Deckbuilding Rules

Each player will have two decks: one for wearing things and one for fighting things. Each deck can be any size, but should be no less than 30 cards each and should be able to be shuffled in a reasonable manner/time before playing. (If you're feeling chaotic, go ahead and shuffle the decks together and play with one deck, just don't get mad when you draw five pairs of pants in a row when you want to attack.)

A single deck, whether it is an equipment deck or attack deck (or both), can only have up to two copies of each unique card, except cards of Legendary rarity, which a deck can only contain a single copy.

## Gameplay Rules

A player loses when their life becomes 0. If all players still standing have no cards in their decks or hands, and are not able to interact with any cards on their side of the playing field in a meaningful way that could win them the game, the game is a draw for any players still standing.

When a card is played, all players have a chance to respond in turn order, if there is no response, the card and its effects are resolved and the card is considered played.

Played cards that do not remain in play are placed in their owner's discard pile.

Equipment that becomes unequipped unintentionally (falls off or is forceably removed by an opponent, etc.) is not discarded, but is instead placed on "the ground." The Ground is a field of play where items can exist during play. They are not considered equipped, and any player may interact with cards on the ground during their turn.

Only one piece of equipment can be equipped per turn and only during a player's turn. **TODO: this needs playtesting**

**TODO: Summonable minions mechanic?**

## Species

Different species are listed below and have varying equipment slots. Slot restrictions and extra slots are listed in parentheses (). Extra slots listed this way are not required to be filled to win.

<details>
  <summary>Human - Basic character option. Best for new players. Can wear pretty much everything any human could wear or hold.</summary>
  
  Class: Humanoid

  - Head (eyes, ears, nose, lips, face) (can also wear pants items on head)
  - Neck 
  - Shoulders (can wear two different shoulder items at half the potency of their effects)
  - Chest (can wear multiple thin layers underneath armor)
  - Waist (same as neck slot)
  - Legs
  - (Wrists) (can wear multiple lightweight wrists such as bracelets)
  - Hands (can wear two different gloves at half the potency of each of their effects)
  - Finger x2 (Finger x6)
  - Feet (Can wear two different feet items at half the potency of their effects) (Ankle x2 similar to wrists) (Toe x10)

</details>

<details>
  <summary>Octopode - Can wear almost anything on its eight tentacles. Resistant to fire damage.</summary>

  Class: Cephalopod
  
  - Head (eyes, beak, face)
  - Neck/Waist
  - Tentacle x8 (Can hold/wear everything except helmets.)

</details>

<details>
  <summary>Spider - Similar to the octopus, but can't equip any weapons. Has special attacks for fangs and stinger.</summary>

  Class: Arthropod
  
  - Head (fangs, face, eyes)
  - Neck
  - Leg x8 (Can wear anything except helmets, can't hold anything.)

</details>

<details>
  <summary>Centaur - Similar to human, but can wear two pairs of pants! Resistant to magic damage.</summary>

  Class: Humanoid, Horseanoid
  
  - Head (eyes, ears, nose, lips, face) (can also wear pants items on head)
  - Neck (can wear any number of necklaces, but for each added necklace **TODO: some sort of hinderance goes here**)
  - Shoulders (can wear two different shoulder items at half the potency of their effects)
  - Chest (can wear multiple thin layers underneath armor)
  - Waist (same as neck slot)
  - Legs x2 (Both leg slots can filled with 1 horse armor, or 2 horse armors at half their potency)
  - (Wrists) (can wear multiple lightweight wrists such as bracelets)
  - Hands
  - Finger x2 (Finger x6)
  - Feet (Can wear 4 different feet items at 1/4 the potency of their effects) (Ankle x2 similar to wrists)

</details>

## Elements

Cards, equipment, species and effects may be elementally attuned. Elements come into play when interacting with other element types, such as Fire is weak against Water. Full element list can be found below as well as the matchup table.

![Element Matchups](https://github.com/Nopfed/get-decked/assets/15887241/4437306e-a0f0-46e5-823e-fa919364d1ef)


Elements can also be combined with other elements that form new combination element types, and are also treated as their base element types. For example, Water combined with Fire makes Steam, Shock and Holy makes Smite. The full table can be found below. If for whatever reason 3 elements were to be combined, they become the Null element. Any element mixed with Null becomes the non-Null element (Air combined with Null makes Air). Null combined with Null makes Null. Below is a table of the elemental combinations. 

![Elemental Combos](https://github.com/Nopfed/get-decked/assets/15887241/c141b6aa-aef3-42d1-8dfd-2718ec7fc234)


## Card Types

There are two main categories of cards (for each of the two decks you play with): Equipment and Combat.

Cards are stored in YAML format for reading and writing purposes. There will also be a script for converting to CSV for importing into software that uses spreadsheet format, such as nanDeck. **TODO: Link to nanDeck software.**

**TODO: Script to convert YAML to CSV.**

**TODO: CSV list of Core Set.**

Example of the card "Punch" in YAML format:

```
combat:
  - attack:
    - Punch:
        rarity: Common
        action_text: Deal 1 physical damage.
        flavor_text: "A simple jab."

```

### Equipment Cards

Equipment cards mostly represent physical items that your character will wear/put on. There will also be utlity spells that interact with cards in your deck(s).

Cards will be categorized under which slot they can be equipped to, and any additional slots in which they can be equipped will be noted somewhere on the card. Below is an example.

```
- hand:
    - Loose Gloves:
        rarity: Common
        action_text: Can't equip more rings to any hands wearing these gloves.
        flavor_text: "Definitely need to put the rings on first before these."
```

The above is also an example of a card where order of equip matters.

### Combat Cards

Combat cards are mostly used for hindering/harming your opponent(s). Spells, attacks, interactions with equipment, etc.

Spell cards are anything that are based in fantasy magic, such as shooting a fireball or putting up a defensive barrier.

Attacks are very simple cards that have no magic involved and typically deal physical damage only or are physical in nature.

Abilities are non-damaging cards and are more utility centric, such as performing "crowd control," or interacting with other cards.

Weapons are cards that you can equip, but are part of the combat deck because you can deal damage with them. Each weapon will have a damage value associated with it in addition to other card fields.

```
  - weapon:
    - Warrior's Blade:
        rarity: Common
        damage: 3
        action_text: 
        flavor_text: "Solid steel fit for any warrior."
```

## Optional Chaos Deck

There is an optional deck to play with that makes the game more fun/chaotic/random. It has very powerful effects that can affect one or more players, turning the favor randomly. Can be a physically printed deck or just a QR code that is scanned for a chaos effect. **TODO: Make chaos cards.**

**TODO: Look into custom QR codes.**
