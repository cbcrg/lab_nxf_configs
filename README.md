# CBCRG lab nextflow configs

Repository to share `nextflow` configurations files used by the cbcrg-lab.

## How to use a config file
### Including the configuration under a `profile` on the `nextflow.config`

Pick any of the configuration files (e.g. `crg_cbcrg.config`), move it to the `conf` folder of your Nextflow pipeline (or any other folder you decide to use to place the configuration files) and include it using the code below on your `nextflow.config`

```bash
profiles {
    crg {
        // Load the config file
        includeConfig 'conf/config_foo.config'
    }
}
```

The profiles of the `nextflow.config` file become available and can be used  specifying the `-profile` option of Nextflow (see [here](https://www.nextflow.io/docs/latest/config.html#config-profiles). Now you can use the `crg` profile with the command below:

```bash
nextflow run <your_script> -profile crg
```

#### BOVREG project reporting

Note, that the configuration file also includes a nested profile corresponding to the **BovReg project**, see [here](https://github.com/cbcrg/lab_nxf_configs/blob/b6feef65f58bc96b7df2e7fee5909be8137b1f28/conf/crg_cbcrg.config#L100-L113). In the case you want to report your computations to the project you can just use the command below:

```bash
nextflow run <your_script> -profile crg,bovreg
```

Note, that you can only report computations perform on the long and short shared queues (`long-sl7` and `short-sl7` respectively) to the BovReg project. If you computation is urgent keep in mind that these queues might have longing
wating times!!!

### Use directly the configuration file

Place the configuration file e.g. `crg_cbcrg.config` on the folder you decide.

Run your pipeline using the `-c` option:

```bash
nextflow run <your_script> -c /path/to/config/crg_cbcrg.config
```

#### BOVREG project reporting

On this case you just need to set the `bovreg` profile since all the other settings are directly load from the configuration file:

```bash
nextflow run <your_script> -c /path/to/config/crg_cbcrg.config -profile bovreg
```
