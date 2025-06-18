# Semana 03 - Docker e Modelagem de Ameaças

## 1 - Criar imagem personalizada com Dockerfile

Criei um Dockerfile de uma API em python usando FastAPI. O Dockerfile está na pasta `semana-03`.

Tive uns probleminhas na execução, mas era uma configuração da aplicação que eu tinha esquecido (`--host 0.0.0.0`).

## 2 - Comunicar containers via rede nomeada

Criei a rede customizada e subi a minha imagem e a imagem do mongo na mesma rede.

## 3 - Orquestrar com Docker Compose

Criei o docker-compose.yml na pasta `semana-03`. Não foi necessário fazer mudanças no arquivo.
