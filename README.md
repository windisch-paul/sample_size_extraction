# Introduction
This repository contains the data and code associated with the manuscript [Extracting the Sample Size From Randomized Controlled Trials in Explainable Fashion Using Natural Language Processing](https://academic.oup.com/jamiaopen/article/7/4/ooae116/7842832) published in JAMIA Open.
The config file can be used to train a model using the spacy/prodigy packages. 

# Data
Each trial in the tranining and test set is a row in the csv file. 150 annotated examples were randomly assigned to an unseen test set. The remaining 846 examples were used to train and validate a named entity recognition model. However, the sets could be merged to allow for different splits.
The columns of the dataset are described below:

- **doi**: Digital Object Identifier of the publication
- **date**: Publication data according to PubMed
- **journal**: Journal the publication was published in according to PubMed
- **title**: Title of the publication according to PubMed
- **text**: The text that was displayed to the annotator (i.e., the abstract)
- **tokens**: The list of tokens that the "text" column was parsed into. Each token has a text, a start, an end, an id, and a boolean ws property that indicates if a token is follows by whitespace or not.
- **spans**: The spans created by the annotator. Each span has a start, and end, a text, a source (if the span had been suggested by a model in the loop), an input_hash, a token_start, a token_end, and a label.
- **answer**: Contains "accept" if an annotator annotated the publication.
- **_input_hash. _taskhash, is_binary,  _timestamp, _annotator_id, _session_id**: Additional columns automatically created by the annotation tool during the annotation process. For detailed documentation see the [prodigy docs](https://prodi.gy/docs/api-components).
- **Number_randomized**: The ground truth (i.e. how many patients were randomized)

The dataset has also been uploaded to [Dryad](https://doi.org/10.5061/dryad.g1jwstr0b).
