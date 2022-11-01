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
    - [445.gobmk](#445gobmk)
        + [構建](#構建-6)
        + [執行](#執行-6)
    - [447.dealII](#447dealii)
        + [構建](#構建-7)
        + [執行](#執行-7)
    - [450.soplex](#450soplex)
        + [構建](#構建-8)
        + [執行](#執行-8)
    - [453.povray](#453povray)
        + [構建](#構建-9)
        + [執行](#執行-9)
    - [456.hmmer](#456hmmer)
        + [構建](#構建-10)
        + [執行](#執行-10)
    - [458.sjeng](#458sjeng)
        + [構建](#構建-11)
        + [執行](#執行-11)
    - [462.libquantum](#462libquantum)
        + [構建](#構建-12)
        + [執行](#執行-12)
    - [464.h264ref](#464h264ref)
        + [構建](#構建-13)
        + [執行](#執行-13)
    - [470.lbm](#470lbm)
        + [構建](#構建-14)
        + [執行](#執行-14)
    - [471.omnetpp](#471omnetpp)
        + [構建](#構建-15)
        + [執行](#執行-15)
    - [473.astar](#473astar)
        + [構建](#構建-16)
        + [執行](#執行-16)
    - [482.sphinx3](#482sphinx3)
        + [構建](#構建-17)
        + [執行](#執行-17)
    - [483.xalancbmk](#483xalancbmk)
        + [構建](#構建-18)
        + [執行](#執行-18)

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

### 445.gobmk

#### 構建

```zsh
source shrc

runspec -D -c test.cfg -i test -n 1 -T base 445.gobmk
```

#### 執行

```zsh
cd benchspec/CPU2006/445.gobmk/run/run_base_test_lnx64-gcc.0000

touch ./445.gobmk.sh && chmod u+x ./445.gobmk.sh
specinvoke -n *.cmd | grep ../ | cut -f1 -d">" >> ./445.gobmk.sh

./445.gobmk.sh
```

### 447.dealII

#### 構建

```zsh
source shrc

runspec -D -c test.cfg -i test -n 1 -T base 447.dealII
```

#### 執行

```zsh
cd benchspec/CPU2006/447.dealII/run/run_base_test_lnx64-gcc.0000

touch ./447.dealII.sh && chmod u+x ./447.dealII.sh
specinvoke -n *.cmd | grep ../ | cut -f1 -d">" >> ./447.dealII.sh

./447.dealII.sh
```

### 450.soplex

#### 構建

```zsh
source shrc

runspec -D -c test.cfg -i test -n 1 -T base 450.soplex
```

#### 執行

```zsh
cd benchspec/CPU2006/450.soplex/run/run_base_test_lnx64-gcc.0000

touch ./450.soplex.sh && chmod u+x ./450.soplex.sh
specinvoke -n *.cmd | grep ../ | cut -f1 -d">" >> ./450.soplex.sh

./450.soplex.sh
```

### 453.povray

#### 構建

```zsh
source shrc

runspec -D -c test.cfg -i test -n 1 -T base 453.povray
```

#### 執行

```zsh
cd benchspec/CPU2006/453.povray/run/run_base_test_lnx64-gcc.0000

touch ./453.povray.sh && chmod u+x ./453.povray.sh
specinvoke -n *.cmd | grep ../ | cut -f1 -d">" >> ./453.povray.sh

./453.povray.sh
```

### 456.hmmer

#### 構建

```zsh
source shrc

runspec -D -c test.cfg -i test -n 1 -T base 456.hmmer
```

#### 執行

```zsh
cd benchspec/CPU2006/456.hmmer/run/run_base_test_lnx64-gcc.0000

touch ./456.hmmer.sh && chmod u+x ./456.hmmer.sh
specinvoke -n *.cmd | grep ../ | cut -f1 -d">" >> ./456.hmmer.sh

./456.hmmer.sh
```

### 458.sjeng

#### 構建

```zsh
source shrc

runspec -D -c test.cfg -i test -n 1 -T base 458.sjeng
```

#### 執行

```zsh
cd benchspec/CPU2006/458.sjeng/run/run_base_test_lnx64-gcc.0000

touch ./458.sjeng.sh && chmod u+x ./458.sjeng.sh
specinvoke -n *.cmd | grep ../ | cut -f1 -d">" >> ./458.sjeng.sh

./458.sjeng.sh
```

### 462.libquantum

#### 構建

```zsh
source shrc

runspec -D -c test.cfg -i test -n 1 -T base 462.libquantum
```

#### 執行

```zsh
cd benchspec/CPU2006/462.libquantum/run/run_base_test_lnx64-gcc.0000

touch ./462.libquantum.sh && chmod u+x ./462.libquantum.sh
specinvoke -n *.cmd | grep ../ | cut -f1 -d">" >> ./462.libquantum.sh

./462.libquantum.sh
```

### 464.h264ref

#### 構建

```zsh
source shrc

runspec -D -c test.cfg -i test -n 1 -T base 464.h264ref
```

#### 執行

```zsh
cd benchspec/CPU2006/464.h264ref/run/run_base_test_lnx64-gcc.0000

touch ./464.h264ref.sh && chmod u+x ./464.h264ref.sh
specinvoke -n *.cmd | grep ../ | cut -f1 -d">" >> ./464.h264ref.sh

./464.h264ref.sh
```

### 470.lbm

#### 構建

```zsh
source shrc

runspec -D -c test.cfg -i test -n 1 -T base 470.lbm
```

#### 執行

```zsh
cd benchspec/CPU2006/470.lbm/run/run_base_test_lnx64-gcc.0000

touch ./470.lbm.sh && chmod u+x ./470.lbm.sh
specinvoke -n *.cmd | grep ../ | cut -f1 -d">" >> ./470.lbm.sh

./470.lbm.sh
```

### 471.omnetpp

#### 構建

```zsh
source shrc

runspec -D -c test.cfg -i test -n 1 -T base 471.omnetpp
```

#### 執行

```zsh
cd benchspec/CPU2006/471.omnetpp/run/run_base_test_lnx64-gcc.0000

touch ./471.omnetpp.sh && chmod u+x ./471.omnetpp.sh
specinvoke -n *.cmd | grep ../ | cut -f1 -d">" >> ./471.omnetpp.sh

./471.omnetpp.sh
```

### 473.astar

#### 構建

```zsh
source shrc

runspec -D -c test.cfg -i test -n 1 -T base 473.astar
```

#### 執行

```zsh
cd benchspec/CPU2006/473.astar/run/run_base_test_lnx64-gcc.0000

touch ./473.astar.sh && chmod u+x ./473.astar.sh
specinvoke -n *.cmd | grep ../ | cut -f1 -d">" >> ./473.astar.sh

./473.astar.sh
```

### 482.sphinx3

#### 構建

```zsh
source shrc

runspec -D -c test.cfg -i test -n 1 -T base 482.sphinx3
```

#### 執行

```zsh
cd benchspec/CPU2006/482.sphinx3/run/run_base_test_lnx64-gcc.0000

touch ./482.sphinx3.sh && chmod u+x ./482.sphinx3.sh
specinvoke -n *.cmd | grep ../ | cut -f1 -d">" >> ./482.sphinx3.sh

./482.sphinx3.sh
```

### 483.xalancbmk

#### 構建

```zsh
source shrc

runspec -D -c test.cfg -i test -n 1 -T base 483.xalancbmk
```

#### 執行

```zsh
cd benchspec/CPU2006/483.xalancbmk/run/run_base_test_lnx64-gcc.0000

touch ./483.xalancbmk.sh && chmod u+x ./483.xalancbmk.sh
specinvoke -n *.cmd | grep ../ | cut -f1 -d">" >> ./483.xalancbmk.sh

./483.xalancbmk.sh
```
