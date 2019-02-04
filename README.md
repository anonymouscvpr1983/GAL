# Towards Optimal Structured CNN Pruning via Generative Adversarial Learning(GAL)

The PyTorch code is for rebuttal on GAL.



## Running Code

In this code, you can run our model on CIFAR10 dataset. The code has been tested by Python 3.6, [Pytorch 0.4.1](https://pytorch.org/) and CUDA 9.0 on Ubuntu 16.04.



### Run examples

The scripts of training and fine-tuning are provided  in the `run.sh`, please kindly uncomment the appropriate line in `run.sh` to execute the training and fine-tuning.

```shell
sh run.sh
```



**For training**, change the `teacher_dir` to the place where the pretrained model is located. 

```shell
# run.sh
python main.py --teacher_dir [pre-trained model dir]
```

The pruned model will be named `pruned.pt`



**For fine-tuning**, change the `refine` to the place where the pruned model is allowed to be fine-tuned. 

```shell
# run.sh
python finetune.py --refine [pruned model dir] 
```

You can set `--pruned` to reuse the `pruned.pt`. If you want to initiate weights randomly, just set  `--random`.



## Models

We also provide our pre-trained, pruned and fine-tuned models below, download and set `--test_only` to test the models. Enjoy your training and testing!



### Resnet56

| Model                                                        | FLOPs.  | #Param. | Top-1 Err. |
| ------------------------------------------------------------ | ------- | ------- | ---------- |
| [Baseline](https://drive.google.com/open?id=1XHNxyFklGjvzNpTjzlkjpKc61-LLjt5T) | 125.49M | 0.85M   | 6.74%      |
| [GAL-0.6](https://drive.google.com/open?id=1Fq4miBYqCLUNCoxJp9VoWaBAbR1rxVMm) | 78.30M  | 0.75M   | 7.02%      |
| [GAL-0.8](https://drive.google.com/open?id=1gQ5vt5KoEPFLF-u2lGcT2bk4PoLcbx_8) | 49.99M  | 0.29M   | 9.64%      |
| [FT-GAL-0.6](https://drive.google.com/open?id=1fhYezcYTCbRhN8e3r_0wY_6CZOud736R) | 78.30M  | 0.75M   | 6.62%      |
| [FT-GAL-0.8](https://drive.google.com/open?id=1-1-9z6zAfMogAx4HjQ0Gxt67Z9RpkQA4) | 49.99M  | 0.29M   | 8.42%      |




