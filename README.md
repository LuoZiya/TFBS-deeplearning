# Deeping learning model for predicting tissue-specific TFBS based on ATAC-seq

Purpose:
Deep learning methods could be applied to predict TFBS in different tissues by combining ATAC-seq  with tsCUT&Tag.In order to solve the problem that it is difficult for tissues to obtain high-quality protoplasts with high transformation efficiency.

Usage:
1. The models：
① The model training selects the overlapping binding sites of transcription factors and the open chromatin region of ATAC-seq , upstream and downstream 100bp of the peak summit is positive data, and the open chromatin region of ATAC-seq without TFBS is negative data set. 
② To predict each TF, it need to replace the corresponding training data (./data/test.csv adn ./data/train.csv).

2. The predicted inputs
The predicted inputs is the open chromatin region sequence of ATAC-seq in csv file (see example ./data/predict-goodATAC.CSV). The prediction model reads a window size of 200bp with a displacement of 100.

3. The outputs
The outputs file (see example ./result/goodatacout.csv) contain two columns, the second column is the TFBS presence or absence, 1 is bound, 0 is not bound. If TFBS is bound, the first column is the position where TFBS is bound (site=start+the first column number*100). Finally, get TFBS position and its' regulated target gene.
