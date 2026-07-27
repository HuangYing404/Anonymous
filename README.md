
# data prepare
 ```bash
    cat data* > data.tar
    tar xvf data.tar
 ```

# enviroment set up
 ```bashFPGIA
    conda create -n FPGIA python==3.9
    conda activate FPGIA
    pip install -r requirements
 ```

## MIMIC-III ours
 ```bash
    python main.py --model mlp --batch-size 32  --w1 1e-5 --w2 1e-5 --presence-obj
 ```

## eICU baseline
 ```bash
    python main_eicu.py --model mlp --batch-size 32  --w1 1e-5 --scale 5
 ```
## MIMIC-III baseline
 ```bash
    python main_mimic.py --model mlp --batch-size 32  --w1 1e-5 --w2 1e-5 --scale 5
 ```
## config
```bash
    --model :the model you try to attack (mlp, transformer)
    --presence-obj :wheather to use presence Loss
    --w1 （--w2） :the coefficient of graph loss
    --tag   :weather to use TAG Loss
 ```


## Dataset Availability

This project uses two publicly available electronic health record datasets:

- MIMIC-III Clinical Database:
  https://physionet.org/content/mimiciii/1.4/

- eICU Collaborative Research Database:
  https://physionet.org/content/eicu-crd/2.0/

Due to data access restrictions and privacy considerations, the original datasets are not included in this repository. Researchers interested in reproducing the experiments should request access from the official providers and comply with the corresponding data use agreements.
