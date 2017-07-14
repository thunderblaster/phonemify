# phonemify
node module to convert text to phonemes

## Install
```npm install phonemify```

## Use
The first and only required parameter is the string to be converted to its phoneme form.  
```javascript
var phonemify = require('phonemify');

var phonemesOfText = phonemify("Hello World!");
```

output:

`HH AH0 - L OW1  W ER1 L D`

The second (optional) parameter is the separator between words.  This defaults to two spaces.

```javascript
var phonemify = require('phonemify');

var phonemesOfText = phonemify("Hello World!", "|");
```

output:

`HH AH0 - L OW1|W ER1 L D`

## Arpabet and Phoneme Representation
Phonemify uses [Arpabet](https://en.wikipedia.org/wiki/Arpabet) to represent phonemes.  Here is a quick list of the phonemes 
and how they are designated:
```
Phoneme Example Translation
------- ------- -----------
AA      odd     AA D
AE      at      AE T
AH      hut     HH AH T
AO      ought   AO T
AW      cow     K AW
AY      hide    HH AY D
B       be      B IY
CH      cheese  CH IY Z
D       dee     D IY
DH      thee    DH IY
EH      Ed      EH D
ER      hurt    HH ER T
EY      ate     EY T
F       fee     F IY
G       green   G R IY N
HH      he      HH IY
IH      it      IH T
IY      eat     IY T
JH      gee     JH IY
K       key     K IY
L       lee     L IY
M       me      M IY
N       knee    N IY
NG      ping    P IH NG
OW      oat     OW T
OY      toy     T OY
P       pee     P IY
R       read    R IY D
S       sea     S IY
SH      she     SH IY
T       tea     T IY
TH      theta   TH EY T AH
UH      hood    HH UH D
UW      two     T UW
V       vee     V IY
W       we      W IY
Y       yield   Y IY L D
Z       zee     Z IY
ZH      seizure S IY ZH ER
```

## Accuracy
Accuracy will vary depending on a number of factors, but some points to note:

 1. Phonemify translates each word independent of context, i.e. it does **not** know part of speech and will translate *read*
 the same in both "I read the book yesterday" and "I will read the book tomorrow".
 2. Words present in [cmudict](http://www.speech.cs.cmu.edu/cgi-bin/cmudict) were translated by a human and should be correct.
 Words not present in cmudict (primarily slang and proper nouns) are translated using the Navy Research Lab algorithm, which
 is very good, but there is no gaurantee that any given word is correct.
 3. Typos and misspellings will, of course, lead to unexpected results.
