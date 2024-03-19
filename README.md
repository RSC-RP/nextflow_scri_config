# nextflow_scri_config
An SCRI nextflow profile for NF-Core for reference which is pulled to 'https://github.com/nf-core/configs/blob/master/conf/seattlechildrens.config'.

The provided config here does not include the [singularity scope](https://www.nextflow.io/docs/latest/config.html#scope-singularity), but SCRI does have some recommended settings for Singularity in the nextflow config, but might not be correct for all pipelines. 

Here is an example of the singularity scope settings used in most SCRI pipelines.

```groovy
//Configs for singularity containers on cybertron
singularity {
    autoMounts = true
    cacheDir = "$HOME/singularity_test"
    runOptions = '--containall --no-home'
}
```

### Test the config file 

Please note that `--project` parameter can be specified on the command line in `nextflow run` or in the `seattlechildrens.config`. 

```bash
ml singularity

# For running on an interactive session on cybertron with singularity module loaded
nextflow run -c 'conf/seattlechildrens.config' \
    nf-core/rnaseq \
    -r 3.14.0 \
    -profile test,local_singularity \
    --outdir "/home/$USER/temp/nf-core-rnaseq-test" \
    --project "207f23bf-acb6-4835-8bfe-142436acb58c" \
    --validationSchemaIgnoreParams 'queue,project'

# For executing the jobs on the HPC cluster with singularity containers
# doesn't work due to bioconductor-dupradar:1.28.0--r42hdfd78af_0
nextflow run -c 'conf/seattlechildrens.config' \
    nf-core/rnaseq \
    -r 3.14.0 \
    -profile test,PBS_singularity \
    --max_memory 32.GB \
    --outdir "/home/$USER/temp/nf-core-rnaseq-test" \
    --project "207f23bf-acb6-4835-8bfe-142436acb58c" \
    --validationSchemaIgnoreParams 'queue,project'
```

```bash
# doesnt work due to wget: unable to resolve host address 'ftp.sra.ebi.ac.uk'
nextflow -c 'conf/seattlechildrens.config' \
    run nf-core/fetchngs \
    -r 1.12.0 \
    -profile test,PBS_singularity \
    --input ids.csv \
    --project "207f23bf-acb6-4835-8bfe-142436acb58c" \
    --outdir "/home/$USER/fetchngs"
```

```
nf-core launch nf-core/methylseq -r 2.6.0
```


### Change log

`2023.03.18` Built during nf-core biohackathon which synced for Cybertron and PBS. 







