## I apologize for the terrible state of the UAT notebook. It's assembled over several weeks and the variable naming, function calls, etc... are a disaster at the moment. After utilizations are narrowed and abstraction is more apparent, clean, readable scripts will follow.

# perspective_sentiment_analysis
A set of tools for analyzing *repeated* speech, such as political speeches or motivational speeches. While there are a lot of tools out there that can do sentiment analysis on a single sentence, or on a corpus of original text, repeated speech is often neglected as its own unique kind of langauge. The same themes will appear within a single speaker's corpus, but with variations as new wordings are tested. Or, multiple speakers will speak on the same subject, with similar phrasology, but differ in how they speak about it.

In this way, similar speech should be analyzed around the perspective on the phrases and not just on an entire sentence.

But this presents an issue. In large bodies of text, from a single speaker or a variety, finding actual common phrases is a manual process and may struggle to achieve good coverage. There may also be additional phrases that appear, but are unknown to the analyst. One part of solving the problem of perspective sentiment analysis is to identify common phrases that have n-duplications in the corpus. This is built around a seed word or seed phrase to scrape the text and identify instances and variations.

The POC notebook contains code that auto detects common phrases within a set of text from a single source, or between multiple speakers to do comparative analysis. It operates off of a seed and the length of words before and after to search for phrase variations. The final result is a pandas dataframe with the original sentence index, sentence, speaker, splitting phrase, prelude phrase, and postfix phrase.

Political speech of Hillary Clinton and Donald Trump were chosen because they offer the same time period, approximately the same number of speeches, same goal, and yet are easily distinguishable in their perspectives on certain phrases. This makes the two corpuses a viable sample set to judge outputs against intutition.

# Major Goals Of This Project
By splitting the sentences into two parts along with a common phrase, the speech/text becomes searchable by a phrase. This will enable faster exploratory analysis of large amounts of text.

This also enables sentiment analysis to be used on the prelude and the postfix of auto-parsed sentences. This removes any inherent bias or perspective of a particular issue from the sentence that might trip up systems like Vader. Thus, hot button issues can be analyzed more easily.

It also allows for perspective injection into sentiment analysis. If a listener/reader views that phrase negatively, and the surrounding sentiment of the sentence is negative, then it is an agreeable sentence. If the polarity of the view and the sentence sentiment are different, then it is a challenging sentence. Thus, it can enable prediction of whether someone will view a sentence positively or negatively based on previously held beliefs.

Sentence splitting is also an anonymizing function on sentences. When comparing speech/written patterns of word use, sentence construction, and others, the prelude and postfix can be targeted for similarity analysis regardless of whether the speaker/writer are discussing the same topic.

Sentence-Phrase structure identification, such as beginning negatively and ending positively. If POV injection is not possible, at least speech stucture should enable additional analysis.
