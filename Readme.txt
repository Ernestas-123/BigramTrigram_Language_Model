*Note Make sure input file has < s> at the start of each sentence and < /s> at the end of each sentence. Each sentence must be on the same line, as the model reads line by line. Ensure there are no special or different format characters that might interfere in the file.

*Note: When selecting the 'first word' to input, the word selected must have been at the start of a atleast 1 sentence in the file (used to train the model). i.e in the file there are a lot of sentences in the form: < s> word1, word2, word3 etc < /s>. Your word you input into the model must be like word1, AFTER < s>. Otherwise you will receive a key error.

This can be fixed by modifying the model to first input a word, use bigram conditional probabilities, then switch to trigram conditional probabilities. But even then depending on the size of your file you can receive a key error. i.e you use a word not used in the training file.

It took too long for my computer to load "sentences_long.txt". So online I found "Reservoir Sampling" which takes a sample of known size q from a population n, where n is unknown quantity.

This randomly samples a 0.1, 1%, 10%, 20% etc of the 1 million lines in "sentences_long.txt" and creates and stores them in a seperate .txt file called "sentences_sample.txt". With each line having 1/n chance to be selected.

This sample can be shown that the class trigram_language_model works with different .txt files of similar format.