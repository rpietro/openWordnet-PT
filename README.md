
# openWordnet-PT

## About the RDF conversion

- Based on http://www.w3.org/TR/wordnet-rdf/ and
  http://semanticweb.cs.vu.nl/lod/wn30/ with some modifications. More
  files from the Princeton distribution were considered and not only
  the database files. More properties and classes are included.
  
- Lisp code used to create the RDF files will be made available soon.

- The wordnet-br.rdf is not a complete wordnet. All relations are in
  the wordnet-en.rdf (the original Princeton WordNet 3.0).


## Team

- Alexandre Rademaker
- Valeria de Paiva

## Contributors

- Gerard de Melo
- Francis Bond

## Related projects

- http://www.casta-net.jp/~kuribayashi/multi/ See openMLWN directory
  for information and the OpenWordnet-PT version in the format used in
  this site.
- http://nlp.lsi.upc.edu/freeling/ See freeling directory for
  information and the OpenWordnet-PT version in the format used by
  FreeLing.
- http://ontopt.dei.uc.pt Another WordNet based ontology in
  Portuguese. It has incorporated OpenWordnet-PT.

## How to cite?

Vide http://arademaker.github.io/bibliography/coling2012.html

## How to contribute?

Please use the GitHub issue tracker
(https://github.com/arademaker/wordnet-br/issues) or clone this repo
and make a pull request. 

## How the project started?

The initial file was generated by combining the following data:

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


## License

<p><a rel="license" href="http://creativecommons.org/licenses/by-sa/3.0/deed.en_US"><img alt="Creative Commons License" style="border-width:0" src="http://i.creativecommons.org/l/by-sa/3.0/88x31.png" /></a><br /><span xmlns:dct="http://purl.org/dc/terms/" href="http://purl.org/dc/dcmitype/Dataset" property="dct:title" rel="dct:type">OpenWN-PT</span> by <a xmlns:cc="http://creativecommons.org/ns#" href="http://arademaker.github.com" property="cc:attributionName" rel="cc:attributionURL">Alexandre Rademaker</a> is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-sa/3.0/deed.en_US">Creative Commons Attribution-ShareAlike 3.0 Unported License</a>. Based on a work at <a xmlns:dct="http://purl.org/dc/terms/" href="http://github.com/arademaker/wordnet-br" rel="dct:source">http://github.com/arademaker/openWordnet-PT</a>.</p>

Also look in the file LICENSE. Note that the wordnet-en.rdf is based
on Princeton WordNet 3.0 being only its conversion for RDF format. The
Princeton WordNet 3.0 is distributed under the license
http://wordnet.princeton.edu/wordnet/license/. 

