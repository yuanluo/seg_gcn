# Segment Graph Convolutional and Recurrent Neural Network (Seg-GCRN) for relation classification
### Requirements
Code is written in Python (2.7) and requires Tensor Flow.

### 1. To get embeddings we used
https://northwestern.box.com/s/eprxyxmee37p3d6khqbpn125tyttq4u6

Include embeddings trained on MIMIC3 corpus, dimensions from 100 to 600.

### 2. To get concept and relation information (e.g., location in the sentence, concept type...) we used
The original data have been removed from the repository due to the change of policy from the data provider. We are trying to update the result along with reduced concept and relation information soon.

### 3. Generate the embedding matrix and syntactic dependencies based on information from 1 and 2 above
Run par1_sp.py, par4_sp.py for training and testing datasets of TeP relation category
Run par2_sp.py, par5_sp.py for training and testing datasets of TrP relation category
Run par3_sp.py, par6_sp.py for training and testing datasets of PP relation category

### 4. Run the Seg-GCRN for different datasets based on information from 3 above
Run train_tep_gcn.py for TeP relation category
Run train_tp_gcn.py for TrP relation category
Run train_pp_gcn.py for PP relation category

### Sidenote: Using the GPU
By default, tensorflow is multiple-GPU friendly and it automatically distributes the loads. However, you can also manually lock your computation to one or more of the GPUs. (https://www.tensorflow.org/programmers_guide/using_gpu)

### The Performance of Seg-GCRN
Due to historical reasons, part of the i2b2/VA 2010 challenge dataset is not available in the current release from the i2b2 website. At the request of multiple colleagues, we have also tested our systems on the current partial release of the i2b2/VA 2010 relation challenge dataset as follows.

| System   | treatment–problem  |       |       |  | test–problem  |      |       |  | problem–problem  |       |       |
|----------|--------------------|-------|-------|--|---------------|------|-------|--|------------------|-------|-------|
|          | P                  | R     | F     |  | P             | R    | F     |  | P                | R     | F     |
| Seg-GCRN | 0.685              | 0.665 | 0.675 |  | 0.813         | 0.79 | 0.801 |  | 0.705            | 0.739 | 0.722 |
