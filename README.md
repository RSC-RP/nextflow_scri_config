# nextflow_scri_config
An SCRI nextflow profile for NF-Core for reference which is pulled to 'https://github.com/nf-core/configs/blob/master/conf/seattlechildrens.config'.

### Test the config file 

Please note that `--assoc` parameter can be specified on the command line in `nextflow run` or in a params or config file. 

```bash
mamba activate nextflow

# For running on an interactive session on sasquatch
nextflow run \
    nf-core/rnaseq \
    -r 3.14.0 \
    -profile seattlechildrens,test \
    --outdir "/data/hps/assoc/private/rsc/user/$USER/nf-core-rnaseq-test" \
    --assoc "rsc" \
    --validationSchemaIgnoreParams 'assoc'
```

```bash
nextflow run \
    nf-core/fetchngs \
    -r 1.12.0 \
    -profile seattlechildrens,test \
    --input ./ids.csv \
    --download_method 'sratools' \
    --assoc "rsc" \
    --outdir "/data/hps/assoc/private/rsc/user/$USER/fetchngs-test"
```

```
nf-core launch nf-core/methylseq -r 2.6.0
```



### Change log

`2025.02.21` Preliminary updates for Sasquatch.
`2023.03.18` Built during nf-core biohackathon which synced for Cybertron and PBS. 







