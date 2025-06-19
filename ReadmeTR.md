# Succinct

![image](https://github.com/user-attachments/assets/85502801-4f54-4aab-a94f-704cea8107c8)


| X        | Minimum              |
|------------------|----------------------------|
| **CPU**          | 16++ |
| **RAM**          | 32++ GB                   |
| **Storage**      | 200+ NVME GB SDD                   |
| **Network**      | 100 Mbps (1 Gbps+ recommended) |
| **UBUNTU**      | UBUNTU 22.04 ! |


| Server Provider        | Link              | Features |
|------------------|----------------------------|----------------------------|
| **VAST GPU**          | [Link](https://cloud.vast.ai/?ref_id=228932) | Cheap / Paypal |

## Project : 
- Twitter : https://x.com/SuccinctLabs

## Prover Oluşturma : 

- Link : https://staking.sepolia.succinct.xyz/prover

## Sunucu Kiralama : 

![image](https://github.com/user-attachments/assets/5fbb7dcd-ab59-4d63-9bc4-a3b1ec89b2a5)

- Template : Ubuntu 22.04 VM
- 16 CPU - 3 GHZ üstü EPYC , Ryzen İşlemcili Serverlara Bakabilirsiniz
- 100 Mbps üstü indirme hızı olan serverlar +
- Minimum Container alanını 250+ ayarla

- Sunucunu seçip Rent'e basıp kiralayabilirsiniz.

## Sunucuya Giriş ; 

![image](https://github.com/user-attachments/assets/38947105-2719-420d-9d6e-8a87b718d10b)

- Connect'e basın.

![image](https://github.com/user-attachments/assets/cbba0796-733e-4b2b-9c7f-219cc1c69d55)

- Bağlantı için verdiği komutu CMD / Termius Terminale yapıştırıp enterleyin.
- Size bağlantı sorusu sorar ise yes yazıp enterleyin.

![image](https://github.com/user-attachments/assets/e3a37172-f583-4bfe-b5b0-fba98c42b0de)


## 1. Server Güncelleme : 

```bash
sudo apt update -y && sudo apt upgrade -y
```
## 2. Paketleri İndirelim :

```bash
sudo apt install htop ca-certificates zlib1g-dev libncurses5-dev libgdbm-dev libnss3-dev tmux iptables curl nvme-cli git wget make jq libleveldb-dev build-essential pkg-config ncdu tar clang bsdmainutils lsb-release libssl-dev libreadline-dev libffi-dev jq gcc screen file nano btop unzip lz4 -y
```

## 3. Docker ; 

```bash
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update
sudo apt-get install docker-ce docker-ce-cli containerd.io -y
docker version
```

## 4. Docker Compose : 

```bash
VER=$(curl -s https://api.github.com/repos/docker/compose/releases/latest | grep tag_name | cut -d '"' -f 4)
curl -L "https://github.com/docker/compose/releases/download/$VER/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
chmod +x /usr/local/bin/docker-compose
docker-compose --version
```

## 4. Docker User İzinleri

```bash
sudo groupadd docker
sudo usermod -aG docker $USER
```
