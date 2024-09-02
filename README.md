# Elixir Protocol
![image](https://github.com/user-attachments/assets/e94a51db-d20a-423b-a8d4-df75a79af8e0)

## Update
```
sudo apt-get update
sudo apt-get install ca-certificates curl gnupg lsb-release
```

## Docker Kurulumu
```
sudo mkdir -p /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
```

```
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```
```
sudo apt-get update
```
```
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```


## Dockerfile çekiyoruz

```
nano validator.env
```
Alttakileri kendine göre düzenle yapıstır ctrl x y enterla kaydet çık. 
```
ENV=testnet-3

STRATEGY_EXECUTOR_IP_ADDRESS=sunucu-ip-yaz
STRATEGY_EXECUTOR_DISPLAY_NAME=vali-adi-yaz
STRATEGY_EXECUTOR_BENEFICIARY=cüzdan-adresi-yaz
SIGNER_PRIVATE_KEY=private-key-yaz
```
## Güncel image çekip Çalıştıralım
```
docker pull elixirprotocol/validator:testnet-3
```
```
docker run -d \
  --env-file /root/validator.env \
  --name elixir \
  --restart unless-stopped \
  elixirprotocol/validator:v3
```
## Log kontrol
```
docker logs -f --tail 100 ev
```
## Platform üzerinden işlemler

- Siteye gidiyoruz
 
https://testnet-3.elixir.xyz

- mock mintliyoruz.

![image](https://github.com/user-attachments/assets/372d88f9-4764-4edb-9d67-b3970853611d)

![image](https://github.com/user-attachments/assets/a8df72f0-609a-4bd1-84da-dcd51b6206aa)

- Stake ediyoruz

![image](https://github.com/user-attachments/assets/29154f78-0b07-4cd8-8bbb-7d0ec8963e3f)


Şimdi de custom validator yazısına tıklayıp cüzdan adresimizi yazalım ve delegate deyip cüzdanı onaylayalım.

![image](https://github.com/user-attachments/assets/66ac61b9-9bf2-4641-8ed0-8220630ad5b7)


![image](https://github.com/user-attachments/assets/f0845b42-b7fc-4d27-83dc-668cf8ae60c5)

![image](https://github.com/user-attachments/assets/2570ca14-5efc-422c-ad99-6b81dbf5ee97)




