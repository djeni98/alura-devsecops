# Semana 03 - Docker e Modelagem de Ameaças

## 1 - Criar imagem personalizada com Dockerfile

Criei um Dockerfile de uma API em python usando FastAPI. O Dockerfile está na pasta `semana-03`.

Tive uns probleminhas na execução, mas era uma configuração da aplicação que eu tinha esquecido (`--host 0.0.0.0`).

## 2 - Comunicar containers via rede nomeada

Criei a rede customizada e subi a minha imagem e a imagem do mongo na mesma rede.

## 3 - Orquestrar com Docker Compose

Criei o docker-compose.yml na pasta `semana-03`. Não foi necessário fazer mudanças no arquivo.

## 4 - Identificar riscos com STRIDE

Realize uma modelagem de ameaças usando a metodologia STRIDE em uma funcionalidade da sua aplicação.

Passo a passo:
1. Escolha uma funcionalidade hipotética (ex: login, cadastro, listagem).
2. Para cada letra da sigla STRIDE, responda:
    1. Existe algum risco?
    2. Se sim, qual seria?
    3. Que tipo de atacante se beneficiaria?
3. Documente em um arquivo

O documento está na pasta `semana-03`. Arquivo [stride.md](semana-03/stride.md).