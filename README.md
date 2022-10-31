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
