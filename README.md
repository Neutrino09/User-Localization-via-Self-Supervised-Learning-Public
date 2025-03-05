# User-Localization-via-Self-Supervised-Learning-Public
This repository contains the code and documentation for a user localization project based on channel state information (CSI) obtained from a massive MIMO channel sounder. The objective is to accurately predict the three-dimensional position of a user using a combination of self-supervised and supervised learning methods.

Overview User localization is an essential feature for wireless communication systems, enabling applications such as navigation, smart factories and cities, surveillance, security, and IoT. Accurate position information also supports improved radio resource management, beamforming, and channel estimation. While machine learning methods have achieved high localization accuracy, they typically require extensive labeled data. This project leverages self-supervised learning to reduce the reliance on labeled data by learning useful representations from abundant unlabelled data.

![image](https://github.com/user-attachments/assets/0edad155-9922-43b5-bc3e-adbdb30e977d)


● The left figure shows the UE positions (latitude/longitude) recorded using a differential GPS. ● The right figure shows the positions (on the XY-plane) transformed to a local coordinate system to have dimensions in meters, with the base station at (0,0).

Dataset Description The dataset was acquired using a massive MIMO channel sounder with the following details:

Antenna Array: 8x8 horizontally polarized patch antennas (only 56 out of 64 antennas were used due to malfunctions). Channel Measurements: CSI Real Part (H_Re): Shape [num_samples, 56, 924, 5] CSI Imaginary Part (H_Im): Shape [num_samples, 56, 924, 5] SNR: Shape [num_samples, 56, 5] Ground Truth Positions (Pos): Shape [num_samples, 3] representing [x, y, z] coordinates in a local Cartesian coordinate system. Total labelled samples: 4096. Spatial Coverage: The transformed area spans approximately 646 × 943 × 41 meters.

Data: labelled_data.zip – Contains CSI (real & imaginary parts), SNR, and ground truth positions for 4096 samples. (https://drive.google.com/file/d/1atPChIUtYv8oiYwPFBZoJ8Ha0pCLFLxF/view) unlabelled_data.zip – Contains CSI and SNR (without position labels) for 36192 samples. (https://drive.google.com/file/d/18iEpL4Q6ybtPPwP2rYcZ3ocdfmMbyHp2/view) test_data.zip – Contains CSI and SNR (without position labels) for 883 samples; note that part of the map is omitted from the labelled dataset. (https://drive.google.com/file/d/1gYQ_ZbX36cOiiwpdqQ94ON7Mt8DlqvEr/view) Note: A subset of the spatial region (two streets) is omitted from the labelled data but included in the test dataset. Additionally, some CSI estimates are recorded as zeros due to very low SNR during channel estimation.

Evaluation Metric The final score for the model is determined by the Mean Absolute Error (MAE) computed over the x, y, and z axes, averaged across all test samples.

References Maximilian Arnold, Jakob Hoydis, and Stephan ten Brink, “Novel Massive MIMO Channel Sounding Data applied to Deep Learning-based Indoor Positioning”, Proc. SCC, 2019.

About
No description, website, or topics provided.
Resources
 Readme
 Activity
Stars
 0 stars
Watchers
 1 watching
Forks
 0 forks
Report repository
Releases
No releases published
Packages
No packages published
Languages
Jupyter Notebook
100.0%
Footer
© 2025 GitHub, Inc.
Footer navigation
Terms
Privacy
Security
