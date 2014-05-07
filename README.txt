 ______________________________________________________________
/                                                              \
|                 AML (AgreementMakerLight)                    |
|              Demo GUI version & CLI version                  |
|                Copyright 2013-2014 LASIGE                    |
|                                                              |
|  This product includes software developed at LASIGE by the   |
|  SOMER team (http://somer.fc.ul.pt) in collaboration with    |
|  the ADVIS Lab (http://www.cs.uic.edu/Advis).                |
\______________________________________________________________/
/                                                              \
|                       DISCLAIMER:                            |
|                                                              |
|  This software is provided on an "AS IS" BASIS, WITHOUT      |
|  WARRANTIES OR CONDITIONS OF ANY KIND, either express or     |
|  implied, including, without limitation, any warranties or   |
|  conditions of TITLE, NON-INFRINGEMENT, MERCHANTABILITY,     |
|  or FITNESS FOR A PARTICULAR PURPOSE.                        |
\______________________________________________________________/
/                                                              \
|                  SYSTEM REQUIREMENTS:                        |
|                                                              |
|  AML requires Java SE Runtime Environment 7. It will not     |
|  run on older Java versions.                                 |
|                                                              |
|  Memory usage depends on the size of the ontologies you are  |
|  working with. We recommend a minimum of 2 GB RAM for small  |
|  ontologies (<1,000 classes), 4 GB RAM for medium-sized      |
|  ontologies (<10,000 classes), 8 GB RAM for large ontologies |
|  (<100,000 classes), and 16 GB RAM for larger ontologies.    |
|  We also recommend restarting AML when changing from one     |
|  pair of ontologies to another, to avoid memory build up.    |
|                                                              |
|  Please keep in mind that opening large ontologies may take  |
|  several minutes. Likewise, matching large ontologies may    |
|  also take several minutes, particularly when WordNet or     |
|  large ontologies are used as background knowledge sources   |
|  and/or the repair option is selected.                       |
|                                                              |
|  Please do not move the AgreementMakerLight.jar file from    |
|  the AML folder, as it will not work without this folder     |
|  structure.                                                  |
\______________________________________________________________/
/                                                              \
|                      AML GUI USAGE:                          |
|                                                              |
|  You can run the AML GUI by simply by executing the file     |
|  AgreementMakerLight.jar                                     |
|                                                              |
|  You can use any ontology as a background knowledge source   |
|  when using the "AML Matcher" algorithm. Just place the      |
|  ontology file (in OWL or RDFS) in "./store/knowledge/" and  |
|  it will be automatically listed by AML.                     |
\______________________________________________________________/
/                                                              \
|                      AML CLI USAGE:                          |
|                                                              |
|  For the AML CLI version, you must run the file              |
|  AgreementMakerLightCLI.jar with java from the Command Line  |
|  by using the command:                                       |
|                                                              |
|  java -jar AgreementMakerLightCLI.jar OPTIONS                |
|                                                              |
|  The options are:                                            |
|                                                              |
|  -s path_to_source_ontology                                  |
|  -t path_to_target_ontology                                  |
|  [-i input_alignment_path]                                   |
|  [-o ouput_alignment_path]                                   |
|  [-m] -> match ontologies                                    |
|  [-r] -> repair alignment (with -m repairs the produced      |
|          alignment, without it repairs the input alignment)  |
|  [-b] -> use background knowledge (only with -m)             |
|  [-u] -> exclude UMLS (only with -m)                         |
|                                                              |
|  Examples:                                                   |
|                                                              |
|  1) Use AML to match two ontologies and save output          |
|  alignment: java -jar AgreementMakerLightCLI.jar             |
|  -s store/anatomy/mouse.owl -t store/anatomy/human.owl       |
|  -o store/anatomy/alignment.rdf -m [-r -b -u]                |
|                                                              |
|  2) Use AML to match two ontologies and evaluate the output  |
|  alignment: java -jar AgreementMakerLightCLI.jar             |
|  -s store/anatomy/mouse.owl -t store/anatomy/human.owl       |
|  -i store/anatomy/reference.rdf -m [-r -b -u]                |
|                                                              |
|  3) Use AML to repair the input alignment between two        |
|  ontologies: java -jar AgreementMakerLightCLI.jar            |
|  -s store/anatomy/mouse.owl -t store/anatomy/human.owl       |
|  -i store/anatomy/alignment.rdf -r                           |
|  -o store/anatomy/repaired_alignment.rdf                     |
\______________________________________________________________/
/                                                              \
|                       ABOUT AML:                             |
|                                                              |
|  AML is a lightweight automated ontology matching system     |
|  specialized on biomedical ontologies but applicable to      |
|  other domains. It is described in:                          |
|  - D. Faria, C. Pesquita, E. Santos, I. Cruz, and F. Couto,  |
|  AgreementMakerLight Results for OAEI 2013, ISWC Workshop    |
|  on Ontology Matching, 2013.                                 |
|  - D. Faria, C. Pesquita, E. Santos, M. Palmonari, I. Cruz,  |
|  and F. Couto, The AgreementMakerLight ontology matching     |
|  system, ODBASE 2013.                                        |
|                                                              |
|  The AML GUI uses Gephi, an open source graph visualization  |
|  and manipulation software. Like AML, Gephi is lightweight   |
|  and efficient. However, it has its faults and limitations,  |
|  which have an impact on the AML GUI. Namely, the rendered   |
|  graph will only ajust to the size of the "Mapping View"     |
|  panel upon being clicked, an inconvenience for which we     |
|  apologize.                                                  |
\______________________________________________________________/
