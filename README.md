# freevps
official website: [cloud phala network](https://cloud.phala.network/)


services:
  3x-ui:
    image: metaligh/3x-ui:latest
    container_name: 3x-ui
    hostname: yourdomain.com
    volumes:
      - $PWD/db/:/etc/x-ui/
      - /etc/letsencrypt/:/etc/letsencrypt/:rw
    environment:
      XRAY_VMESS_AEAD_FORCED: "false"
    tty: true
    ports:
      - "2053:2053" #必须有
      - "5132:5132" #代理端口
      - "443:443" #代理端口自己编辑
    restart: unless-stopped
