# D2Etal MuleDropper

# Introduction
Etal is a project of D2NT Diablo 2 bot. It has an official script called AutoMulingSystem which can transfer items to mules when the main character is full. However, items in mules are not categorized, so it takes time to collect the items you need from different mules. The Etal MuleDropper is an Etal script to drop specified items in assigned accounts. It allows you to collect the items in mules you need efficiently. You can set the mules to drop gems, rune sets, or Uber key while use other mules to categorize and store these items. (Basically, you need to have multi-CDKey and multi-instance of Diablo II on a single computer to do this yourself.)

# How it works?
The script logs in every characters in assigned accounts. Each character joins a specified game (you need to create this game manually beforehand), drop items, and the script will log the inventory/stash of this character. Next, the character will stay for minimum game length (to avoid realm down), and then the script will switch to the next character or the next account.

# Guides
## Installation
Clone the repository to your computer.
Copy three things into your D2Etal folder:
D2Etal_MuleDropper\scripts\CMMuleDrop.ntj to D2Etal\scripts
D2Etal_MuleDropper\scripts\NTBot\bots\CMDropper.ntj to D2Etal\scripts\NTBot\bots
D2Etal_MuleDropper\scripts\libs\common\CMAction.ntl to D2Etal\scripts\libs\common
Add folders
add a folder named CMDrop to D2Etal\scripts
add a folder named Status to D2Etal\scripts\CMDrop

## Configuration
in D2Etal\scripts\CMMuleDrop.ntj
Set the game name to join and the game password. e.g. game = "example_abc"; password = "example_123";
Set the accounts to log in. e.g. var accNames = ["accounts1", "accounts2", "accounts3"] (all accounts must have the same password)
in D2Etal\scripts\NTBot\bots\CMDropper.ntj
Set the items you want to drop. The format is [itemid1, itemid2, itemid3, ...]. You can find the item id in D2Etal\sdk\classid.txt e.g. var items = [647, 648, 649]; will drop Uber keys.

## Usage
Use a character to create a game manually. The game name and password must be the same with configuration in CMMuleDrop.ntj.
Turn on the Etal Manager and change a profile's entry point to CMMuleDrop.ntj. Run it.
