# VisionPorComputadoras
>Introduction tutorial to getting started in Deep Learning with Keras

- Jorge Sanchez
- Pablo Pastore

-------------------------------------------

## Dependencies

- Python 3+
- [pip](https://pip.pypa.io/en/stable/) >= 9.0
- virtualenv
- virtualenvwrapper
- tensorflow

### Virtualenv and Virtualenvwrapper

`$ pip3 install --user virtualenv virtualenvwrapper`

Then add the following lines to the bottom of you `~/.bashrc` file:

```
# virtualenv and virtualenvwrapper settings
export VIRTUALENVWRAPPER_PYTHON=/usr/bin/python3
[[ -s "$HOME/.local/bin/virtualenvwrapper.sh" ]] && source "$HOME/.local/bin/virtualenvwrapper.sh"
```

Update changes:

`$ source ~/.bashrc`

You should see an output like this:

```
virtualenvwrapper.user_scripts creating /home/<username>/.virtualenvs/premkproject
virtualenvwrapper.user_scripts creating /home/<username>/.virtualenvs/postmkproject
virtualenvwrapper.user_scripts creating /home/<username>/.virtualenvs/initialize
virtualenvwrapper.user_scripts creating /home/<username>/.virtualenvs/premkvirtualenv
virtualenvwrapper.user_scripts creating /home/<username>/.virtualenvs/postmkvirtualenv
virtualenvwrapper.user_scripts creating /home/<username>/.virtualenvs/prermvirtualenv
virtualenvwrapper.user_scripts creating /home/<username>/.virtualenvs/postrmvirtualenv
virtualenvwrapper.user_scripts creating /home/<username>/.virtualenvs/predeactivate
virtualenvwrapper.user_scripts creating /home/<username>/.virtualenvs/postdeactivate
virtualenvwrapper.user_scripts creating /home/<username>/.virtualenvs/preactivate
virtualenvwrapper.user_scripts creating /home/<username>/.virtualenvs/postactivate
virtualenvwrapper.user_scripts creating /home/<username>/.virtualenvs/get_env_details
```

Create virtualenv:

`$ mkvirtualenv <name> --python=/usr/bin/python3`

### Additional Python libs

Install other Python libraries with: 
`$ pip install -r requirements.txt`

### Tensorflow

#### CPU only

`$ pip install tensorflow==1.5`

#### Using the GPU:

Maybe you should add the following lines to you `~/.bashrc`:

```
# Cuda and cudnn
export PATH=$PATH:/opt/cuda/8.0/bin
export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/opt/cudnn/v6:/opt/cuda/8.0/lib64
```

The tensorflow version that you should install depends on you Cuda and Cudnn version. For example for Cuda 8.0 with Cudnn 6.0 we should install the following version:
`$ pip install tensorflow-gpu==1.4.1`

-------------------------------------------

## Run Notebooks

### Local machine:

`$ jupyter notebook`

### Working on a remote server:

1. Launch notebook on the server:

`$ jupyter notebook --port=<port>  --no-browser --ip=0.0.0.0`

2. Make a tunnel on your local machine:

`$ ssh -f remote_user@remote_host -L <port>:localhost:<port> -N`

3. Then go to: http://localhost:<port>/?token=<token>

