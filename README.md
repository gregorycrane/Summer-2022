# Summer-2022

---

### /

`GreekExercises.ipynb` contains some rough preliminary code for checking English -> Greek translations. As of right now, it can identify missing or incorrect accents and breathing marks, check the forms of each word, identify extraneous or missing words, and recognize when a word is valid Greek but does not belong in a particular sentence. Note that some edge cases are not being accounted for; for instance, if a word is both missing the correct accents and in the incorrect form, it is marked as invalid. Ideally, if this situation arises then the user should be alerted about both mistakes and the word should be marked as valid.

`HomericaQuizzes.ipynb` contains preliminary code for interactive exercises based on the [Homerica quizzes](https://github.com/gregorycrane/Homerica/tree/master/quizzes). As of now, error-checking is extremely basic (i.e. it can check accents and determine whether the input matches the specified answer exactly). Also: the regex I'm using to read each quiz question is not 100% accurate all the time, and probably needs to be tweaked a little.

`MultipleChoice.ipynb` is an experimentation with a couple of things: 
1. Using [Stanza](https://stanfordnlp.github.io/stanza/index.html) to create multiple-choice questions about the structure of a given sentence. Just as with `HomericaQuizzes.ipynb`, questions are drawn from `lib/quiz_questions.txt`. 
2. Generating a list of words with possible and impossible accents. The user is then asked to identify the words with impossible accents. This utilizes modules from [greek-accentuation](https://github.com/jtauber/greek-accentuation).
3. Using [greek-accentuation](https://github.com/jtauber/greek-accentuation) to break a word into syllables, ask the user to identify the antepenult, penult, or ultima of the word
4. Drill accent rules by asking the user to identify possible legal locations of a given accent
5. A single word is randomly chosen, along with several possible and impossible accentuations of that word. The user is then asked to identify all the possible accentuations.

`StanzaExercises` is an experimentation with using Stanza to create exercises and give specific feedback

`GenerateVocabList` takes as input an xml file containing all the contents of the Crosby-Schaeffer text. Grabs all of the vocabulary terms and places them into a csv file

`CrosbySchaeffer` (ultimately) will use the csv file generated by `GenerateVocabList` to check the accuracy of students' responses by allowing for multiple different correct translations 

`StanzaUgarit` imports greek sentences from each chapter of Crosby-Schaeffer (as well as their english translations), then treebanks them (using CoNLL-U format).

`GetTranslationExercises` reads through the Crosby-Schaeffer xml file and extracts all of the translation exercises, putting them into a csv file

`GenerateVerbForms` uses Stanza to find the lemmas for a list of verbs, then uses James Tauber's [greek-inflexion repo](https://github.com/jtauber/greek-inflexion) to generate all the forms of those verbs. Detailed instructions for use can be found at the top of the notebook.



---

### user-profile-system/

`user-profile-system` is an experimental django registration app created using [this](https://dev.to/earthcomfy/creating-a-django-registration-login-app-part-i-1di5) tutorial. Run `user-profile-system/user-profile.ipynb` to start up the web app.

---

### lib/

`quiz_questions.txt` contains a set of Greek sentences and their translations, drawn from `a_hs.txt`

`a_hs.txt` is a set of quiz questions based on the [Homerica quizzes](https://github.com/gregorycrane/Homerica/tree/master/quizzes). 

`CrosbySchaefferSentences - Lesson 1.tsv` contains the questions and answers from Crosby and Schaeffer Lesson 1

`tlg0012-tbankplus.txt` and `tlg0012.tlg001.perseus-grc1.tb.xml` are treebanks of the first book of the Iliad

`verbs.tsv` and `paradigms.tsv` are [lists of forms](https://github.com/jtauber/greek-inflexion/tree/master/homer-data) from Pharr's Homeric Greek

---

### lib/greek-inflexion-files

This folder contains files generated by the `GenerateForms` notebook (both intermediate and final). `all_forms.csv` contains all the present active indicative forms of a given list of verbs

`lib/greek-inflexion-files/cs_10_verbs.txt` contains all the verbs from the first 10 chapters of crosby-schaeffer

---

### lib/Crosby-Schaeffer-Lessons/

`CrosbySchaefferLesson*.csv` contains the exercises from each Crosby-Schaeffer lesson (where * is the lesson number)
