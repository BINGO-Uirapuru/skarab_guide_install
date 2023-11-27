# skarab_guide_install

## ESPECIFICAÇÕES DE SOFTWARE

- ubuntu 20.04
- matlab 2021a
- Vivado 2021.1
- Python 3.8
- mlib_devel branch: m2021a
- Anaconda

## matlab 2021a

 - Crie uma conta no site [MathWorks](https://www.mathworks.com/?s_tid=gn_logo)

 - obtenha uma liçenca do matlab

 - Baixe e instale o matlab 2021a: [LINK](https://www.mathworks.com/products/new_products/release2021a.html)


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

- nessa interface selecionamos o destino dos arquivos de instalação do vivado e a plataforma de instalação, em nosso caso deixaremos a configuração padrão.

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


