Text documents, such as crawled web data, are usually comprised of topically coherent text
data, which within each topically coherent data, one would expect that the word usage
demonstrates more consistent lexical distributions than that across data-set. A linear partition of
texts into topic segments can be used for text analysis tasks, such as passage retrieval in IR
(information retrieval), document summarization, recommender systems, and learning-to-rank
methods.


# Task 1: Parsing Raw Text Files


touches the very first step of analyzing textual data, i.e., extracting data
from semi-structured text files. Each student is provided with a data-set that contains
information about several units in the Monash University (please find your own file from this link,
i.e., <your_student_number>.txt ). Each data-set contains information about the unit, e.g., unit
code, unit title, synopsis, requirements, output, chief examiner, etc. ( see test.txt ). Your task is to
extract the data and transform the data into the XML and JSON format with the following
elements:
1. Unit code: is a 7-character string (three uppercase letter followed by 4 digits).
2. Pre-requisites: only the unit codes of the units that are pre-requisite + co-requisite for
the current unit (‘NA’ if the value is Null).
3. Prohibitions: only the unit codes of the units that are prohibited to be taken with the
current unit (‘NA’ if the value is Null).
4. Synopsis: a string containing the synopsis of the unit (‘NA’ if the value is Null)
5. Requirements: the list of requirements of the current unit (‘NA’ if the value is Null).
6. Outputs: the list of outputs of the current unit (‘NA’ if the value is Null).
7. Chief-examiners: the list of the chief-examiners of the current unit (‘TBA’ if Null).




# Task 2: Text Pre-Processing

touches on the next step of analyzing textual data, i.e., converting the extracted
data into a proper format. In this assessment, you are required to write Python code to
preprocess a set of unit information and convert them into numerical representations (which are
suitable for input into recommender-systems/ information-retrieval algorithms).
The data-set that we provide contains 400 unit information crawled from Monash University.
Please find your pdf file from this link.The pdf file contains a table in which each row contains
information about a unit which is unit code, synopsis, and requirements. Your task is to extract
and transform the information for each unit into a vector space model considering the following
rules:
Generating sparse representations for the unit information
In this task, you need to build sparse representations for the unit information, which includes
word tokenization, vocabulary generation, and the generation of sparse representations.
Please note that the following tasks must be performed ( not necessarily in the same order ) to
complete the assessment.
1. The word tokenization must use the following regular expression, "\w+(?:[-']\w+)?"
2. The context-independent and context-dependent (with the threshold set to %95) stop
words must be removed from the vocab. The stop words list (i.e, stopwords_en.txt )
provided in the zip file must be used.
3. Tokens should be stemmed using the Porter stemmer.
4. Rare tokens (with the threshold set to %5) must be removed from the vocab.
5. Tokens must be normalized to lowercase except the capital tokens appeared in the
middle of a sentence/line.
6. Tokens with the length less than 3 should be removed from the vocab.
7. First 200 meaningful bigrams (i.e., collocations) must be included in the vocab using
PMI measure.
