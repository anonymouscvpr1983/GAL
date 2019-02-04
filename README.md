# Towards Optimal Structured CNN Pruning via Generative Adversarial Learning(GAL)

The PyTorch code for GAL.



## Running Code

In this code, you can run our model on CIFAR10 dataset. The code has been tested with Python 3.6, Pytorch 0.4.0 and CUDA 9.0 on Ubuntu 16.04.



### Run examples

Training and fine-tuning scripts are provided in the `run.sh`. please uncomment the appropriate line in `run.sh` that you want to execute.

```shell
sh run.sh
```



**For training**, change the `teacher_dir ` argument to the place where the pretrained model located. 

```shell
# run.sh
python main.py --teacher_dir [pre-trained model dir]
```

The pruned model will be named `pruned.pt`



**For fine-tuning**, change the `refine` argument to the place where the pruned model to be fine tuned. 

```shell
# run.sh
python main.py --refine [pruned model dir] 
```

You can set `--pruned` to reuse the `pruned.pt`.

If you want to initiate weights randomly, please set  `--random`.



## Models

we provied our pretrained, pruned and fine-tuned models below, download and set `--test_only` to test the models.

### Resnet56

| Model                                                        | #Param. | #FLOPs | Top-1 Err. |
| ------------------------------------------------------------ | ------- | ------ | ---------- |
| [Baseline](https://drive.google.com/open?id=1XHNxyFklGjvzNpTjzlkjpKc61-LLjt5T) | 125.49M | 0.85M  | 6.74%      |
| [GAL-0.6](https://drive.google.com/open?id=1Fq4miBYqCLUNCoxJp9VoWaBAbR1rxVMm) | 78.30M  | 0.75M  | 7.02       |
| [GAL-0.8](https://drive.google.com/open?id=1gQ5vt5KoEPFLF-u2lGcT2bk4PoLcbx_8) | 49.99M  | 0.29M  | 9.64       |
| [FT-GAL-0.6](https://drive.google.com/open?id=1fhYezcYTCbRhN8e3r_0wY_6CZOud736R) | 78.30M  | 0.75M  | 6.62       |
| [FT-GAL-0.8](https://drive.google.com/open?id=1-1-9z6zAfMogAx4HjQ0Gxt67Z9RpkQA4) | 49.99M  | 0.29M  | 8.42       |




