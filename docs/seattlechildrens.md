# nf-core/configs: PROFILE Configuration

All nf-core pipelines have been successfully configured for use on the the Cybertron HPC at Seattle Children Research Institude (SCRI), Seattle, WA.

To use, run the pipeline with `-profile PROFILENAME`. This will download and launch the [`seattlechildrens.config`](../conf/seattlechildrens.config) which has been pre-configured with a setup suitable for the Cybertron cluster at SCRI. Using this profile, a docker image containing all of the required software will be downloaded, and converted to a Singularity image before execution of the pipeline.

# Below are non-mandatory information 
Before running the pipeline you will need to create a Nextflow environment on `mamba`. You might also load _Singularity_ using the environment module system on Cybertron. 

## Create Nextflow environment on `mamba`

1. Create _nextflow.yml_ file containing the following content 

```yaml
name: nextflow
channels:
  - bioconda
  - conda-forge
dependencies:
  - python>=3.9
  - nextflow==23.10.0
  - nf-core==2.10
  - graphviz
```
2. Create the _Nextflow_ environment on `manba`
```bash
> mamba env create -f nextflow.yaml
```

3. Setting channel priority
Make sure that channel priority is set to flexible using the following comments:

```bash
> mamba config --describe channel_priority # print your current conda settings
> mamba config --set channel_priority flexible # set to flexible if not already done
```

## module load _Singularity_ (option)

```bash
ml singularity/3.9.9
```



