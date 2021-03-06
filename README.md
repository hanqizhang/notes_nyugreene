# notes_nyugreene
Notes and useful references for setting up the NYU Greene HPC

## singularity and miniconda
The first thing to do to get started on Greene is to set up a [singularity](https://en.wikipedia.org/wiki/Singularity_(software)) container. Then you are free to install stuff in your conda environment. For guide on setting up singularity and conda, follow NYU HPC's official guide:  
https://sites.google.com/nyu.edu/nyu-hpc/hpc-systems/greene/software/singularity-with-miniconda  
I had some issues with the pytorch version as suggested in this line:
```
pip3 install torch==1.10.0+cu113 torchvision==0.11.1+cu113 torchaudio==0.10.0+cu113 -f https://download.pytorch.org/whl/cu113/torch_stable.html
```
Finding and downloading the right version of torch and cuda will resolve the issue.

## notes for running jupyter notebook on greene with ssh port forwarding, in the context of singularity container
For the most part, we can follow the tutorial in this link:  
https://dorukkilitcioglu.com/2018/11/18/nyu-hpc-data-science.html  
The instructions were based on the old Prince cluster, but are still valid for Greene,
except for the content in the sbatch file. This is because Singularity is adopted for
Greene, so we have to run Jupyter in a Singularity container.

For an example sbatch file, please see my run-jupyter.sbatch in this repo.

Your slurm-<job id>.out will output something like the following:  
```
[I 22:10:48.082 NotebookApp] Serving notebooks from local directory: /home/<net-id>/tools/batch  
[I 22:10:48.083 NotebookApp] Jupyter Notebook 6.4.6 is running at:  
[I 22:10:48.083 NotebookApp] http://localhost:8766/  
[I 22:10:48.083 NotebookApp] Use Control-C to stop this server and shut down all kernels (twice to skip confirmation).  
```

Note that I don't have to input jupyter notebook token here. It is also okay to use a token, but I feel it's worth it to set up a password like [so](https://jupyter-notebook.readthedocs.io/en/stable/public_server.html).
