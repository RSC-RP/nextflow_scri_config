# documentation
This config file is created for the use on the Cybertron HPC at Seattle Children Research Institude (SCRI), Seattle, WA. Using this config will pre-configure a set up suitable for the Cybertron HPC. The Singularity images will be downloaded to run on the cluster. The nextflow pipeline should be executed inside of the Cybertron system.

```groovy
//To list all the projects you are authorized on HPC.
project info
```

//It will list all the project names, project codes and expiration dates.
//Example Interactive Job with 4GB Memory:
```groovy
qsub -I -q freeq -l select=1:ncpus=1:mem=4g -l walltime=1:00:00 -P [PROJECT CODE]
qsub -I -q freeq -l select=1:ncpus=1:mem=4g -l walltime=1:00:00 -P $(project code [PROJECT NAME])
```
//For more details, use project info --detail

