# Protocolo ACME Pós-Quântico

## Trabalho de Conclusão de Curso
**Curso:** Ciência da Computação  
**Universidade:** Universidade Federal de Santa Catarina (UFSC)  
**Autor:** Matheus de Oliveira Saldanha


### Instruções para configurar o ambiente e executar o cliente e servidor ACME

As instruções são para um ambiente Linux.

Primeiramente, certifique-se que o Go está instalado, caso não esteja, basta acessar a [página do Go](https://go.dev/) e seguir as instruções para o download.

Após isso, crie no diretório ```$HOME``` a seguinte estrutura de pastas:

```
mkdir -p go/src/github.com/{usuario}
mkdir -p go/bin
mkdir -p go/pkg
```

Onde {usuario} é um nome qualquer.

Após isso:

```
cd go/src/github.com/{usuario}
git clone git@github.com:zinho02/pqc-acme.git
```

Siga as instruções para instalar as *bindings* da **LibOQS** para **Go** e instale o repositório em ```$HOME/go/src/github.com/```, elas podem ser encontradas [aqui](https://github.com/open-quantum-safe/liboqs-go).

Com isso feito, altere o final do arquivo ```$HOME/.bashrc``` com as seguintes alterações:

```shell
export GOROOT=$HOME/go/src/github.com/{usuario}/go
export GOPATH=$HOME/go:$HOME/go/src/github.com/{usuario}/go:$HOME/go/src/github.com/{usuario}
export PATH=$GOPATH/bin:$GOROOT/bin:$PATH
export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/usr/local/lib
export PKG_CONFIG_PATH=$PKG_CONFIG_PATH:$HOME/go/src/github.com/liboqs-go/.config
```

Com isso feito, basta rodar as instruções do cliente e do servidor ACME disponíveis:  
-  [Cliente ACME](https://github.com/go-acme/lego)
-  [Servidor ACME](https://github.com/letsencrypt/pebble)
