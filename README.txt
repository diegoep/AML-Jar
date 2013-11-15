 ______________________________________________________________
/                                                              \
|                 AML (AgreementMakerLight)                    |
|             OAEI 2013 executable jar version                 |
|                Copyright 2013-2013 LASIGE                    |
|                                                              |
|  This product includes software developed at LASIGE by the   |
|  SOMER team (http://somer.fc.ul.pt) in collaboration with    |
|        the ADVIS Lab (http://www.cs.uic.edu/Advis).          |
\______________________________________________________________/
/                                                              \
|    This software is provided on an "AS IS" BASIS, WITHOUT    |
|   WARRANTIES OR CONDITIONS OF ANY KIND, either express or    |
|    implied, including, without limitation, any warranties    |
|  or conditions of TITLE, NON-INFRINGEMENT, MERCHANTABILITY,  |
|            or FITNESS FOR A PARTICULAR PURPOSE.              |
\______________________________________________________________/
/                                                              \
|  AML is a lightweight automated ontology matching framework  |
| specialized on biomedical ontologies but applicable to other |
|   domains. You can find a detailed description of AML at:    |
|    http://www.dit.unitn.it/~p2p/OM-2013/oaei13_paper1.pdf    |
\______________________________________________________________/

#Usage:
java -jar AgreementMakerLight.jar OPTIONS

#Options:
-s path_to_source_ontology -> required for AML to run
-t path_to_target_ontology -> required for AML to run
[-o ouput_path] -> required for AML to save the produced alignment
[-r reference_path] -> required for AML to evaluate the produced alignment and for interactive selection (see below)
[-bk] -> optional, allows AML to use all available background knowledge
[-bu] -> optional, allows AML to use all background knowledge except UMLS
[-r] -> optional, makes AML repair final alignment
[-i] -> optional, makes AML employ a simulated interactive selection algorithm (requires a reference alignment selected above)

#Examples:
> AML simple configuration:
java -jar AgreementMakerLight.jar -s store/anatomy/mouse.owl -t store/anatomy/human.owl
-o alignment.rdf -r store/anatomy/reference.rdf

> AML with background knowledge and repair
java -jar AgreementMakerLight.jar -s store/anatomy/mouse.owl -t store/anatomy/human.owl
-o alignment.rdf -r store/anatomy/reference.rdf -bk -r
