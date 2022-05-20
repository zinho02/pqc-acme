# Post-Quantum ACME Protocol

## Completion of course work
**Course:** Computer Science
**University:** Federal University of Santa Catarina (UFSC)
**Author:** Matheus de Oliveira Saldanha


### Instructions for setting up the environment and running the ACME client and server

The instructions are for a Linux environment.

First, make sure that Go is installed, if not, just access the [Go page](https://go.dev/) and follow the download instructions.

After that, create the following folder structure in the ```$HOME``` directory:

```
mkdir -p go/src/github.com/{username}
mkdir -p go/bin
mkdir -p go/pkg
```

Where {username} is any name.

After this:

```
cd go/src/github.com/{username}
git clone git@github.com:zinho02/pqc-acme.git
```

Follow the instructions to install the *bindings* from **LibOQS** to **Go** and install the repository at ```$HOME/go/src/github.com/```, they can be found [here ](https://github.com/open-quantum-safe/liboqs-go).

With that done, change the end of the ```$HOME/.bashrc``` file with the following changes:

```shell
export GOROOT=$HOME/go/src/github.com/{user}/go
export GOPATH=$HOME/go:$HOME/go/src/github.com/{username}/go:$HOME/go/src/github.com/{username}
export PATH=$GOPATH/bin:$GOROOT/bin:$PATH
export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/usr/local/lib
export PKG_CONFIG_PATH=$PKG_CONFIG_PATH:$HOME/go/src/github.com/liboqs-go/.config
```

With that done, just run the available ACME client and server instructions:
- [ACME Client](https://github.com/go-acme/lego)
- [ACME Server](https://github.com/letsencrypt/pebble)
