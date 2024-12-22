# Backtrack

## Challenge Description

Kenji is a nice guy who lives in Tokyo. He is in a dilemma. In 2017, he was late to an important meeting and is now facing repercussions. To defend himself, he needs to prove that it was not his fault. His evidence? The train he boarded that day, traveling between Omotesandō and Suitengumae, was delayed. However, his boss is not providing the specific details of the accusation. Kenji vividly remembers one key fact: the train was around 61 minutes late. Help him uncover the exact date of the incident and the start time of the delay. Justice for Kenji!
Flag Format: nite{time_date} Example: nite{13:00_3January}

## Solution

Firstly I Googled for news articles or records that mentions train delays of 61 minutes or longer, as such long delays are relatively rare in Japan's highly efficient train system but that was of no use. Then I went to the official website of [Tokyo Metro](https://www.tokyometro.jp/lang_en/index.html) and searched for "Omotesando" in the "Route/Station Information" tab. I looked for the route line through which the train passes through Suitengumae and that was Hanzomon line

![image](https://github.com/user-attachments/assets/a635f209-d1f3-4aad-9dfb-1a23bbff4351)

If you search for the delay certificate, you can only access the delay certificates dating back approximately a month. We need the delay certificate from 2017. That's when [Wayback Machine Archive](https://web.archive.org/) comes into play. I entered the URL of Hanzomon Delay Certificate and searched for the data in 2017, which gave me the following result

![image](https://github.com/user-attachments/assets/7989c2e3-e9b6-49ce-8a39-5ddaf1d03e67)

I scrolled through each of the snapshots until I found this

![image](https://github.com/user-attachments/assets/dd187db7-c9b6-4816-bc1d-5730dc328e37)

Thus the flag for this challenge is nite{17:00_20February}





