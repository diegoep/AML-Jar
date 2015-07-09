 ______________________________________________________________
/                                                              \
|                 AML (AgreementMakerLight)                    |
|                  Demo GUI / CLI version                      |
|                Copyright 2013-2015 LASIGE                    |
|                                                              |
|  This product includes software developed at LASIGE by the   |
|  SOMER team (http://somer.fc.ul.pt) in collaboration with    |
|  the ADVIS Lab (http://www.cs.uic.edu/Advis).                |
\______________________________________________________________/
/                                                              \
| Licensed under the Apache License, Version 2.0 (the          |
| "License"); you may not use this file except in compliance   |
| with the License. You may obtain a copy of the License at    |
| http://www.apache.org/licenses/LICENSE-2.0                   |
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
|  AML requires Java SE Runtime Environment 7. It likely will  |
|  not run on older Java versions.                             |
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
|  You can run the AML GUI by simply double-clicking the file  |
|  AgreementMakerLight.jar or through the command line, by     |
|  typing 'java -jar AgreementMakerLight.jar' without any      |
|  arguments.                                                  |
|                                                              |
|  If you want to use external ontologies as background        |
|  knowledge sources, just place them in 'store/knowledge/'    |
|  and they will be automatically listed by AML.               |
\______________________________________________________________/
/                                                              \
|                      AML CLI USAGE:                          |
|                                                              |
|  For running AML through the command line (without calling   |
|  the GUI, type:                                              |
|                                                              |
|  java -jar AgreementMakerLight.jar OPTIONS                   |
|                                                              |
|  The options are:                                            |
|                                                              |
|  -h (--help) -> print the help menu                          |
|  -s (--source) 'path_to_source_ontology'                     |
|  -t (--target) 'path_to_target_ontology'                     |
|  -i (--input)	'path_to_input_alignment'                      |
|               (mandatory in repair mode, where it will be    |
|               the alignment to repair; optional in match     |
|               mode, where it will be used as the reference   |
|               alignment, to evaluate the match result)       |
|  -o (--output) 'path_to_ouput_alignment'                     |
|               (if you want to save the resulting alignment)  |
|  -a (--auto) -> automatic match mode                         |
|   OR                                                         |
|  -m (--manual) -> manual match mode (you can configure the   |
|                   matcher in the store/config.ini file)      |
|   OR                                                         |
|  -r (--repair) -> repair alignment mode                      |
|                                                              |
|  Examples:                                                   |
|                                                              |
|  1) Use AML to automatically match two ontologies and save   |
|  output alignment: 'java -jar AgreementMakerLight.jar        |
|  -s store/anatomy/mouse.owl -t store/anatomy/human.owl       |
|  -o store/anatomy/alignment.rdf -a'                          |
|                                                              |
|  2) Use AML to manually match two ontologies and evaluate    |
|  the output alignment: 'java -jar AgreementMakerLight.jar    |
|  -s store/anatomy/mouse.owl -t store/anatomy/human.owl       |
|  -i store/anatomy/reference.rdf -m'                          |
|  Note that you can configure the options manually in the     |
|  store/config.ini file.                                      |
|                                                              |
|  3) Use AML to repair the input alignment between two        |
|  ontologies: 'java -jar AgreementMakerLight.jar              |
|  -s store/anatomy/mouse.owl -t store/anatomy/human.owl       |
|  -i store/anatomy/alignment.rdf -r                           |
|  -o store/anatomy/repaired_alignment.rdf'                    |
\______________________________________________________________/
/                                                              \
|                 AML TRANSLATION MODULE:                      |
|                                                              |
|  AML's translation module is based on the Microsoft (Bing)   |
|  translator. To use it, you MUST get your own access token   |
|  from microsoft as detailed here:                            |
|  https://msdn.microsoft.com/en-us/library/hh454950.aspx      |
|                                                              |
|  Once you have an access token, create a file called         |
|  exactly 'microsoft-translator-id' and place it in the       |
|  store/ folder. This file should contain your client_id in   |
|  the first line and your access_token in the second line. It |
|  should contain no other information.                        |
|                                                              |
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
