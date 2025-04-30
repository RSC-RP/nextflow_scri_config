# nextflow_scri_config
An SCRI nextflow profile for NF-Core for reference which is pulled to 'https://github.com/nf-core/configs/blob/master/conf/seattlechildrens.config'.

### Test the config file 

Unlike with our local "sasquatch.config" file, we must specify the association with an environmental variable rather than as a parameter.

```bash
mamba activate nextflow

export ASSOC="rsc"

# For running on an interactive session on sasquatch
nextflow run \
    nf-core/rnaseq \
    -r 3.14.0 \
    -profile seattlechildrens,test \
    --outdir "/data/hps/assoc/private/rsc/user/$USER/nf-core-rnaseq-test" \
    -work-dir "/data/hps/assoc/private/rsc/user/$USER/nf-core-rnaseq-test-temp"
```

```bash
export ASSOC="rsc"

nextflow run \
    nf-core/fetchngs \
    -r 1.12.0 \
    -profile seattlechildrens,test \
    --input ./ids.csv \
    --download_method 'sratools' \
    --outdir "/data/hps/assoc/private/rsc/user/$USER/fetchngs-test" \
    -work-dir "/data/hps/assoc/private/rsc/user/$USER/fetchngs-test-temp"
```

```
nf-core launch nf-core/methylseq -r 2.6.0
```



### Change log

`2025.04.30` Minor touchups and draft config for `process_gpu`.

`2025.02.21` Preliminary updates for Sasquatch.

`2023.03.18` Built during nf-core biohackathon which synced for Cybertron and PBS. 







