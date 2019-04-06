## I apologize for the terrible state of the UAT notebook. It's assembled over several weeks and the variable naming, function calls, etc... are a disaster at the moment. After utilizations are narrowed and abstraction is more apparent, clean, readable scripts will follow.

# perspective_sentiment_analysis
A set of tools for analyzing repeated speech, such as political speeches or motivational speeches. Auto detects common phrases within a set of text from a single source, or between multiple speakers to do comparative analysis. The final result is a pandas dataframe with the original sentence index, sentence, speaker, splitting phrase, prelude phrase, and postfix phrase.

It's intended development was for analyzing repeated text that has small differences in speech or writing behavior. Political speech of Hillary Clinton and Donald Trump were chosen because they offer the same time period, approximately the same number of speeches, same goal, and yet are easily distinguishable in their perspectives on certain phrases.

# Major Goals Of This Project
By splitting the sentences into two parts along with a common phrase, the speech/text becomes searchable by a phrase. This will enable faster exploratory analysis of large amounts of text.

This also enables sentiment analysis to be used on the prelude and the postfix of auto-parsed sentences. This removes any inherent bias or perspective of a particular issue from the sentence that might trip up systems like Vader. Thus, hot button issues can be analyzed more easily.

It also allows for perspective injection into sentiment analysis. If a listener/reader views that phrase negatively, and the surrounding sentiment of the sentence is negative, then it is an agreeable sentence. If the polarity of the view and the sentence sentiment are different, then it is a challenging sentence. Thus, it can enable prediction of whether someone will view a sentence positively or negatively based on previously held beliefs.

Sentence splitting is also an anonymizing function on sentences. When comparing speech/written patterns of word use, sentence construction, and others, the prelude and postfix can be targeted for similarity analysis regardless of whether the speaker/writer are discussing the same topic.
