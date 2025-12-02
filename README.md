# CV-FInal-Repo


README File for Group 3

To run our models, ensure the following dependencies are installed
- torch 
- torchvision 
- torchaudio
- transformers 
- datasets
- timm
- matplotlib 
- pillow 
- tqdm
- accelerate
- pytorch-lightning
- os
- json


or 

use following command

```{bash}
pip install -r requirements.txt
```


For running the flickr8k model, simply run the flickrfinal.ipynb.  No additional work is needed.  This will save
the final model, sample captions from each epoch, and will print results and their corresponding images.


## To run fully on COCO training dataset, you will need to COCO dataset downloaded

you can download dataset from official site

COCO[!href link]

Once you can downloaded, you will need to update `GLOBAL_PATH`s & `GLOBAL VARIABLE` in `COCO_pretraining_py.py` to accurate path to the dataset.


To submit job request on BigRed200:
Follow these steps:

1) Clone this repo:

```
git clone https://github.com/Jags96/CV-FInal-Repo.git
```

2) Use vim editor for editing the GLOBAL PATH and VARIABLEs both on COCO_pretraining_py.py and `blip2.slurm` paths as well


3) Once, you set accurate Global variable, run following command on your bigred ssh

```
sbatch blip2.slurm
```

This command will submit the Job request batch, which will run once resources are available.

> To use model for evaluation, you can use `blip2_eval_py.py` instead of `COCO_pretraining_py.py` and follow above steps.


### For Results (from our report)

- `./results/GROUND_TRUTH_JSON.json` contains ground truth of `val2017` segment of COCO in the same order as official val2017 annotations json.
- `./results/new_format_json.json` contains generated captions on `val2017` BY MODEL_TRAINED on COCO (in same order as GT(above))
- `./results/output_json_model_flickr.json` contains both GT and generated outputs of MODEL TRAINED on COCO.


