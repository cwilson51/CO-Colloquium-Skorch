# CO-Colloquium-Skorch
Code, notebooks, job scripts from the Compute Ontario Weekly Colloquia, 2023-11-29

**Note: the job scripts and python are meant to be run on Alliance Clusters**

## Intstallation

You can install everything needed for the presentation notebook and python jobs from the requirements file:

```
pip install -r requirements.txt
```

## Running the presentation notebook

To run the notebook in presentation mode you have to use `nbclassic`, since it uses RISE which plays nicer with the older notebook style:

```
jupyter nbclassic
```

## Running the Multi-GPU `GridSearchCV`

You will need to pre-download the CIFAR-10 dataset if running on the clusters.

The job submission script is found in `cifar10_resnet_gs_parallel.sh`

Copy the jobscripts and add your account info `#SBATCH --account=def-somuser` and other options you might want. You'll also need to set up the virtual environment and replace the path in the script.

The scripts otherwise should run as written if you submit the jobs from this repo directory. You may want to specify absolute paths to the python scripts.

I have also included the single GPU example.

## About Resnet

All credit for the ResNet implementation goes to Yerlan Idelbayev. The ResNet implementation can be found at https://github.com/akamaster/pytorch_resnet_cifar10/tree/master which I forked and made installable as a package. **My ResNet package install from github, so you won't be able to install it in a virtual environment on cluster compute nodes. You need to pre install before running on the clusters.**

If you use Yerlan's implementation please cite their repo:

```
@misc{Idelbayev18a,
  author       = "Yerlan Idelbayev",
  title        = "Proper {ResNet} Implementation for {CIFAR10/CIFAR100} in {PyTorch}",
  howpublished = "\url{https://github.com/akamaster/pytorch_resnet_cifar10}",
  note         = "Accessed: 20xx-xx-xx"
}
```
