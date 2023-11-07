# mist-v2

## Installation

This repository is based on [PyTorch](https://pytorch.org/). Specifically, please make sure your environment satisfies `python==3.10` and `cuda >= 11.6`. We do not guarantee the code's performance on other versions.

If you're a conda user, simply run:
```bash
conda create -n mist-v2 python=3.10
conda activate mist-v2
```


Then, install the other requirements:
```bash
pip install -r requirements.txt
```

## Usage

The default command in the WebUI is:

GPU:
```bash
accelerate launch attacks/iadvdm.py --cuda --low_vram_mode --instance_data_dir_for_adversarial data/training --output_dir output/ --class_data_dir data/class --instance_prompt "a painting in the style of sks, high quality, masterpiece" --class_prompt "a painting, high quality, masterpiece" --mixed_precision bf16 --max_train_steps 3 --checkpointing_iterations 1
```

CPU:
```bash
accelerate launch --cpu attacks/iadvdm.py --instance_data_dir_for_adversarial data/training --output_dir output/ --class_data_dir data/class --instance_prompt "a painting in the style of sks, high quality, masterpiece" --class_prompt "a painting, high quality, masterpiece" --mixed_precision bf16 --max_train_steps 3 --checkpointing_iterations 1
```
