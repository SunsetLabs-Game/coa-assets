# Citizen of Arcanis assets

Contains assets for Citizen of arcanis NFT tokens.

## Contract - [ERC1155](https://eips.ethereum.org/EIPS/eip-1155#specification)

The main token contract is ERC1155. Here's a recommended standard,

## For fungible tokens (countable non-unique amount of something)
* Use only lower 128 bit ID for countable tokens - Coins can be 1, fuel can be something else, etc.
* For example, let's say coin is `0x1`, then user `0xb0bb0` could have `2356` tokens of type `0x1`. 
* Use the table below to keep a record of token IDs used in the game

### **Fungible Token IDs** (Lower 128-bit ID)

| Token ID (Hex) | Name            | Description                                | Use Case      |
|---------------|----------------|--------------------------------------------|-----------------|
| `0x1`        | Credits          | Primary in-game currency               | Trading, purchases |
| `0x100` - `0x1ff` | Some type of Ammo | Ammunition units of different types | Weapons |
| `0x100`     | Hand gun Ammo    | Pistol ammunition units                | Hand pistols |
| `0x101`     | Machine gun Ammo | AR ammunition units                    | Automatic Rifles |

## For NFTs (unique tokens like weapons/gear)
* Use first 128 bits for type of item - like weapon/armour etc
* Use the next 128 bits for a specific item ID.
* For example, let's say `0x1` is for weapons, and I have weapon number `5`. This would look like I have `1` token of type `0x100000000000000000000000000000005`
* John could have gloves number 5, if glove type is set to be `0x25`. This would look like John has `1` token of type `0x2500000000000000000000000000000005`.

### **NFT Token Prefixes** (First 128-bit ID)  

| Type Prefix (Hex) | Category       | Description                                 |
|------------------|---------------|---------------------------------------------|
| `0x1`           | Weapons        | Melee & ranged combat weapons              |
| `0x2000` - `0x2fff` | Different types of armour | Probably just 5 types in the beginning |
| `0x2000`        | Helmets        | Head protection, tactical HUDs             |
| `0x2001`        | Chest Armor    | Body armor, exoskeletons, reinforced vests |
| `0x2002`        | Leg Armor      | Leg plating, combat greaves, cyberknees    |
| `0x2003`        | Boots          | Tactical footwear, gravity stabilizers     |
| `0x2004`        | Gloves         | Combat gloves, hacking gloves, power fists |
| `0x30000` - `0x3ffff`   | Different types of vehicles                 |
| `0x800000` - `0x8fffff` | Pets/Drones    | AI companions & robotic assistants |

Total supply of all NFTs should be just `1`. The contract allows for flexibility, but let's adhere to the standards specced in this file.
