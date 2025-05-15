# Instructions for workbench

### Install the env / dependencies / model
```
micromamba create -y -n wan21 python=3.10.12
micromamba activate wan21
pip install -r requirements.txt

# /data in workbench works with a physical SSD
huggingface-cli download Wan-AI/Wan2.1-T2V-1.3B --local-dir /data/Wan2.1-T2V-1.3B
```

### Run a Text2Video generation

```
python generate.py \
       --task t2v-1.3B \
       --size 832*480 \
       --ckpt_dir /data/Wan2.1-T2V-1.3B \
       --offload_model True \
       --t5_cpu \
       --sample_shift 8 \
       --sample_guide_scale 6 \
       --prompt "Two anthropomorphic cats in comfy boxing gear and bright gloves fight intensely on a spotlighted stage."
```




