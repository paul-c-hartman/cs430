# Names: Paul, Jenessy
# Lab: lab6 (NLP)
# Date: 3/9/26

1. The word 'is' receives the most attention from 'it'. It didn't match our intuition because we expected it to attend more strongly to words like 'suitcase'. This was because we were thinking about semantic attention instead of syntactic attention, which is what layer 1 captures.

2. [CLS] shows up at the beginning of each sentence and is meant to carry the meaning of the sentence as a whole. Many tokens attend to it because it carries the meaning of the entire sentence, rather than a dictionary meaning.

3. The model uses knowledge from other sentences, encoded in its weights, while rule-based parsers simple apply rules they know.

4. Head #3 seems to point to the previous token, whereas head #11 seems to point to the next token.

5. Attention patterns are a lot more diffuse in layer 1 than layers 8 or 12. When the model transitions to semantic processing, it is more focused on specific tokens. This might be because semantic relationships are more focused than syntactic relationships.

6. Having multiple heads lets you process more information and make more connections. This is helpful for resolving ambiguity.

7. It does consistently attend more to "trophy" than "suitcase." "Suitcase" gets more attention in a couple heads (3 and 6). Although the overall meaning that BERT understands comes from the combined attention of all heads, it should be noted that each head is specialized and only analyzes certain kinds of meaning.

8. You could start removing context from the sentence and see its initial understanding still holds up.

9. We decided that we think BERT does "understand" the sentence. This is because it can clearly understand syntax and semantics that roughly maps to human understanding of the sentence. Although it isn't sentient, it can take information from the sentence and use it meaningfully--perhaps by coming up with additional text.

10. They're pretty clearly separated. The profession and animal word clusters have a range of x values but they're separated in the y dimension. These are also the two categories which are closest to each other--this might be because of the connections between veterinarians and animals, chefs cooking animals, etc., and the fact that there aren't as many linguistic associations between countries and animals/professions.

11. Colloquialisms might cause words to be shifted closer to each other incorrectly--for example, "raining cats and dogs" might cause cats and dogs to be shifted closer to water which isn't necessarily correct. Words that are only used in very specific contexts might end up being placed far apart from other words that are linguistically similar just because they aren't as commonly used, even though the meaning is similar. Corpus-based meaning only captures how the language is used, not how it could potentially be used.

12. It did return "queen" as the top answer. The answers are all pretty plausible and unsurprising. This shows that it's learned how we use language but it doesn't necessarily understand the meaning of different words and the fact that there are many cases outside of the plausible-sounding, average ones.

13. Doctor and teacher are most strongly associated with "man" and doctor, nurse, and teacher are most strongly associated with "woman." It definitely takes both linguistic reality and social stereotypes into account, since they are equivalent in some ways. Linguistic reality can be different from social stereotypes but it's difficult to know; the only way to try to prevent stereotypes from affecting these models is to look at the linguistic reality of the training data that's used. Another thing to think about: do you want a tool like this to be less biased than the people using it?

14. Highest scores: "disaster," "brilliant," and the period at the end of the sentence. They do seem intuitively most important. The model might be sensitive to punctuation overall because its training data led it to care about transitions between sentences; it might also be sensitive to punctuation because it learned to use punctuation similarly to [CLS] or [SEP]--as semantic summaries or tools.

15. "Disaster" scores higher. The mode likes to prioritize negative sentiment overall--we tried switching the sentence around--"The film was surprisingly disastrous but the ending was brilliant"--and the model still thought the sentence was negative. We also tested just using the words "good" and "bad" and got similar results.

16. Masking "disaster" caused the largest drop in confidence and caused the predicted label to flip. From these results, it looks like tokens with high saliency scores correspond to high causal importance but this is not a hard rule. "Disaster" also had the highest saliency score, which follows this prediction, but "brilliant" had the smallest confidence change despite having higher saliency scores than either "was" or "surprisingly."

17. Gradient sensitivity is a token's importance to the sentence it is in. Causal importance is the potential for a masked token to decide the meaning of a sentence. The space and role of a token with high causal importance can change the meaning of a sentence moreso than those of other tokens.

18. The confidence shift for negation is larger on average than swapping positive and negative words, so it looks like the model weights negation higher than lexical sentiment changes.

19. The model's prediction does not change meaningfully at all. This shows that while the model does take sentiment-bearing adjectives into account, as seen in the other examples, it does not always depend on them.