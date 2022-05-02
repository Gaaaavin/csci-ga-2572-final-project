# csci-ga-2572-final-project
Final competition code repository for CSCI-GA 2572 Deep Learning spring 2022.

All codes in this repository were run on Greene.

## Pretraining

## Fine Tuning
We fine tuned the pretrained weights above by the folloing steps.
1. Change the path in line 59 in `fine_tune/barlowtwins.py` to the path of weight generated in the pretraining part
2. Change the overlay path in `fine_tune/run.sh` to your corresponding path for environment and labeled dataset. Then, change line 20 in `fine_tune/run.sh` into `python barlowtwins.py -n 20 --lr 0.0001` to train for 20 epochs with a learning rate of 0.0001. Use `sbatch run.sh` to start traning. This will give a mAP of approximately 0.20
3. Train another 20 epoch with learning rate = 5e-5, by changing line 20 in `fine_tun/run.sh` into `python barlowtwins_continue -n 20 --lr 0.00005`. This will give a mAP of approximately 0.28.