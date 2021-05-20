# CBCRG lab nextflow configs

Repository to share `nextflow` configurations files used by the cbcrg-lab.

## How to use a config file

Pick any of the configuration files (e.g. `config_foo.config`), move it to the `conf` folder of your Nextflow pipeline (or any other folder you decide to use to place the configuration files) and include it using the code below on your `nextflow.config`

```bash
// Load the config file
includeConfig 'conf/config_foo.config'
```

The profiles of the config files become available and can be used  specifying the `-profile` option of Nextflow (see [here](https://www.nextflow.io/docs/latest/config.html#config-profiles) for a detailed explanation). As an example, if the configuration file sets a `singularity` and a `crg_cluster` profile you could use the command below to use them simultaneously:

```bash
nextflow run <your_script> -profile crg_cluster,singularity
```
## How to add a new config file

TODO
