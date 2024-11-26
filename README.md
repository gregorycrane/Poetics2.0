# Aristotle, Poetics 2.0

## Project Goals 

This project works towards a truly digital edition of Aristotle's Poetics. While the project will evolve over time, our initial goals including the following:

1. Opening up the Greek text to audiences with no knowledge of the language.

2. Providing new services to advanced researchers on Aristotle.

3. Creating a framework whereby audiences can develop as much command of the source as they need or wish to possess.

4. Structuring our information to serve, as effectively as possible, audiences familiar with many different languages and from many different backgrounds.


## Available Greek Texts

1. The Perseus Digital Library has included [the 1966 Rudolf Kassel edition](https://www.perseus.tufts.edu/hopper/text?doc=Perseus%3Atext%3A1999.01.0055%3Asection%3D1447a). This Greek file has not yet been updated and remains in beta code on the local Perseus file structure as: texts/Classics/Aristotle/copyright/aristot.poet_gk.xml. This file opens:

```
<text n="Poet."><body><p>
<milestone unit="section" n="1447a"/>
<milestone ed="Bekker" unit="line" n="8"/><milestone ed="P" unit="para"/>
peri\ poihtikh=s au)th=s te kai\ tw=n ei)dw=n au)th=s, h(/n tina du/namin e(/kaston e)/xei,
kai\ pw=s dei= suni/stasqai tou\s mu/qous
<milestone ed="Bekker" unit="line" n="10"/>ei) me/llei kalw=s e(/cein h( poi/hsis,
e)/ti de\ e)k po/swn kai\ poi/wn e)sti\ mori/wn,
....

```
The Kassel edition simpoly does not contain the chapter and section breaks that other editors use -- not even as an alternate citation scheme. 

The 1831 Bekker page breaks regularly appear in the middle of sentences and do not define logical units of the text. Bekker citations are coded as TEI XML \<milestone/> markers -- points in, rather than chunks of, the text.

The Bekker citation units are inadequate for modern research: (1) the precise location of a citation such as 1447a10 is an approximate marker and will vary from edition to edition; (2) digital prose texts should always have editorially vetted sentence breaks with persistent citations so that they can work with sentence-based Natural Language Processing systems. 

2. The [Harvard/Tufts Digital Corpus for Graeco-Arabic Studies](https://www.graeco-arabic-studies.org/) published an [XML version of the Bekker edition the Poetics](https://www.graeco-arabic-studies.org/fileadmin/user_upload/texts.xml/Arist-Gr_004.xml). Open Greek and Latin published [an updated XML version that is compliant with the Capitains CTS library](https://github.com/gregorycrane/First1KGreek/blob/master/data/tlg0086/tlg034/tlg0086.tlg034.1st1K-grc1.xml).

Although this ditital version uses the Bekker edition, the source for this image was [an 1837 Oxford version](https://hdl.handle.net/2027/uc1.31158006467772?urlappend=%3Bseq=248%3Bownerid=13510798902191406-256) that does not contain the same page and line breaks as the 1831 edition. This Bekker edition does not contain Bekker page citations but it **does** contain the chapter and section breaks that Kassel left out of his Oxford Classical Text.

*To do*: We can align the Bekker and Kassel editions:

* We can add the Berlin Bekker citations from Kassel back to the Oxford Bekker edition, so that it has both citation schemes.

* We can add the chapter/section citations from the Oxford Bekker to the Kassel edition, so it has both citation schemes.

* We can align the readings from both editions so that readers of one can see where and how it differs from the other edition.

## IIIF Manuscripts 

We need to check for manuscripts available via IIIF.

## The 13th century Moerbeke Latin translation

This Latin translation contains evidence about an earlier stage of the text than our manuscripts preserve. It can be quickly OCRd. There are multiple editions that we can start with. 

## the 10th century Arabic translation (from Syriac)

The Harvard Tufts Greco-Arabic Corpus has published [five editions of the Arabic translation from a Syriac translation of the Poetics](https://www.graeco-arabic-studies.org/texts.html). Perseus updated one of these ([the 1953 Badawi edition](https://github.com/PerseusDL/canonical-greekLit/blob/master/data/tlg0086/tlg034/tlg0086.tlg034.digicorpus-ara1.xml)) so that it would be CTS compatible. This is not yet visible in Scaife and probably needs some fine tuning. 

The biggest task would be to align the Arabic at the section level to the Greek. For now, the Perseus edition marks chapter breaks but not sections. Alignment could take a fair amount of work and we might find that Greek sections break in the middle of Arabic sentences but it needs to be done and issues that crop up should be noted.

## Named entity tagging and linking

[ToposTexts](https://topostext.org/texts) contains several works by Aristotle but does not include a translation of the Poetics. This would be the usual starting point for pre-existing named entity classification and linking.

We can probably start with a back-of-the-book index and then link the entries to Wikidata and/or the Perseus Smith's Dictionaries.

## Treebanks

The [GLAUx (the Greek Language Automated) Corpus](https://github.com/gregorycrane/Poetics2.0/blob/main/eng/tlg0086.tlg034.butcher1911.xml) contains analyses for most (perhaps all?) of Aristotle's surviving works. The [GLAUx Treebank for the Poetics] was automatically generated.  There will surely be issues (especially given the amount of ellipsis in Aristotle) but this provides a strong first pass. The GLAUx Treebank uses the chapters and sections as citations and does not include Bekker pages. GLAUx does not (as far as I can tell) identify its source editions but this may be the Bekker edition from the Greco-Arabic corpus.

The Treebank breaks the text down into sentences. The automatic sentence segmentation has an error rate (though that can be low and there may be no errors in a given text). That said, we may also want to edit the sentence breaks -- often we can break editorial sentences into smaller logical chunks. In general, smaller sentences are preferable -- if a small sentence needs to have addition context for immediate comprehension, it is easy to combine sentences. It is much harder to split a text into sentences.

## Available English Translations

All translations should not only have the chapter/section breaks but should ideally be aligned to the sentence breaks of the treebank. We want to be able to provide mutliple translations for each treebanked sentence. Shorter sentences as a default are better -- when readers are studying the usage of a word they should start with the shortest syntactic units and then request more context if needed.

Aligning translations to treebank sentences is laborious by hand but LLMs can perform a strong -- but imperfect -- first pass. It is much faster to edit automatic alignments than to do them by hand but you have to be sure that the LLMs do not just retranslate the Greek. That is a problem with earlier LLMs (e.g., GPT 3.5) but GPT 4o is much more faithful.

1. The Perseus Digital Library includes the 1932 English translation by William Hamilton Fyfe, which is based on the 1885 (3rd) Leipzig edition by Johannes Vahlen (a full scan of which is [available at the Hathi Trust](https://hdl.handle.net/2027/uc1.aa0015641178)).

The TEI XML version of this translation is now compliant with the Canonical Text Services guidelines. The file is [available on Github](https://github.com/PerseusDL/canonical-greekLit/blob/master/data/tlg0086/tlg034/tlg0086.tlg034.perseus-eng2.xml) and in both [Perseus 4](https://www.perseus.tufts.edu/hopper/text?doc=Perseus%3Atext%3A1999.01.0056%3Asection%3D1447a) and the [Scaife Viewer](https://scaife.perseus.org/reader/urn:cts:greekLit:tlg0086.tlg034.perseus-eng2:1.1-1.5/). The Perseus 4 version will not change. Any improvements will be based upon the newer TEI XML and in newer versions of Perseus. 

The updated XML uses the chapter and section breaks as the dominant citation scheme. Bekker page citations are encoded with the \<milestone/> tag.

2. The Butcher 1911 (4th edition) Translation based on [this exemplar at the Hathi Trust](https://hdl.handle.net/2027/mdp.39015010218140).

The Butcher translation was published as a side-by-side translation next to Butcher's Greek edition. Butcher includes both Bekker citations and the traditional chapter and section citations.

We now have a [preliminary digitized version in this directory](https://github.com/gregorycrane/Poetics2.0/blob/main/eng/tlg0086.tlg034.butcher1911.xml). The basic XML is in place.  Chapters and sections are the dominant hierarchy.

This needs work.

* While all 26 chapters are tagged, not every section break has been captured, i.e., we may jump from section 9 to section 11.

* Butcher quotes Greek and that Greek needs to be added to the English --  Tesseract OCR can do English or Greek well but does not do a good job with mixed English and Greek. Where there is substantial Greek quoted (.e.g, lines of poetry), we can re-OCR the page image as Greek, cut and paste from this into the English and correct any errors that show up. Where there are isolated words quoted, it is easier to just type the Greek in. I added Greek as I saw it while doing the first pass of tagging but did not systmatically go through the translation.

* Butcher includes single quotation marks to cover multiple functions glosses of Greek words and phrases as well as quotations from a hypothetical speaker (e.g., "Some may ask, 'What is the point?'"). I have used \<gloss/> tags everywhere and this works where the English represents a translation. But we need to see where the Greek is explaining a word and where Butcher has added an explanation in the English. Quotations of a hypthetical speaker should use \<q/> tags -- quoted speech invented by the author. Exertnal quotations should be marked with \<quote/> tags -- and ideally \<cit/> and \<bibl/> tags.

3. We have (an XML version of Thomas Buckley's 1850 Bohn translation)[https://github.com/gregorycrane/english_trans-dev/tree/master/volumes/aristotle_1850] that is based on [this exemplar at the HathiTrust](https://hdl.handle.net/2027/uva.x001000005?urlappend=%3Bseq=427%3Bownerid=13510798899562602-485).

The Bohn Translation series provided literal translations that frequently offered detailed notes alerting readers to different ways the text could be understood. They are a much underappreciated achievement of 19th century scholarship. This XML needs work -- 

* the quoted Greek words and phrases are often encoded but need to be checked. They are a solid start.

* more extensive Greek quotes were not entered. Substantial Greek quotes show up as image files. These can be OCRd and the results quickly corrected and pasted into the XML but that is a laborious task.

* The text includes marginal summary notes. These need to be corrected and used in some way (e.g., as self-standing chapter summaries). This is very good data.

* The footnotes need to be matched to footnote markers.

* The primary source citations need to be converted to machine actionable, CTS-compliant references.

* The back of the book index does not contain exhaustive information about people and places.

Greg Nagy translation of chapters 1-4:

Aristotle’s Poetics, translation and commentary in progress, Chapter 1: https://classical-inquiries.chs.harvard.edu/aristotles-poetics-translation-and-commentary-in-progress-part-1/

Aristotle’s Poetics, translation and commentary in progress, Chapter 2: https://classical-inquiries.chs.harvard.edu/aristotles-poetics-translation-and-commentary-in-progress-part-2/
Aristotle’s Poetics, translation and commentary in progress, Chapter 3: https://classical-inquiries.chs.harvard.edu/aristotles-poetics-translation-and-commentary-in-progress-part-3/
Aristotle’s Poetics, translation and commentary in progress, Chapter 4: https://classical-inquiries.chs.harvard.edu/aristotles-poetics-translation-and-commentary-in-progress-part-4/

## Greek Music 

It can be very difficult to conceptualize the artistic and performance background that the Poetics assume. For an example, see [Rediscovering Ancient Greek Music (2017)](https://www.youtube.com/watch?v=4hOK7bU0S1Y).

Paging through the Poetics by chapter/section [here](https://scaife.perseus.org/reader/urn:cts:greekLit:tlg0086.tlg034.digicorpus-grc2:1.1?right=perseus-eng2) -- easier for aligning the translation.


## Arabic Grammar

For now we use the abridged Wright grammar [here](https://babel.hathitrust.org/cgi/pt?id=uc1.32106001616553&seq=9). A transcription is available [here](https://github.com/gregorycrane/wright-arabic/blob/main/elementaryarabic01thoruoft.txt)

## 1508 Editio Princeps

In [Europeana](https://www.europeana.eu/en/item/794/ark__12148_bpt6k319048q) pp. [269](https://gallica.bnf.fr/ark:/12148/bpt6k319048q/f293.item)-[286](https://gallica.bnf.fr/ark:/12148/bpt6k319048q/f310.item)

![detail](https://gallica.bnf.fr/iiif/ark:/12148/bpt6k319048q/f293/888.7304942716966,1928.9602334501897,318.46316856551346,74.57681795521489/158,37/0/native.jpg)