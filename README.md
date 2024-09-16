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

2. The Perseus Digital Library includes the 1932 English translation by William Hamilton Fyfe, which is based on the 1885 (3rd) Leipzig edition by Johannes Vahlen (a full scan of which is [available at the Hathi Trust](https://hdl.handle.net/2027/uc1.aa0015641178)).

The TEI XML version of this translation is now compliant with the Canonical Text Services guidelines. The file is [available on Github](https://github.com/PerseusDL/canonical-greekLit/blob/master/data/tlg0086/tlg034/tlg0086.tlg034.perseus-eng2.xml) and in both [Perseus 4](https://www.perseus.tufts.edu/hopper/text?doc=Perseus%3Atext%3A1999.01.0056%3Asection%3D1447a) and the [Scaife Viewer](https://scaife.perseus.org/reader/urn:cts:greekLit:tlg0086.tlg034.perseus-eng2:1.1-1.5/). The Perseus 4 version will not change. Any improvements will be based upon the newer TEI XML and in newer versions of Perseus. 
