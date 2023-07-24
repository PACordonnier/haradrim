
# TOSIT Haradrim v0.0.1

Haradrim installs everything necessary to install TDP on your cluster of machines.

## Prerequisites

Install required packages:

- `python` >= 3.9 with virtual env package (i.e. `python3-venv`)
- `npm` >= 14.13.0
- `jq`
- `git`
- `curl`

## Features

- Downloads in a local cache TDP Stack binaries for the targeted distribution version
- Create a python virtual environment with Ansible, tdp-lib and tdp-server
- Create configuration for the lib and the server
- Downloads TDP-UI and creates its configuration
- Configure ansible-galaxy dependencies for the collections you want to use
- Initialize the tdp-variables

## Usage

1. Export environment variables if necessary, for example:

```bash
export PYTHON_BIN=/path/to/python
export NPM_BIN=/path/to/npm
```

2. Create `config.json` using [this example](config.example.json).

3. Curl or clone haradrim script and run it:

```bash
# curl -L https://github.com/path/to/release haradrim
# git clone https://github.com/PACordonnier/haradrim
cd haradrim
./haradrim
```

> Call help to learn all possible options:
  ```bash
  ./haradrim -h
  ```

## Using TDP manager

After setup, use TDP manager in the separate terminals.

TDP lib:

```bash
source venv/bin/activate && source .env
tdp browse
```

TDP server:

```bash
source venv/bin/activate && source .env
uvicorn tdp_server.main:app --reload
```

TDP UI:

```bash
npm --prefix ./tdp-ui run dev
```

## Authors

- Paul-Adrian Cordonnier
- Sergei Kudinov