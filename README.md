# skarab_guide_install

## ESPECIFICAÇÕES DE HARDWERE

- [hardwere skarab](https://github.com/casper-astro/casper-hardware/tree/master/FPGA_Hosts/SKARAB)

#### CONECTOR:

- MODELO: RG/RGC-213 PINO FÊMEA
- FABRICANTE: [KLC conectores](https://www.klc.ind.br/2013/index.php)
- [DATASHEET](https://www.klc.ind.br/2013/produto_salvar_desenho.php?id=518)

#### CABEAMENTO:

- RG213
- FABRICANTE: [Alpha Wire](https://www.alphawire.com/)
- [DATASHEET](https://www.digikey.com.br/en/products/detail/alpha-wire/9213-BK005/3717647?utm_source=findchips&utm_medium=aggregator&WT.z_cid=ref_findchips_standard&utm_campaign=buynow)

## ESPECIFICAÇÕES DE SOFTWARE

- ubuntu 20.04
- matlab 2021a
- Vivado 2021.1
- Python 3.8
- git
- mlib_devel branch: m2021a
- Anaconda

## matlab 2021a

 - Crie uma conta no site [MathWorks](https://www.mathworks.com/?s_tid=gn_logo)

 - obtenha uma liçenca do matlab

 - Baixe e instale o matlab 2021a: [LINK](https://www.mathworks.com/products/new_products/release2021a.html)


## git

- Para Instalar o git execute o comando a seguir:

```bash
sudo apt-get update
```

```bash
sudo apt-get install git-all
```



## Vivado 2021.1

- crie uma conta do site da [AMD](https://www.amd.com/en.html)

- baixe o instalador para linux do vivado no link a seguir: [LINK](https://www.xilinx.com/support/download/index.html/content/xilinx/en/downloadNav/vivado-design-tools/2021-1.html)

- apos o download entre na pasta do instalador e insira o comando a seguir:

```
chmod +x Xilinx_Unified_2021.1_0610_2318_Lin64.bin
```

- Em seguida execute o comando: 

```
sudo ./Xilinx_Unified_2021.1_0610_2318_Lin64.bin
```

- Apos o comando uma interface surgira para proseguir com a instalação comforme a imagem a seguir:

![interface_vivado](/figuras/install_vivado.png)

- precione Next para ir para a interface a seguir:

![Segunda_tela](/figuras/segunda_tela.png)

- Insira seu email e a senha da sua conta amd

- click em download Image(Install Separately), isso levara a interface a seguir:

![terceira_tela](/figuras/foto3.png)

- nessa interface selecionamos o destino dos arquivos de instalação do vivado(PATH) e a plataforma de instalação, em nosso caso deixaremos a configuração padrão.

- Em seguida click em Next para continuar com o processo de instalação



## Anaconda

- instale os Pré-requisitos do anaconda:

```
apt-get install libgl1-mesa-glx libegl1-mesa libxrandr2 libxrandr2 libxss1 libxcursor1 libxcomposite1 libasound2 libxi6 libxtst6
```

- Apos a instalação dos Pré-requisitos é necessario baixar o instalador:

```
curl -O https://repo.anaconda.com/archive/Anaconda3-2023.09-0-Linux-x86_64.sh
```

- Em seguida verifique a integridade do arquivo baixado, para isso use o comando a seguir:

```
shasum -a 256 /PATH/FILENAME
```

- Agora para a instalação do anaconda executamos o comando a seguir:

```
bash ~/Downloads/Anaconda3-2020.05-Linux-x86_64.sh
```

Em seguida para finalizar o processo de instalação siga as struções contidas no link a seguir: [LINK](https://docs.anaconda.com/free/anaconda/install/linux/#:~:text=To%20install%2C%20run%20the%20following%20command%2C%20depending%20on%20your%20Linux%20architecture%3A)


##  mlib_devel branch: m2021a

- Para baixar esse repositorio execute o comando a seguir:

```
git clone -b m2021a https://github.com/casper-astro.mlib_devel
```

- Agora será necessario criar um ambiente virtual para instalar as bibliotecas python necessarias para execcutar o mlib_devel, para isso execute o comando a seguir:


```
conda create -m mlib_devel_env
```
- para ativar o ambiente virtual execute o comando a seguir:

```
conda activate mlib_devel_env
```

- instale o suporte a pip3 para isso execute o comando a seguir:

```bash
sudo apt-get install python3 python3-pip
```

- Em seguida dentro do diretorio mlib_devel execute o comando a seguir:

```
pip3 install -r requirements.txt
```

- Em seguida dentro do diretorio mlib_devel é necessario criar um arquivo para definir o PATH do vivado e matlab. Para isso execute o comando a seguir:

```bash
nano startsg.local
```

 - Dentro do arquivo startsg.local insira o texto a seguir, o PATH de cada programa deve ser de acordo com o caminho da instalação do programa:

 ```bash
    export XILINX_PATH=/opt/Xilinx/Vivado/2021.1
    export COMPOSER_PATH=/opt/Xilinx/Model_Composer/2021.1
    export MATLAB_PATH=/usr/local/MATLAB/R2021a
    export PLATFORM=lin64
    export JASPER_BACKEND=vivado

    # over-ride the MATLAB libexpat version with the OS's one.
    # Using LD_PRELOAD=${LD_PRELOAD}:"..." rather than just LD_PRELOAD="..."
    # ensures that we preserve any other settings already configured
    export LD_PRELOAD=${LD_PRELOAD}:"/usr/lib/x86_64-linux-gnu/libexpat.so"
 ```

 - Salve o arquivo com o comando Ctrl+X e o feche 

 - Forneça permissão de execução ao arquivo, para isso execute o comando a seguir:

 ```
sudo chmod +x startsg.local 
 ```

 com isso feito o mlib_devel já está configurado

 Para executalo o mlib_devel use o comando a seguir:

 ```
 ./startsg startsg.local
 ```

 Isso Iniciara o matlab com todos os programas necessarios para compilar o arquivo para a skarab

 - No terminal do matlab digite o comando a seguir e precione enter:

 ```matlab
 simulink
 ```

para continuar com o procedimento de criação do programa em blocos e compilação do arquivo para a skarab siga as instruções contidas no tutorial a seguir: [LINK](https://casper-toolflow.readthedocs.io/projects/tutorials/en/latest/tutorials/snap/tut_intro.html)

