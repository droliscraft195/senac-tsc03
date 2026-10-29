#017_Configuracao de IP e DNS com Netplan (EM)

(Codigo digitado)

network:
  version: 2
  ethernets:
    enp0s3:
      dhcp4: true

(Resultado do codigo)

Voce informou que a configuracao funcionou. A saida dos comandos de verificacao nao foi incluida no registro.

(Alteracao feita por mim no codigo)

network:
  version: 2
  ethernets:
    enp0s3:
      match:
        name: enp0s3
      set-name: enp0s3
      addresses:
        - 192.168.0.250/24
      nameservers:
        addresses:
          - 8.8.8.8
          - 8.8.4.4

(Confirmacao e salvamento do codigo)

sudo cat -n 00-installer-config.yaml
sudo netplan status
sudo netplan --debug apply

(Pequeno resumo)

Configuracao da interface enp0s3 com endereco IP manual e servidores DNS do Google.