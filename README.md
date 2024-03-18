# nextflow_scri_config
An SCRI nextflow profile for NF-Core for reference which is pulled to 'https://github.com/nf-core/configs/blob/master/conf/seattlechildrens.config'.

SCRI does have some recommended settings for Singularity in the nextflow config, but might not be correct for all pipelines. 
Here is an example of the singularity scope settings used in most SCRI pipelines.

```bash
//Configs for singularity containers on cybertron
singularity {
    autoMounts = true
    cacheDir = "$HOME/singularity_test"
    runOptions = '--containall --no-home'
}
```

```bash
nextflow run -c 'conf/seattlechildrens.config' \
    nf-core/rnaseq \
    -r 3.14.0 \
    -profile test,local_singularity
    --outdir ~/temp
```

`2023.03.18` Built during nf-core biohackathon which synced for Cybertron and PBS. 







