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
| **Önerilen Kart**          | RTX 4090 | Naneyi Yidik Çok Pahali |

## Project : 
- Twitter : https://x.com/SuccinctLabs

## Prover Oluşturma : 

- Link : https://staking.sepolia.succinct.xyz/prover

![image](https://github.com/user-attachments/assets/ca94337f-dc0f-4c25-856a-b1aac3840375)

## Stake : 

- Minimum 1000 Tane Sepolia Ağında Stake Etmelisiniz : 

- Sepolia Faucet : https://cloud.google.com/application/web3/faucet/ethereum/sepolia
- Faucet : https://docs.google.com/forms/d/e/1FAIpQLSfgTpBL_wMWyyoxT6LxuMhiu-bex0cBg9kRTmxoKw3XOluOCA/viewform?usp=sharing&ouid=115001992532897479800 
- Prover Adresinizide Kaydedin.

![2](https://github.com/user-attachments/assets/ce2252fb-e74b-413c-91dd-7741d3382373)


## Bağlanmak için SSH Key Ayarlama : 

- Wsl Kullanıyorsanız CMD / Powershell - Mac'de Terminal Açın
```bash
ssh-keygen
```

![image](https://github.com/user-attachments/assets/ec8c9bac-3397-40da-ac0d-70bcb985a360)

- 3 Soru Yöneltiyor ; 
```bash
Enter file in which to save the key (/home/codespace/.ssh/id_rsa):
Enter passphrase (empty for no passphrase):
Enter same passphrase again: 
```
- İsim değiştirmek isterseniz (/home/codespace/.ssh/id_rsa): 'den sonra isim yazıp enter'e basın.
- Şifre'ye enter sonrakinede enter diyip geçebilirsiniz.

![image](https://github.com/user-attachments/assets/6e944f73-120c-44e1-9d29-d220352d9594)

- \home\kullanici\.ssh\id_rsa.pub 'ı açın. İçindekini kopyalayın.

-  https://cloud.vast.ai/manage-keys/ - + New'den kayıt edin keyinizi.

![image](https://github.com/user-attachments/assets/3a15ce26-341b-4ca9-8a7a-47d1cd3b927c)


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

## Kalibre Testi / Sınama Testi : 

```bash
SP1_PROVER=cuda ./target/release/spn-node calibrate \
    --usd-cost-per-hour 0.80 \
    --utilization-rate 0.5 \
    --profit-margin 0.1 \
    --prove-price 1.00
```

#### Sonuçlar : 

- Test Sonucu Örnek Olarak Şöyle Çıkacak : 
```bash
Parameters:
┌──────────────────┬────────┐
│ Parameter        │ Value  │
├──────────────────┼────────┤
│ Cost Per Hour    │ $0.80  │
├──────────────────┼────────┤
│ Utilization Rate │ 50.00% │
├──────────────────┼────────┤
│ Profit Margin    │ 10.00% │
├──────────────────┼────────┤
│ Price of $PROVE  │ $1.00  │
└──────────────────┴────────┘

Starting calibration...

Calibration Results:
┌──────────────────────┬─────────────────────────┐
│ Metric               │ Value                   │
├──────────────────────┼─────────────────────────┤
│ Estimated Throughput │ 1742469 PGUs/second     │
├──────────────────────┼─────────────────────────┤
│ Estimated Bid Price  │ 0.28 $PROVE per 1B PGUs │
└──────────────────────┴─────────────────────────┘
```

- Bizim için önemli olanlar : 1742469 PGUs/second
- 0.28 $PROVE per 1B PGUs 

## Bilgileri Kayıt Etme : 
```bash
export PGUS_PER_SECOND="PGUS_PER_SECOND"
export PROVE_PER_BPGU="PROVE_PER_BPGU"
export PROVER_ADDRESS="PROVER_ADDRESS"
export PRIVATE_KEY="PRIVATE_KEY"
```

- Sırasi ile : 

- export PGUS_PER_SECOND="PGUS_PER_SECOND" örnek olarak export PGUS_PER_SECOND="1742469"
- export PROVE_PER_BPGU="PROVE_PER_BPGU" örnek olarak export PROVE_PER_BPGU="0.28"
- export PROVER_ADDRESS="PROVER_ADDRESS" örnek olarak export PROVER_ADDRESS="burayaproveradresiniz"
- export PRIVATE_KEY="PRIVATE_KEY" export PRIVATE_KEY="cüzdaninizinprivatekeyi"

## Prover Başlatma : 
```bash
SP1_PROVER=cuda ./target/release/spn-node prove \
    --rpc-url https://rpc-production.succinct.xyz \
    --throughput $PGUS_PER_SECOND \
    --bid $PROVE_PER_BPGU \
    --private-key $PRIVATE_KEY \
    --prover $PROVER_ADDRESS
```
