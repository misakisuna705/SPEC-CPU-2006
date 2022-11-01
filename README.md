# SPEC CPU®2006

<!-- vim-markdown-toc GFM -->

* [參數](#參數)
    - [系統](#系統)
    - [目標](#目標)
* [環境](#環境)
    - [compiler](#compiler)
    - [cross compiler](#cross-compiler)
* [SPEC CPU®2006](#spec-cpu2006)
    - [安裝](#安裝)
    - [配置](#配置)
    - [400.perlbench](#400perlbench)
        + [構建](#構建)
        + [執行](#執行)
    - [401.bzip2](#401bzip2)
        + [構建](#構建-1)
        + [執行](#執行-1)
    - [403.gcc](#403gcc)
        + [構建](#構建-2)
        + [執行](#執行-2)
    - [429.mcf](#429mcf)
        + [構建](#構建-3)
        + [執行](#執行-3)
    - [433.milc](#433milc)
        + [構建](#構建-4)
        + [執行](#執行-4)
    - [444.namd](#444namd)
        + [構建](#構建-5)
        + [執行](#執行-5)

<!-- vim-markdown-toc -->

---

## 參數

### 系統

-   Ubuntu 18.04（WSL）

### 目標

-   arm64

## 環境

-   /etc/apt/sources.list

```apacheconf
deb http://dk.archive.ubuntu.com/ubuntu/ xenial universe
```

### compiler

```zsh
sudo apt install -y gcc
sudo apt install -y g++
```

### cross compiler

```zsh
sudo apt install -y gcc-4.9-aarch64-linux-gnu
sudo apt install -y g++-4.9-aarch64-linux-gnu

```

## SPEC CPU®2006

### 安裝

```zsh
./speccpu2006/tools/src/buildtools
```

### 配置

```zsh
cd speccpu2006

cp -f config/linux64-arm64-gcc.cfg config/test.cfg
```

-   config/test.cfg

```apacheconf
CC = aarch64-linux-gnu-gcc-4.9 -static
CXX = aarch64-linux-gnu-g++-4.9 -static
```

### 400.perlbench

#### 構建

```zsh
source shrc

runspec -D -c test.cfg -i test -n 1 -T base 400.perlbench
```

#### 執行

```zsh
cd benchspec/CPU2006/400.perlbench/run/run_base_test_lnx64-gcc.0000

touch ./400.perlbench.sh && chmod u+x ./400.perlbench.sh
specinvoke -n *.cmd | grep ../ | cut -f1 -d">" >> ./400.perlbench.sh

./400.perlbench.sh
```

### 401.bzip2

#### 構建

```zsh
source shrc

runspec -D -c test.cfg -i test -n 1 -T base 401.bzip2
```

#### 執行

```zsh
cd benchspec/CPU2006/401.bzip2/run/run_base_test_lnx64-gcc.0000

touch ./401.bzip2.sh && chmod u+x ./401.bzip2.sh
specinvoke -n *.cmd | grep ../ | cut -f1 -d">" >> ./401.bzip2.sh

./401.bzip2.sh
```

### 403.gcc

#### 構建

```zsh
source shrc

runspec -D -c test.cfg -i test -n 1 -T base 403.gcc
```

#### 執行

```zsh
cd benchspec/CPU2006/403.gcc/run/run_base_test_lnx64-gcc.0000

touch ./403.gcc.sh && chmod u+x ./403.gcc.sh
specinvoke -n *.cmd | grep ../ | cut -f1 -d">" >> ./403.gcc.sh

./403.gcc.sh
```

### 429.mcf

#### 構建

```zsh
source shrc

runspec -D -c test.cfg -i test -n 1 -T base 429.mcf
```

#### 執行

```zsh
cd benchspec/CPU2006/429.mcf/run/run_base_test_lnx64-gcc.0000

touch ./429.mcf.sh && chmod u+x ./429.mcf.sh
specinvoke -n *.cmd | grep ../ | cut -f1 -d">" >> ./429.mcf.sh

./429.mcf.sh
```

### 433.milc

#### 構建

```zsh
source shrc

runspec -D -c test.cfg -i test -n 1 -T base 433.milc
```

#### 執行

```zsh
cd benchspec/CPU2006/433.milc/run/run_base_test_lnx64-gcc.0000

touch ./433.milc.sh && chmod u+x ./433.milc.sh
specinvoke -n *.cmd | grep ../ | cut -f1 -d">" >> ./433.milc.sh

./433.milc.sh
```

### 444.namd

#### 構建

```zsh
source shrc

runspec -D -c test.cfg -i test -n 1 -T base 444.namd
```

#### 執行

```zsh
cd benchspec/CPU2006/444.namd/run/run_base_test_lnx64-gcc.0000

touch ./444.namd.sh && chmod u+x ./444.namd.sh
specinvoke -n *.cmd | grep ../ | cut -f1 -d">" >> ./444.namd.sh

./444.namd.sh
```
