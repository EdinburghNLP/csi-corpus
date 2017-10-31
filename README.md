# csi-corpus

This repository contains annotated screenplays [1] for 39 CSI:Crime Scene Investigation episodes
from seasons 1--5. Each episode contains 
1. word-level gold standard entity annotations using three types (perpetrator, suspect, other),
2. human behavioral perpetrator guesses (sentence-level), and 
3. case disambiguation information for episodes featuring two cases
(sentence-level).

If you would like to obtain the visual and auditory features used in
this work please email l.frermann@ed.ac.uk. Please note that in order
for us to make these available to you, you must purchase the CSI:Crime Scene Investigation DVDs (seasons 1-5) which are available on sites like
Amazon and eBay. 

If you use this data in your research please cite the following paper:

Lea Frermann, Shay B. Cohen, Mirella Lapata (2017) Whodunnit? Crime Drama as a Case for Natural 
Language Understanding. Transactions of the Association for Computational 
Linguistics (TACL).

## Annotation Format

Each file contains the screenplay corresponding to one CSI episode (identified 
in the title), one word per line. It contains the following annotations in 
tab-separated columns

- CaseID: indicates which case the sentence is relevant to (some
episodes cover two cases)

- sentID: sentence counter (case specific)

- speaker: speaker of the utterance (None for scene descriptions)

- word: the actual word of the utterance

- killer_gold: binary indicator whether word refers to perpetrator (word-level 
label)

- other_gold: binary indicator whether word refers to suspect (word-level label)

- suspect_gold: binary indicator whether word refers to any other participant 
in the plot (word-level label)

- human_guess: human behavioral perpetrator guesses when watching the episode 
for the first time (sentence-level label)

- medion_time: mid-point of video segment corresponding to current sentence

- start_time: start time of video segment corresponding to current sentence

- end_time: end time of video segment corrqesponding to current sentence

- i1_time--i5_time: five equally spaced time points covering video
segment corresponding to current sentence. Audio feature samples were
taken at these points. 

Note that except for the columns 'word', 'killer_gold',
'suspect_gold', and 'other_gold' all labels are provided on the
sentence-level (i.e., invariant for words in the same sentence).


-----------------------------------------------------------------------------
[1] screenplays were downloaded from http://transcripts.foreverdreaming.org/

