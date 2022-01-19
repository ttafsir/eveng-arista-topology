# eveng-arista-topology
This repository provides a topology file for EVE-NG that be used and modified to quickly provision an Arista L3LS+EVPN topology for practice/testing. The instructions below demonstrate how to use the [evensdk](https://github.com/ttafsir/evengsdk) library and CLI to deploy this lab in your existing EVE-NG deployment.

![image-20220114164837189](./topology-base.png)


## Install Requirements

```sh
pip install eve-ng
```

## Configure Your Environment

You can define your environment variables in a `.env` so that you can easily export environemnt variables to configure the EVE-NG CLI tool. **This will prevent you from getting prompted for credentials**.

STEP 1. Create your `.env` file

```txt
export EVE_NG_HOST=192.168.2.100
export EVE_NG_USERNAME=admin
export EVE_NG_PASSWORD=eve
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
eve-ng node list --path /arista-level3-lab.unl
```

> Note: To avoid repeatedly having to provide the lab path, you can export `EVE_NG_LAB_PATH=/arista-level3-lab.unl` or add it to your `.env` file and source it.

Start your lab

```sh
eve-ng lab start --path /arista-level3-lab.unl
```
