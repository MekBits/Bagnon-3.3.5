# Bagnon for 3.3.5

Bagnon by Tuller and Jaliborc, as backported to WoW 3.3.5a by
[RichSteini/Bagnon-3.3.5](https://github.com/RichSteini/Bagnon-3.3.5). This
fork adds one fix.

## Buying guild bank tabs

In `Bagnon_GuildBank` a guild master could not buy a new guild bank tab: a click
on a tab that has not been bought only switched to it. The purchase dialog lives
in Blizzard's guild bank UI, which Bagnon replaces, so it never showed.

Now the next tab in line shows *Purchase guild bank tab* with its cost in the
tooltip, and a click opens the normal confirmation dialog
(`CONFIRM_BUY_GUILDBANK_TAB`, `BuyGuildBankTab()`). Only the guild master sees
it, and only for the next tab (`GetNumGuildBankTabs() + 1`), which is all the
server accepts.

## Installation

Copy the `Bagnon*` folders into `Interface/AddOns/`.
