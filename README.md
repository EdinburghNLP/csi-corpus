This repository contains two datasets derived from annotates screenplays [1] for 39 CSI:Crime Scene Investigation episodes
from seasons 1-5. Each episode contains.

1. The Perpetrator Identification corpus
2. The Screenplay Summarization corpus

# Perpetrator Identification corpus

The directory data_perpetrator_identification contains human annotations of perpetrator methions in 39 CSI episodes, as presented
in the following paper:

Lea Frermann, Shay B. Cohen, Mirella Lapata (2017) Whodunnit? Crime Drama as a Case for Natural 
Language Understanding. Transactions of the Association for Computational 
Linguistics (TACL).

Please cite the following paper if you use this data in your research.

The annotations include:

1. word-level gold standard entity annotations using three types (perpetrator, suspect, other)
2. human behavioral perpetrator guesses (sentence-level)
3. case disambiguation information for episodes featuring two cases
(sentence-level).

If you would like to obtain the visual and auditory features used in
this work please email lea.frermann@unimelb.edu.au. Please note that in order
for us to make these available to you, you must purchase the CSI:Crime Scene Investigation DVDs (seasons 1-5) which are available on sites like
Amazon and eBay. 

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

- other_gold: binary indicator whether word refers to any other participant
in the plot (word-level label)

- suspect_gold: binary indicator whether word refers to suspect (word-level label)

- human_guess: human behavioral perpetrator guesses when watching the episode 
for the first time (sentence-level label)

- medion_time: mid-point of video segment corresponding to current sentence

- start_time: start time of video segment corresponding to current sentence

- end_time: end time of video segment corrqesponding to current sentence

- i1_time-i5_time: five equally spaced time points covering video
segment corresponding to current sentence. Audio feature samples were
taken at these points. 

Note that except for the columns 'word', 'killer_gold',
'suspect_gold', and 'other_gold' all labels are provided on the
sentence-level (i.e., their values are invariant for words in the same sentence).


# Screenplay Summarization corpus

The directory data_summarization contains human annotations for the summary of each episode in the dataset. The dataset has been introduced and used in the paper [*Screenplay Summarization Using Latent Narrative Structure*](https://arxiv.org/pdf/2004.12727.pdf).

The annotations include:

1. scene-level binary labels denoting whether the scene belongs to the summary of the episode
2. aspect-based labels for the scenes that belong to the summary, i.e., which aspect of the episode summary the scene addresses
3. sentence-level binary labels denoting the sentences of the screenplay that belong to the summary for 10 episodes of the dataset

Please cite the following paper if you use this data in your research:

@article{papalampidi2020screenplay,
  title={Screenplay Summarization Using Latent Narrative Structure},
  author={Papalampidi, Pinelopi and Keller, Frank and Frermann, Lea and Lapata, Mirella},
  journal={arXiv preprint arXiv:2004.12727},
  year={2020}
}

## Annotation Format

### scene_level_n_aspects folder 

This folder includes the scene-level summary annotations alongside with the aspect-based labels. It contains 39 csv files, each one corresponding to a CSI episode. Each csv file contains the following information in tab-separated columns:

- scene_id: the index of the scene in the episode

- scene_text: the text included in the screenplay scene separated in sentences

- in_summary: binary label; 1 if scene is part of the summary, 0 otherwise

- aspects: aspect of the summary that the scene corresponds to; a summary scene can refer to more than one aspects or none

Set of aspects that are considered for a CSI summary:

- Crime scene

- Victim

- Death cause

- Evidence

- Perpertrator

- Motive

### sentence_level folder

This folder includes the sentence-level summary annotations for 10 episodes. It contains 10 csv files, each one corresponding to a CSI episode. ach csv file contains the following information in tab-separated columns:

- scene_id: the index of the scene in the episode

- sentence_id: the index of the sentence in the current scene

- sentence_text: the screenplay text corresponding to the current sentence 

- in_summary: binary label; 1 if sentence is part of the summary, 0 otherwise

-----------------------------------------------------------------------------
[1] screenplays were downloaded from http://transcripts.foreverdreaming.org/

