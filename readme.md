<p align="center">

  <h2 align="center">Zero-shot Image Editing with Reference Imitation</h2>
  <p align="center">
    <a href="https://xavierchen34.github.io/"><strong>Xi Chen</strong></a>
    ·
    <a href="https://scholar.google.com.hk/citations?user=mZwJLeUAAAAJ&hl=zh-CN"><strong>Yutong Feng</strong></a>
    ·
    <a href="https://mengtingchen.github.io/"><strong>Mengting Chen</strong></a>
    ·
    <a href="https://openreview.net/profile?id=~Yiyang_Wang2"><strong>Yiyang Wang</strong></a>
    ·
    <a href="https://jshilong.github.io/"><strong>Shilong Zhang</strong></a>
    ·
    <a href="https://scholar.google.com/citations?user=8zksQb4AAAAJ&hl=zh-CN"><strong>Yu Liu</strong></a>
    ·
    <a href="https://shenyujun.github.io/"><strong>Yujun Shen</strong></a>
    ·
    <a href="https://hszhao.github.io/"><strong>Hengshuang Zhao</strong></a>
    <br>
    <br>
        <a href="https://arxiv.org/abs/2406.07547"><img src='https://img.shields.io/badge/arXiv-MimicBrush-red' alt='Paper PDF'></a>
        <a href='https://xavierchen34.github.io/MimicBrush-Page/'><img src='https://img.shields.io/badge/Project_Page-MimicBrush-green' alt='Project Page'></a>
        <a href='https://huggingface.co/spaces/xichenhku/MimicBrush'><img src='https://img.shields.io/badge/%F0%9F%A4%97%20Hugging%20Face-Spaces-blue'></a>
    <br>
    <b>The University of Hong Kong &nbsp; | &nbsp;  Alibaba Group  | &nbsp;  Ant Group </b>
  </p>
  
  <table align="center">
    <tr>
    <td>
      <img src="assets/teaser.png">
    </td>
    </tr>
  </table>

## News
* **[2024.06.12]** Release inference code, local gradio demo, online demo.
* **[Todo]** Release our benchmark.


## Installation
Install with `pip`:

```bash
#Python==3.8.5
conda env create -f environment.yaml
conda activate mimicbrush
pip install —upgrade transformers==4.29.0 # for Segment Anything (SAM)
```


## Download Checkpoints
Download SD-1.5 and SD-1.5-inpainting checkpoint from Huggingface:

```python
from huggingface_hub import snapshot_download
snapshot_download(repo_id="xichenhku/cleansd", local_dir="./cleansd")
print('=== Pretrained SD weights downloaded ===')
snapshot_download(repo_id="xichenhku/MimicBrush", local_dir="./MimicBrush")
print('=== MimicBrush weights downloaded ===')
```


## Gradio Demo 
First, modify `./configs/inference.yaml` to set the path of model weight. Afterwards, run the script:
```bash
python run_gradio3_demo.py
```

The gradio demo would look like the UI shown below. 

<font color="#dd0000">*Please do not forget to click ''keep the original shape'' if you want condut texture transfer like the third case.</font><br /> 

A biref tutorial:

* Upload/select a source image to edit. 
* Draw the to-edit regionon the source image.
* Upload/select a reference image. 
* Run. 

<table align="center">
  <tr>
  <td>
    <img src="assets/demo.png">
  </td>
  </tr>
</table>

## Inference

1. Dowload our evaluation benchmark at Google Drive:
    * URL: [to be released]

2. Set the path to each dataset and checkpoints in `./config/inference.yaml` :

3. Run inference with 
    ```bash
    python run_inference_benchmark.py
    ```


## Acknowledgements
This project is developped on the codebase of [IP-Adapter](https://github.com/tencent-ailab/IP-Adapter) and [MagicAnimate](https://github.com/magic-research/magic-animate)  . We  appreciate this great work! 


## Citation
If you find this codebase useful for your research, please use the following entry.
```BibTeX
@article{chen2024mimicbrush,
  title={Zero-shot Image Editing with Reference Imitation},
  author={Chen, Xi and Feng, Yutong and Chen, Mengting and Wang, Yiyang, and Zhang, Shilong and Yu, Liu and Shen, Yujun and Zhao, Hengshuang},
  journal={arXiv preprint arXiv:2406.07547},
  year={2024}
}
```