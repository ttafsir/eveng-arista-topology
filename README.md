# eveng-ios-topology

Simple Network Topology with IOS and NXOS.


## Requirements

To deploy the topology, you will need to have the following:

* a running instance of EVE-NG
* The [evensdk](https://github.com/ttafsir/evengsdk) library and CLI tool.

Images:

* `vios-adventerprisek9-m.vmdk.SPA.156-2.T`
* `nxosv9k-9.3.5`

## Install Requirements

To install the `evengsdk` library and CLI tool, run the following command:

```sh
pip install eve-ng
```

## Configure Your Environment

You can define your environment variables in a `.env` so that you can easily export environemnt variables to configure the EVE-NG CLI tool. **This will prevent you from getting prompted for credentials**.

STEP 1. Create your `.env` file

```txt
export EVE_NG_HOST=10.246.33.49
export EVE_NG_USERNAME=admin
export EVE_NG_PASSWORD=eve
export EVE_NG_LAB_PATH='/cisco-ansible-lab.unl'
```

:warning: The `.env` file is ignored from version control so that you do not accidentally

STEP 2. Source the variables from the file

```sh
source .env
```

## Create lab from topology

Create the lab

```
eve-ng lab create-from-topology -t topology.base.yml
```

Verify that lab is showing in list

```sh
eve-ng lab list
```

View the nodes in your lab

```
eve-ng node list --path /cisco-ansible-lab.unl
```

> Note: To avoid repeatedly having to provide the lab path, you can export `EVE_NG_LAB_PATH=/cisco-ansible-lab.unl` or add it to your `.env` file and source it.

Start your lab

```sh
eve-ng lab start --path /cisco-ansible-lab.unl
```
