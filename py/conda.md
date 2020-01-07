# Conda

## Create new Conda Environment
```bash
# create environment
conda create --name <new_env_name>

# create environment with python 3.6
conda create --name <new_env_name> python=3.6
```

also see: <https://docs.conda.io/projects/conda/en/latest/commands/create.html>

## Activate and deactivate Environment
```bash
# activate environment
conda activate <env_name>

# deactivate (leave) environment
conda deactivate
```

see also: <https://docs.conda.io/projects/conda/en/latest/glossary.html?highlight=deactivate#activate-deactivate-environment>

## Update all Packages
```bash
conda update --all
```

see also: <https://docs.conda.io/projects/conda/en/latest/commands/update.html>

## List all available Environments
```bash
conda info --envs
```

see also: <https://docs.conda.io/projects/conda/en/latest/commands/info.html>

## Remove Environment
```bash
conda remove --name <env_name> --all
```

see also: <https://conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html#removing-an-environment>

##  Remove unused cached Packages
```bash
conda clean -a
```

also see: <https://docs.conda.io/projects/conda/en/latest/commands/clean.html>

## conda-forge Pakete erstellen
- conda-forge: <https://conda-forge.org/>
- conda install conda-verify vor dem build: <https://github.com/conda/conda-verify>
- Beispiele:
  - <https://github.com/conda-forge/keras-feedstock>
  - <https://github.com/conda-forge/numpy-feedstock>

## Where are the conda environments stored?
- Mac: `/usr/local/miniconda3/envs`

## Weitere Conda-Channel konfigurieren
Wenn eine Python Bibliothek nicht im Standardverzeichnis von Conda
gepflegt wird, kann es notwendig sein weitere Channel für die
Installation zu konfigurieren.

Hierzu muss in der Conda-Bash der folgende Befehl ausgeführt werden:
`conda config --append channels <Channelname>`

Den passenden Channel findet man unter <https://anaconda.org>

Beispiel für die Bibliothek geopPy: <https://anaconda.org/search?q=geopy>

## Conda Installation and Setup

### Disable automatic base activation: 
```bash
conda config --set auto_activate_base false
```
also see: <https://stackoverflow.com/a/54560785/271118>

### Conda Installation auf Linux
- Download Conda (Python 3.7, Linux, 64bit): <https://conda.io/miniconda.html>
- Installationsdatei ausführbar machen:

```bash
chmod +x Downloads/Miniconda3-latest-Linux-x86_64.sh
```

- Installation starten

```bash
./Downloads/Miniconda3-latest-Linux-x86_64.sh
```

- der Lizenz zustimmen
- default install location zustimmen
- miniconda zu PATH .bashrc hinzufügen lassen -\> mit yes bestätigen
- aus Terminal ausloggen und wieder einloggen

### Conda Installation auf Windows
- Download Mini Conda (nicht Anaconda): <https://conda.io/en/latest/miniconda.html>
- Für Python 3.6 und nicht 2.5 und als 64 bit Version (nicht 32 bit)
- Proxy installieren
  - in der `.condarc` Datei folgendes einfühen (und darauf achten, dass der Key `ssl_verify` nicht doppelt ist), diese Datei liegt unter `C:\Users\<User>`

```YAML
proxy_servers:
  http: http://user:pass@corp.com:8080
  https: https://user:pass@corp.com:8080

ssl_verify: False
```
