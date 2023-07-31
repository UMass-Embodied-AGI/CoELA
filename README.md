# Building Cooperative Embodied Agents Modularly with Large Language Models

This repo contains codes for the following paper:

_Hongxin Zhang*, Weihua Du*, Jiaming Shan, Qinhong Zhou, Yilun Du, Joshua B. Tenenbaum, Tianmin Shu, Chuang Gan_: Building Cooperative Embodied Agents Modularly with Large Language Models 

Paper: [Arxiv](https://arxiv.org/abs/2307.02485)

Project Website: [Co-LLM-Agents](https://vis-www.cs.umass.edu/Co-LLM-Agents/)

![Pipeline](assets/pipeline.png)

## News

**[8/1/2023]**: we found that there are some missing files in Virtual Home's executable zip, we update a new one [here](https://drive.google.com/file/d/1JTrV5jdF-LQVwY3OsV3Jd3r6PRghyHBp/view?usp=sharing). If you meet `XDG_RUNTIME_DIR not set in the environment` error, please download it.

## Installation

For detailed instructions on the installation of the two embodied multi-agent environments `Communicative Watch-And-Help` and `ThreeDWorld Multi-Agent Transport`, please refer to the Setup sections in `envs/cwah/README.md` and `envs/tdw_mat/README.md`, respectively.

### A simple start guide for `Communicative Watch-And-Help`:

**Step 1**: Get the VirtualHome Simulator and API

Clone the [VirtualHome API](https://github.com/xavierpuigf/virtualhome.git) repository in envs dictionary:

```bash
cd envs
git clone --branch wah https://github.com/xavierpuigf/virtualhome.git
```

Download the [Simulator](https://drive.google.com/file/d/1JTrV5jdF-LQVwY3OsV3Jd3r6PRghyHBp/view?usp=sharing) (Linux x86-64 version), and unzip it in `envs`.

The files should be organized as follows:

```bash
|--cwah/
|--virtualhome/
|--executable/
```

**Step 2**: Install Requirements
```bash
cd cwah
conda create --name cwah python=3.8
conda activate cwah
pip install -r requirements.txt
```

### A simple start guide for `ThreeDWorld Multi-Agent Transport`:

Run the following commands step by step to setup the environments:

```bash
cd envs/tdw_mat
conda create -n tdw_mat python=3.9
conda activate tdw_mat
pip3 install -e .
```

After that, you can run the demo scene to verify your setup:

```bash
python demo/demo_scene.py
```

## Run Experiments

The main implementation code of our Cooperative LLM Agents is in `envs/*/LLM` and `envs/*/lm_agent.py`. The scripts for running the agents are in `envs/*/scripts` folder, you can try to run them on your own.

When running the scripts, be sure that you are in the parent folder of `scripts` (i.e., `envs/tdw_mat` or `envs/cwah`).

## Results

Our experiment shows that llm agents can achieve comparable performance regard to human-designed hierarchical planning agents (hp agents):

![quantitative_results](assets/quantitative_results.png)

Besides, we found many interesting behavoirs of llm agents in the multi-agent settings:

![qualitative_results](assets/qualitative_results.png)

## Citation
If you find our work useful, please consider citing:
```
@article{zhang2023building,
  title={Building Cooperative Embodied Agents Modularly with Large Language Models},
  author={Zhang, Hongxin and Du, Weihua and Shan, Jiaming and Zhou, Qinhong and Du, Yilun and Tenenbaum, Joshua B and Shu, Tianmin and Gan, Chuang},
  journal={arXiv preprint arXiv:2307.02485},
  year={2023}
}
```
