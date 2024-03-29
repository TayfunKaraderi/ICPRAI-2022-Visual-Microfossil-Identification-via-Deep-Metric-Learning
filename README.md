# ICPRAI-2022-Visual-Microfossil-Identification-via-Deep-Metric-Learning
Contains source code for https://arxiv.org/abs/2112.09490.
Forams dataset is avaliable at http://endlessforams.org.

# Guide
1. Download forams dataset from http://endlessforams.org, cut text and borders out using processing.py. Then, place those files into datasets folder in train and test folders.
2. To train with full dataset, run command such as:
```
  python train.py --out_path=output/ --folds_file=datasets/OpenSetForams/splits/all_35_classes.json --img_rows=224 --img_cols=224 --model=TripletResnetSoftmax --learning_rate=0.001 --embedding_size=128 --logs_freq=20 --num_epochs=30 --eval_freq=2 --batch_size=16 --loss_function=OnlineReciprocalSoftmaxLoss
```
4. To train with openset data, alter the.json file.
5. To visualize embeddings with tsne, run command such as:
```
  python visualise_embeddings.py --model_path=output/full_data_rotation_augmented/best_model_state.pkl --dataset=Forams --batch_size=1 --embedding_size=128 --current_fold=0 --folds_file=datasets/OpenSetCows2020/splits/all_35_classes.json --save_path=output/fold_0
```
6. To obtain test set performance, run command such as:
```
python test_save.py --model_path=output/augmentations/ALL_AUG_ep10/best_model_state.pkl --dataset=Forams --batch_size=16 --embedding_size=128 --current_fold=0 --folds_file=datasets/OpenSetCows2020/splits/all_35_classes.json --save_path=output/full_data_rotation_augmented
```

# Cite
T Karaderi, T Burghardt, AY Hsiang, J Ramaer, DN Schmidt. Visual Microfossil Identification via Deep Metric Learning. 3rd International Conference on Pattern Recognition and Artificial Intelligence (ICPRAI), Lecture Notes in Computer Science (LNCS), Vol 13363, pp. 34-46, June 2022.

```
@inproceedings{mstennett2022visual,
      title={Visual Microfossil Identification via Deep Metric Learning}, 
      author={Karaderi, T and Burghardt, T and Hsiang, AY and Ramaer, J and Schmid, DN},
      year={2022},
      month=June,
      month_numeric = {6},
      booktitle={3rd International Conference on Pattern Recognition and Artificial Intelligence (ICPRAI), Lecture Notes in Computer Science (LNCS)},
      Volume = {13363},
      page = {34-46}
}
```
