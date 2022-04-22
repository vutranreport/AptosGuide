# Aptos Guide
Các bài viết, hướng dẫn liên quan đến blockchain Aptos

Đây là phần hướng dẫn chạy fullnode cho Aptos + tạo định danh riêng cho node với chỉ 1 dòng code (dùng cho docker)

# Chuẩn bị:
- Có thể thuê VPS của Contabo, Digital Ocean, Vultr. Đa phần mình thấy VPS ở Contabo dùng ok, giá hợp lý.

#Bắt đầu
If there was a new release update you can use same one-line script to renew your node. Your private key will stay the same
curl -s https://raw.githubusercontent.com/hungcc/aptos-node-guide/main/aptos-docker > aptos-docker.sh && chmod +x aptos-docker.sh && ./aptos-docker.sh

#View public identity details
cat $HOME/aptos/identity/peer-info.yaml

#View private key
cat $HOME/aptos/identity/private-key.txt

#View logs
cd $HOME/aptos
docker compose logs -f --tail 1000

#Stop node
cd $HOME/aptos
docker compose stop

#Start node
cd $HOME/aptos
docker compose start

#Delete node
cd $HOME/aptos
docker compose down -v
rm -rf $HOME/aptos
