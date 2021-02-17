# 21M.387 - Fund. of Digital Music Processing

## Resources

[`Fund. of Music Processing (MIT login)`](https://link-springer-com.libproxy.mit.edu/book/10.1007%2F978-3-319-21945-5)
[`Mathematics of DFT with Audio Applications`](https://ccrma.stanford.edu/~jos/mdft/mdft.html)

## Setup
### Install Python3

Linux:
```
$ sudo apt install python3-pip python3-venv python3-tk
```

Mac OS X (via Homebrew):
```
$ brew install python@3
$ pip3 install virtualenv
```

### Setup virtual env

```
$ python3 -m venv /path/to/your/venv
$ source /path/to/your/venv/bin/activate
```

### Install python dependencies

```
$ pip3 install --no-cache-dir -r requirements.txt
$ jupyter nbextension enable --py widgetsnbextension
```

### Setup Jupyter kernel

Some docs online state that you need to create a separate kernel from
your virtualenv, and this is how you can go about that:
```
$ python -m ipykernel install --user --name=fmp
```

Though if you don't create a kernel, so long as you used the pip from
your activated virtualenv to install jupyter, the default Python kernel
should already be good to go:
```
$ jupyter kernelspec list
Available kernels:
  fmp        /home/jmf/.local/share/jupyter/kernels/fmp
  python3    /home/jmf/src/venv/fmp/share/jupyter/kernels/python3
```

You can select which kernel to use from a drop-down menu in the jupyter UI.

## Running
To start out a local jupyter instance, you can run the command below from this
directory:

```
$ jupyter notebook <notebook_file.ipynb>
```

And then open your browser at `http://localhost:8888` to access it. Click on any of the .ipynb files to open a notebook.

If you're running this notebook server remotely, however, and trying to access the
it from a different machine, you can create a ssh tunnel for that.

From your client (the machine you're ssh'ing from):
```bash
$ ssh -L 8080:localhost:8888 user@yourserver.org
```

From your server (the machine you ssh'ed to, and from which you'll be running
the jupyter notebook server):
```
$ ./run.sh       # starts out the jupyter server
```

Then from your client machine, direct your browser to `http://localhost:8080`
to access the jupyter server.
