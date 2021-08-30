# NameMatching
Name Matching Algorithm in R
This technique is based on common understanding and basic principles of name matching. It was developed as part of a specialized project. And requires great amount of data cleaning prior to the use of the algorithm (including steps like removing stop words/common words, consolidating common words, and consolidating different ways of writing a word/abbreviations/partial abbreviations, etc.) 
The algorithm is developed and used in R.
Basically two different algorithms are combined to create this algorithm.
First algorithm was inspired from the NGram analysis and used in the following way:

Lets take the word TOM. It can be broken down into 6 possible NGrams (letters)

TOM = 'T', '0', 'M', 'TO','OM', 'TOM' = 6

Now the word TIME. It can be broken down into 10 possible NGrams (letters)

TIME = 'T', 'I', 'M', 'E', 'TI','IM','ME', 'TIM', 'IME','TIME' = 10

Minimum no. of total combinations of the two words = min(6,10) = 6

Number of NGrams overlap = 2 ('T' and 'M')

Overlap ratio = 2/6 = 0.3333 

Upon experimentation, we found it to be useful to boost this ratio up for when the two words start with the same letter (T in this case). Mainly because two words that are to be the same, the boosting factor depends on the application, and can range from 0 to 0.25 points. 

Another algorithm used was the Demarau Levenstein ALGORITHM or the DL Algorithm

The algorithm looks into how many switches/additions/subtractions does it take for changing a word A to B

A-> B

TIM -> TOM = 1
From TIM to TOM we need to switch  I with O

KAMRAN -> CAMERON = 3
In this case, we need to switch K with C, followed by the addition of E after M, and then switching the last A with O

The smaller the number of actions, the better (comparative to the size of the word)

We use the two algorithms together and let both of them together find the matching of different words.
