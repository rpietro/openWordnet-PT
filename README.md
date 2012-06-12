
# Open-WordNet-PT

## About the files

The file was generated by combining the following data:

- Princeton WordNet 3.0 was used to obtain English glosses and English
  terms for synset IDs.

- The unreleased 2010-12 version UWN and MENTA provided candidate
  terms in Portuguese, candidate glosses in Portuguese (from
  Wikipedia), and candidate terms in Spanish.

- The EuroWordNet base concept list (`5000_bc.xml`) provides the base
  concept numbers. The original file was mapped from WordNet 2.0 to
  3.0 using the mappings from
  [WN-Map](http://nlp.lsi.upc.edu/web/index.php?option=com_content&task=view&id=21&Itemid=57). When
  multiple mappings for a WordNet 2.0 synset existed, all possible
  WordNet 3.0 synsets were kept. Hence, there may be multiple entries
  with the same base concept number.
  
## Guidelines for WordNet translation

1. Read the English gloss and the English words.  
1. Come up with Portuguese words that express the same meaning as the
   English gloss and have the part-of-speech indicated by the first
   letter of the WordNet synset identifer (n: noun, v: verb, a:
   adjective, r: adverb) and write them into "PT-Words-Man".
1. Optionally: Write a Portuguese gloss into the "PT-Gloss"
   field. This may be shorter than the English gloss. If the gloss
   contains English example sentences, then only translate them if
   their translations sound natural in Portuguese and if the
   translation actually contains the Portuguese words added to the
   synset.

Example: 

    <row>
     <BC>4</BC>
     <WN-3.0-Synset>n6269</WN-3.0-Synset>
     <PT-Words-Man>vida</PT-Words-Man>
     <PT-Words-Candidates>vida</PT-Words-Candidates>
     <EN-Gloss>living things collectively; "the oceans are teeming with life"</EN-Gloss>
     <EN-Words>life</EN-Words>
     <PT-Gloss>coisas vivas, tomadas coletivamente; "os oceanos estão repletos de vida"</PT-Gloss>
     <PT-Gloss-Prop />
     <Spa-Words-Prop>vida</Spa-Words-Prop>
     <Comments />
    </row>

Additional considerations for Step 2:

- Be careful not to be misguided by English words with multiple
  meanings. You can use the Portuguese and Spanish candidates as a
  guide, but keep in mind that they were automatically generated and
  may be entirely wrong. The main criterion is whether Portuguese word
  corresponds to the English gloss.
- The PT-Words-Man field can contain multiple words, separated by
  comma, or alternatively you can also have more than one
  <PT-Words-Man> element. In either case, the words should ideally be
  sorted by relevance (the most commonly used ones first).
- If an entry has been checked and it seems that there are no relevant
  Portuguese words to express a concept then use <PT-Words-Man
  LexicalGap="true" /> If there are expressions that could be used to
  express the concept, but these expressions are not real words or
  lexicalized expressions that would appear in a dictionary, then use
  the following syntax: <PT-Words-Man Lexicalized="false">mover
  reflexivamente</PT-Words-Man>
  
It might be a good idea to have a WordNet browser open as well
when doing the annotation, so that you can check hyponyms/hypernyms
(or subclasses/parent classes): 

http://www.lexvo.org/uwn/entity/s/n2084071

Another good page to leave open is some online English-Portuguese
translation dictionary.
  
## Team

- Alexandre Rademaker
- Gerard de Melo
- Valeria de Paiva
- Rafael Haeusler

## License

<p></p>
<a rel="license"
href="http://creativecommons.org/licenses/by-sa/3.0/br/"><img
alt="Creative Commons License" style="border-width:0"
src="http://i.creativecommons.org/l/by-sa/3.0/br/88x31.png" /></a><br
/><span xmlns:dct="http://purl.org/dc/terms/"
href="http://purl.org/dc/dcmitype/Dataset" property="dct:title"
rel="dct:type">OpenWN-PT</span> by <a
xmlns:cc="http://creativecommons.org/ns#" href="http://emap.fgv.br"
property="cc:attributionName" rel="cc:attributionURL">EMAp, Getulio
Vargas Foundation</a> is licensed under a <a rel="license"
href="http://creativecommons.org/licenses/by-sa/3.0/br/">Creative
Commons Attribution-ShareAlike 3.0 Brazil License</a>.<br />Based on a
work at <a xmlns:dct="http://purl.org/dc/terms/"
href="https://github.com/arademaker/wordnet-br"
rel="dct:source">github.com</a>.

Take a look in the file LICENSE. 


## Converting to Open Universal Wordnet format

grep -v \" wn-data-por.tab > wn-data-por-1.tab
awk -F \t 'BEGIN {OFS = "\t" } NR > 1 { print $1, $2, $3 } NR == 1 { print }' wn-data-por-1.tab > wn-data-por-2.tab
sort wn-data-por-2.tab | uniq > wn-data-por-3.tab 
sed 's/_/ /g' wn-data-por-3.tab > wn-data-por-4.tab

## DTD

Para usar o DTD executar no prompt:

$ xmllint --noout --dtdvalid wordnet.dtd uwn-pt-sorted-aa.xml

Apos resolver problemas problemas atuais com esta versao do DTD,
modificar o DTD conforme cada item abaixo e corrigir os XML a partir
dos novos erros de validacao que irao surgir.

- Remover as variacoes de PT-Words-Cand e PT-Word-Cand 
- Remover variacoes de Spa-Words-Sug e SPA-Words-Sug 
- Remover variacoes nos atributos do PT-Words-Man 

