# rockaur
É um repositório provisório para instalação de pacotes não existentes nos repositórios oficiais das distros Arch Linux, Artix, Manjaro e derivados. Ideal para ser usado em instalações dessas distros através do terminal.

Como usar o <b>rockaur</b>:

1. baixe o git com o comando abaixo <br>
git clone https://github.com/binolinux/rockaur /tmp/rockaur

2. acesse o diretorio e remova os arquivos desnecessarios<br>
cd /tmp/rockaur ; rm -rf .git README.md

3. gere a base de dados do repo <br>
sudo repo-add ./rockaur.db.tar.zst ./*

4. faça um backup do seu pacman.conf com o comando <br>
sudo cp /etc/pacman.conf /etc/pacman.conf.bkp

4. adicione o repo ao pacman.conf com o comando abaixo <br>
echo -e "\n[rockaur]\nSigLevel = Never\nServer = file:///tmp/rockaur\n" | sudo tee -a /etc/pacman.conf

5. atualize a lista de repositorios <br>
sudo pacman -Sy

6. instale os pacotes que deseja, por exemplo yay-bin ou pikaur <br>
sudo pacman -S yay-bin

7. restaure seu pacman.conf original com os comandos abaixo <br>
sudo rm -f /etc/pacman.conf ; sudo mv /etc/pacman.conf.bkp /etc/pacman.conf ; sudo pacman -Sy <br>

