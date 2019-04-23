[![docker-cloud-automated](https://img.shields.io/docker/cloud/automated/sagebionetworks/agoradataprocessing.svg)](https://cloud.docker.com/u/sagebionetworks/repository/docker/sagebionetworks/agoradataprocessing) [![Docker Cloud Build Status](https://img.shields.io/docker/cloud/build/sagebionetworks/agoradataprocessing.svg)](https://cloud.docker.com/u/sagebionetworks/repository/docker/sagebionetworks/agoradataprocessing/builds)
# Agora Data Processing

Script for processing data from Synapse to Agora. This required permissions to read and write to specific location in Synapse. Data is stored in the Synapse project at https://www.synapse.org/agora.

To process all Agora data from Synapse files to JSON files suitable for import into the Agora MongoDB, use ([exec/process.R](exec/process.R)), which requires the [config.json](config.json) file. Providing the `--store` parameter will store the results to Synapse.
  
  ```
  exec/./process.R --config config.json --store
  ```

If changes to the gene database used are needed, run [inst/getMyGeneInfo.R](inst/getMyGeneInfo.R) to get gene information from [mygene.info](http://mygene.info). This puts the resulting data into Synapse. This step is required to run separately due to conflicts between the `synapser` and `mygene` R packages.

## Development

The `master` branch has the most recent changes used in production.

The `develop` branch has the most recent changes that are in testing.

There is a long-running `staging` branch that pushes data to a separate data folder for testing purposes.

### Releases

Use semantic versioning for releases.
