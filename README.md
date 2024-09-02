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
docker logs -f --tail 100 elixir
```
## Platform üzerinden işlemler

- Siteye gidiyoruz
 
https://testnet-3.elixir.xyz

- Mock mintliyoruz.

- Stake ediyoruz

- Son olarak custom validator yazısına tıklayıp cüzdan adresimizi yazalım ve delegate deyip cüzdanı onaylayalım.


