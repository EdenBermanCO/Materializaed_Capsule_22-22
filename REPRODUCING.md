This [Code Ocean](https://codeocean.com) Compute Capsule will allow you to run and reproduce the results of [Original Materialized Capsule](https://useast1.r2220.aws.codeocean.dev/capsule/3667489/tree) on your local machine<sup>1</sup>. Follow the instructions below, or consult [our knowledge base](https://docs.codeocean.com/user-guide/compute-capsule-basics/managing-capsules/exporting-capsules-to-your-local-machine) for more information. Don't hesitate to reach out to [Support](mailto:support@codeocean.com) if you have any questions.

<sup>1</sup> You may need access to additional hardware and/or software licenses.

# Prerequisites

- [Docker Community Edition (CE)](https://www.docker.com/community-edition)

# Instructions

## Download attached Data Assets

In order to fetch the Data Asset(s) this Capsule depends on, download them into the Capsule's `data` folder:
* [Inside](https://useast1.r2220.aws.codeocean.dev/data-assets/2737f122-3233-4970-be41-64fa967fadcf) should be downloaded to `data/Internal`

## Log in to the Docker registry

In your terminal, execute the following command, providing your password or API key when prompted for it:
```shell
docker login -u eden.berman@codeocean.com registry.useast1.r2220.aws.codeocean.dev
```

## Run the Capsule to reproduce the results

In your terminal, navigate to the folder where you've extracted the Capsule and execute the following command, adjusting parameters as needed:
```shell
docker run --platform linux/amd64 --rm \
  --workdir /code \
  --volume "$PWD/code":/code \
  --volume "$PWD/data":/data \
  --volume "$PWD/results":/results \
  registry.useast1.r2220.aws.codeocean.dev/capsule/1fc210c5-d22a-48db-aeab-4c5035e6435a \
  bash run a 2.2
```
