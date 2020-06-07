# Task Design and Crowd Sentiment in Biocollections Information Extraction

## Dataset and Subset
The utilized dataset is found at: https://github.com/idigbio-aocr/label-data
Only 100 of the images were utilized: 34 Entomology, 33 Herbs, and 33 Lichens.
In the file subset.txt, it is found this list of images, which was randomly generated.

## Gold data
In files Gold_Transcription.ods and Gold_Selection.ods are found the experts' transcription to the 100 images' field values.
The Gold_Transcription.ods values were also used for the evaluation of the Cropping's results.

## Fields
Twelve fields were utilized in the experiments. All of them were processed as verbatim values. Therefore, the terms listed below were considered verbatim, despite the lack of utilization of the "verbatim" word in the experiments interface. The following information was taken from the Quick Reference Guide of the Darwin Core terms (http://tdwg.github.io/dwc/terms/):
- Event date (eventDate): The verbatim original representation of the date and time information for an Event. Examples: "spring 1910", "Marzo 2002", "1999-03-XX", "17IV1934"
- Scientific name (scientificName): The full scientific name, with authorship and date information if known. When forming part of an Identification, this should be the name in lowest level taxonomic rank that can be determined. This term should not contain identification qualifications, which should instead be supplied in the identificationQualifier term. Examples: "Coleoptera" (order), "Vespertilionidae" (family), "Manis" (genus), "Ctenomys sociabilis" (genus + specificEpithet), "Ambystoma tigrinum diaboli" (genus + specificEpithet + infraspecificEpithet), "Roptrocerus typographi (Györfi, 1952)" (genus + specificEpithet + scientificNameAuthorship), "Quercus agrifolia var. oxyadenia (Torr.) J.T. Howell" (genus + specificEpithet + taxonRank + infraspecificEpithet + scientificNameAuthorship).
- Identified by (identifiedBy): A list (concatenated and separated) of names of people, groups, or organizations who assigned the Taxon to the subject. The recommended best practice is to separate the values with a vertical bar (' | '). Examples: "James L. Patton", "Theodore Pappenfuss | Robert Macey".
- Country (country): The name of the country or major administrative unit in which the Location occurs. Recommended best practice is to use a controlled vocabulary such as the Getty Thesaurus of Geographic Names. Examples: "Denmark", "Colombia", "España".
- State (stateProvince): The name of the country or major administrative unit in which the Location occurs. Recommended best practice is to use a controlled vocabulary such as the Getty Thesaurus of Geographic Names. Examples: "Denmark", "Colombia", "España".
- County (county): The full, unabbreviated name of the next smaller administrative region than stateProvince (county, shire, department, etc.) in which the Location occurs. Examples: "Missoula", "Los Lagos", "Mataró".
- Latitude (verbatimLatitude): The verbatim original latitude of the Location. The coordinate ellipsoid, geodeticDatum, or full Spatial Reference System (SRS) for these coordinates should be stored in verbatimSRS and the coordinate system should be stored in verbatimCoordinateSystem. Example: "41 05 54.03S".
- Longitude (verbatimLongitude): The verbatim original longitude of the Location. The coordinate ellipsoid, geodeticDatum, or full Spatial Reference System (SRS) for these coordinates should be stored in verbatimSRS and the coordinate system should be stored in verbatimCoordinateSystem. Example: "121d 10' 34" W".
- Elevation (verbatimElevation): The original description of the elevation (altitude, usually above sea level) of the Location. Example: "100-200 m".
- Locality (verbatimLocality): The original textual description of the place. Example: "25 km NNE Bariloche por R. Nac. 237".
- Habitat (habitat): A category or description of the habitat in which the Event occurred. Examples: "oak savanna", "pre-cordilleran steppe".
- Recorded by (recordedBy): A list (concatenated and separated) of names of people, groups, or organizations responsible for recording the original Occurrence. The primary collector or observer, especially one who applies a personal identifier (recordNumber), should be listed first. The recommended best practice is to separate the values with a vertical bar (' | '). The primary collector or observer, especially one who applies a personal identifier (recordNumber), should be listed first. Examples: "José E. Crespo", "Oliver P. Pearson | Anita K. Pearson" where the value in recordNumber "OPP 7101" corresponds to the number for the specimen in the field catalog (collector number) of Oliver P. Pearson.

## Similarity script
In order to compute the similarity between two strings it is utilized the normalized Damerau-Levenshtein distance algorithm. The Damerau-Levenshtein implementation used is the developed by Geoffrey Fairchild and available at https://github.com/gfairchild/pyxDamerauLevenshtein.
The script used to compute the similarity of lists of values is [similarity.py](https://github.com/acislab/HuMaIN_Crowdsourcing_Complexity/blob/master/similarity.py).

All the material in this repository is under the Apache 2.0 License: [read License](https://github.com/acislab/HuMaIN_Crowdsourcing_Complexity/blob/master/LICENSE)

## Acknowledgement
HuMaIN is funded by a grant from the National Science Foundation's ACI Division of Advanced Cyberinfrastructure (Award Number: 1535086).
Any opinions, findings, and conclusions or recommendations expressed in this material are those of the author(s) and
do not necessarily reflect the views of the National Science Foundation.
