# nextflow_scri_config
An SCRI nextflow profile for NF-Core for reference which is pulled to 'https://github.com/nf-core/configs/blob/master/conf/seattlechildrens.config'.

### Test the config file 

Please note that `--assoc` parameter can be specified on the command line in `nextflow run` or in the `seattlechildrens.config`. 

```bash
mamba activate nextflow

# For running on an interactive session on cybertron with singularity module loaded
nextflow run -c 'conf/seattlechildrens.config' \
    nf-core/rnaseq \
    -r 3.14.0 \
    -profile test,sasquatch \
    --outdir "/home/$USER/temp/nf-core-rnaseq-test" \
    --assoc "rsc" \
    --validationSchemaIgnoreParams 'assoc'
```

```bash
nextflow run -c 'conf/seattlechildrens.config' \
    nf-core/fetchngs \
    -r 1.12.0 \
    -profile test,sasquatch \
    --input ./ids.csv \
    --download_method 'sratools' \
    --assoc "rsc" \
    --outdir "/home/$USER/fetchngs"
```

```
nf-core launch nf-core/methylseq -r 2.6.0
```



### Change log

`2025.02.21` Preliminary updates for Sasquatch.
`2023.03.18` Built during nf-core biohackathon which synced for Cybertron and PBS. 







