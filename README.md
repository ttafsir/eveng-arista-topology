# eveng-arista-topology
Arista Leaf Spine topology for L3 lab practice

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

```
eve-ng lab create-from-topology -t topology.base.yml
```

```sh
eve-ng lab list
```
