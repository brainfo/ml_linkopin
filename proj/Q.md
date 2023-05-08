# Questions regarding two options of the project
## Option 1: "Predict" gene transcription from TF expression and prom/enh region accessibity
input features:
- TF expression (CPM)
- region accessibility (AUC)
output features:
- target gene transcription (CPM)
observations:  
nuclei (one barcode from 10X multiomics data)  
1. The known e-regulon from SCENIC+ is learnt from the data, which has information overlap with the data which this model optimation needs. For the same reason, the input features might not be independent. Though the previous examination revealed that most of the TF and region accessibility in the PBMC data were not linearly related, the question remains if I should only keep the non-linear pairs of input.
2. From input to output, there should be reaction formula as math model, should I formulate that model and fit the parameters there or should I select any machine learning methdod based on performance measurement.
3. For the target gene transcription, should I use only the transcription parameters of unspliced transcripts, since the TF regulon in theory should only directly affect the transcription but not the transport, (binding and tagging so that it cannot be sequenced by 10X) and degradation.
4. For simplication reason, should I first try on one TF-one region-one gene, or start with a minimum network with TFs-one region-genes. If so, should I formulate the reaction system modeling, seems there might be no unique solution for such a model.
## Option 2: From TF expression to PAPPA transcription params in syncytialtrophoblast
The problem is I don't have accessibility here. 
1. Is it legit the assumption that the accessibility is constant in different nuclei? 
2. Or should we say it's some hidden variable with some given distribution? 
3. Or should we do not give any assumptions for it, just as an unknown variable. Then in this case, seems if I have a interpretable prior model, the params for TF expression and this hidden variable is deducible.