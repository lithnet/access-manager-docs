# Creating and managing word lists

When Access Manager Agent policies are configured to generate passphrases for use with local administrator accounts, they do so using *word lists* - lists of thousands of unique words that are delivered to clients in order for them to generate secure passphrases.

By default, Access Manager comes bundled with one word list: the [EFF diceware wordlist](https://www.eff.org/files/2016/07/18/eff_large_wordlist.txt) from the [Electronic Frontier Foundation](https://www.eff.org/dice), containing 7776 unique English words for use in passphrases.

If, for example, you wish to generate passphrases in a language better suited to your user base, you can import your own word lists with which Access Manager can generate passphrases.

--

Access Manager comes with a default word list used for generating passphrases. However, you can create your own custom word lists that can be used to generate LAPS passphrases. 

From the `Access Manager agent/Password settings` page, you can see the word lists currently available on your system.

![](../../images/ui-page-access-manager-agent-password-settings.png)

The built-in word lists cannot be modified, but you can duplicate or add your own word lists.

## Adding a new word list

Click the `Add..` button to add a new word list.

![](../../images/ui-page-access-manager-agent-password-settings-wordlist.png)

Click the `Import words from txt file` button to import your custom word list. The text file should have one word per line, and must contain at least 2000 individual words.

Once you save the word list, you can assign the word list to computers using the [agent policy](setting-up-agent-policies.md)

--

You can find a list of "diceware" word lists in other languages for use with Access Manager [here](https://theworld.com/~reinhold/diceware.html#Diceware%20in%20Other%20Languages|outline).
