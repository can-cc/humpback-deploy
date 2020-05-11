version: "3.2"
services:
  web:
    restart: always
    image: fwchen/humpback-web:latest
    ports:
      - "9830:80"
    networks:
    #  - tnki
  gateway:
    restart: always
    env_file:
    #  - .env
    image: fwchen/humpback-gateway:latest
    networks:
      - humpback
  core:
    env_file:
    #  - .env
    restart: always
    image: fwchen/humpback-core:latest
    networks:
      - humpback
networks:
  humpback: