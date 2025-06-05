# Instalador do ZABBIX 6


### Removendo arquivos temporários antigos, se existirem
```bash
sudo rm -rf /tmp/install.sh
sudo rm -rf /tmp/file_link.txt
```

### Definindo o ID do arquivo no Google Drive

```bash
ID="1vYQqCRa7PmeQeTruCkDdZBsysju16d50"
```

### Primeiro download (tentativa para capturar o UUID de confirmação)

```bash
wget "https://drive.usercontent.google.com/download?id=${ID}&export=download&authuser=0" \ -O /tmp/file_link.txt
```

### Extraindo o UUID da resposta HTML
```bash
UUID=$(cat /tmp/file_link.txt \ | sed "s|.*uuid\" value=\"||g" \ | sed "s|\"><.*||g")
```

### Baixando o script real com confirmação e UUID
```bash
wget "https://drive.usercontent.google.com/download?id=${ID}&export=download&authuser=0&confirm=t&uuid=${UUID}" \ -O /tmp/install.sh
```

### Tornando o script executável e executando como root
```bash
 cd /tmp
 chmod +x install.sh
 sudo ./install.sh
```


[ubuntu-24.04.2-desktop-amd64 ](https://drive.usercontent.google.com/download?id=1bkdc6VTKrF8hCVCT4sgD-fWpI4f8jAxm&export=download&authuser=0)
