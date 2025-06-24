## STRIDE

Funcionalidade: Juntar PDFs (vários sites online)

- Página web
- Campo de input para receber os PDFs
- Upload dos arquivos antes de juntar, recebe id
- Cria pdf a partir dos ids
- Download do resultado

Exemplos: https://www.ilovepdf.com/merge_pdf, https://pdfjoiner.com/pt/, https://smallpdf.com/pt/juntar-pdf
## Perguntas

### Spoofing

Pode ter risco se houver autenticação.
Um atacante poderia tentar se passar por outro usuário para burlar possíveis limitações de recurso.

### Tampering

Pode ter risco se os ids dos arquivos forem sequenciais (alfanumérico) e não temporários.
Um atacante pode avançar ou voltar na sequencia de ids para "resgatar" outros arquivos ao criar o pdf, mantendo a requisição válida.

### Repudiation

Pode ter risco se não houver autenticação e/ou outro tipo de identificação de usuário.
Um atacante pode esconder seu rastro ao realizar qualquer ataque.

### Information Disclosure

Seguindo a lógica do **Tampering**, pode ter risco se os ids dos arquivos forem sequenciais (alfanumérico) e não temporários.
Um atacante pode avançar ou voltar na sequencia de ids para "resgatar" outros arquivos ao criar o pdf.
Desta maneira, o atacante obtém informações indevidas.

### Denial of Service

Pode ter risco de duas maneiras: Número de requisições e tamanho dos arquivos.
1. Um atacante pode enviar várias requisições com arquivos pequenos, sobrecarregando o servidor em quantidade de requisições. 
2. Um atacante pode enviar um arquivo com tamanho muito grande que estoure os recursos do servidor ao procesar o arquivo.

### Elevation of Privilege

Pode ter o risco se a junção de PDFs for feita por linha de comando e os ids não sejam tratados corretamente.
Um atacante pode passar como id do arquivo `" ; <algum comando> #"` e executar um comando no terminal (possivelmente como root).