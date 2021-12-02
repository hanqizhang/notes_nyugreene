# notes_nyugreene
Notes and useful references for setting up the NYU Greene HPC

## singularity and miniconda
For the most part, you can follow Greene's official guide: 
https://sites.google.com/nyu.edu/nyu-hpc/hpc-systems/greene/software/singularity-with-miniconda
I had some issues with the pytorch version as suggested in this line:
<code>pip3 install torch==1.10.0+cu113 torchvision==0.11.1+cu113 torchaudio==0.10.0+cu113 -f https://download.pytorch.org/whl/cu113/torch_stable.html</code>
Finding and downloading the right version of torch and cuda will resolve the issue.

## notes for forwarding jupyter notebook in the context of singularity container
For the most part, we can follow the tutorial in this link:
https://dorukkilitcioglu.com/2018/11/18/nyu-hpc-data-science.html
The instructions were based on the old Prince cluster, but are still valid for Greene,
except for the content in the sbatch file. This is because Singularity is adopted for
Greene, so we have to run Jupyter in a Singularity container.

For an example sbatch file, please see my run-jupyter.sbatch in this repo.
