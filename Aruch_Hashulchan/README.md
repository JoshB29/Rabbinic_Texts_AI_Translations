# AI draft translation of Aruch Hashulchan 

This repository contains an AI generated draft translation of the Aruch Hashulchan on Orach Chaim. 
`AH_Translation_Orach_Chaim.pdf` contains a PDF version of the text (careful, its more than 3000 pages!), while `ah_oc_gpt4_translation_full.json` contains a JSON serialized object that can be analyzed programmatically.

# Overview
To create this translation, I downloaded the Aruch Hashulchan Hebrew text from [Sefaria](https://www.sefaria.org/Arukh_HaShulchan?tab=contents), specifically, the file `Arukh HaShulchan - he - Arukh HaShulchan, Orach Chayim -- Wikisource.json`. I then passed seif by seif, each hebrew text to OpenAI's GPT4o model (with a temperature parameter of .7), prompting it to translate the text. The result is then saved. The total cost for processing this amount of text and getting the translation was about $50.
For Yoreh Deah, I had to combine two different files from Sefaria `Arukh HaShulchan - he - Arukh HaShulchan, Yoreh De'ah -- Wikisource.json` and `Arukh HaShulchan - he - Aruch HaShulchan, Vilna 1923-29.json`

Note that the `ah_oc_gpt4_translation_full.json` file storing the raw translations has the same schema as the original Sefaria. 



# Brief Impressions

I have not extensively benchmarked the output, but my overall assessment is that the translation is preverytty good, at least as a draft translation albeit which sometimes has clunky language or is not 100% precise. Here are a few examples:

 I have noticed that the model sometimes translates "רבינו הבית יוסף" as "Rabbeinu the Beit Yosef" rather than the smoother "Our Rabbi, the Beit Yosef". 

The translation sometimes adds translation of technical terms that are strictly speaking not part of the original. For example, the very first sentence of the translation of Yoreh Deah is " Shechita (ritual slaughter) is a positive commandment. " The Aruch Hashulchan himself never defines shechita as ritual slaughter.

In Yoreh Deah 92:44, the translated text is "And in England andother places, they do not cook without a cover, and in this case, it is all the same as mentioned in subsection 46." I do not know wht the correct translation of "ובענגלש"ע קיכי"ן " is, but this translation is certainly not correct. 

In YD 2:5, it translates "עבריין לתיאבון" as a "A habitual sinner", but this is strictly speaking not correct, as לתיאבון does not mean habitual. 

It should also be noted that since I pass each seif to the model seperately from other seifim, this is likely to lead to some errors do to the model not understanding the context of what was said before. 

I would be interested to see what other errors people find. 

# Note
Special thanks to my father, Rabbi Michael Broyde, and Emory University's Law and Religion Center, which funded the model calls for this project. Thank you of course also to Sefaria for publishing the original hebrew text.


