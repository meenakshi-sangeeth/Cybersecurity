## Challenge

In the summer of 2007, a massive archive quietly surfaced — a meticulous ledger of items that once rolled across desert sands under foreign command. The file was structured, line after line, page after page, each entry tied to a unit whose banners flew far from home.
Someone wasn’t happy about its release. A message was sent, demanding its silence — a digital plea from a uniformed gatekeeper. The request was denied.
Your task is to uncover the sender of that plea.
Clues hide in old public archives — look for a tabular trail documenting what was once called Operation Freedom, catalogued in a comma-separated vault of** 1,996 pages** worth of equipment.
Some say the sands between two nations hold the real context — where east met west, and war turned into a spreadsheet.
Find the** email address** of the official who tried to bury the list.

Format: v1t{hello.hi@ehatever.com}

## Solution

On googling I found [this](https://www.muckrock.com/foi/united-states-of-america-10/iraq-oif-property-list-pub-date-july-27-2007-us-army-forces-command-forscom-unclassified-for-official-use-only-3287/)

```bash
According to a published report, on June 26, 2008 a 4/1 IBCT Signal Systems Technician, CW2 David J. Hoskins (david.j.hoskins@us.army.mil) sent an unclassified email to wikileaks@sunshinepress.org stating that he had discovered a web page containing sensitive information that needed to be removed due to confidentiality concerns, specifically http://wikileaks.org/wiki/B_BTRY_2-32_FA_REG_(WA1LB0). (Source: http://www.wikileaks.org/wiki/Iraq_OIF_Property_List.csv)
```

Flag: `v1t{david.j.hoskins@us.army.mil}`
