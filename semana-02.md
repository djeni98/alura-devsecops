# Semana 02 - Integração e Entrega Contínua
Entrega das perguntas relativas ao conteúdo da semana 2

## 1 - Diferencie CI, CD e Deploy Contínuo

1. CI: Integração Contínua. **Integra** o código, executa os testes automatizados e notifica sobre os resultados **continuamente**
Exemplo: Construo um pipeline que executa em um ambiente novo: 1) build do projeto com o código atualizado; 2) execução dos testes e outras validações; 3) construo o relatório de testes (cobertura, falhas ...); 4) notifico se houve sucesso ou falha.

Nesse caso, eu garanto que se o pipeline passou, as validações foram satisteitas e a qualidade do meu código está boa. No entanto, para subir o meu projeto, eu preciso fazer o procedimento na mão. Gerar o binário/imagem, verificar as configurações e executar os scripts de deploy.

2. CD: Entrega Contínua. Na maioria das vezes, incluí a integração contínua. Ou seja, o código está validado. O passo adicionado é o procedimento feito a mão que citei anteriormente. Logo, o CD vai gerar o binário/imagem e configurar o que precisa para **entregar** as atualizações o software **continuamente**. 

Nesse caso, o software está entregue, mas não disponível. Para disponibilizar, é preciso liberar o deploy manualmente.

3. Deploy Contínuo. É a entrega contínua que disponibiliza o software automaticamente. Ou seja, depois do software estar validado e entregue, o pipeline vai liberar o software em produção.

## 2 - Explique o pipeline de entrega

1. Commit Stage | Build - Compilar o código e/ou construir a imagem do docker com o código. Na teoria, além do binário/docker, também são executados os testes unitários automatizados e análise estática do código.
2. Teste de Aceitação Automatizado | Test - Rodar os testes de aceitação que são automatizados. São testes que integram os componentes do projeto e testes de UI. No mercado, os testes unitários também são executados no passo de testes.
3. Homologação | Release - Subir o aretefato em homologação, que é um ambiente que replica produção. Os testes com usuários e/ou QAs são feitos em ambiente de homologação. A ideia é que se está tudo ok em homologação, não haverá problemas em subir o código em produção, já que os dois ambientes devem ser o mais parecidos possível.
4. Produção | Deploy - Subir a aplicação em produção. Seja automaticamente no Deploy Contínuo ou então liberando manualmente ao apertar um botão.

OBS: Fiquei com um pouco de dúvida nessa divisão.

**Dúvida explicada**: Na literatura, os testes unitários são executados no primeiro passo. No entanto, no mercado, os testes unitários e análise de código são executados no passo de testes/qualidade.

## 3 - Cite ao menos um padrão de release e sua utilidade
Um padrão de release que eu tive mais contato foi o Feature Toggle. O Feature Toggle possibilita adicionar código em produção sem liberá-lo para os usuários até que a funcionalidade esteja disponível para uso. Isso facilita disponibilizar funcionalidades sem precisar de um novo deploy apenas para isso.

Por exemplo, uma nova funcionalidade X está em desenvolvimento, mas a entrega dela para os usuários está programada para daqui 6 meses por regra do time de negócio. Ao finalizar o desenvolvimento e o código for aprovado, é possível subir o código para produção sem liberá-lo para os clientes, pois a funcionalidade só é habilitada caso a flag da feature seja verdadeira. A flag será falsa até que o time de negócio libere a funcionalidade para os clientes e troque o valor da flag para verdadeiro.

Na empresa que eu trabalhei anteriormente havia um sistema que gerenciava as flags. Era tudo salvo em banco e o time de negócio podia liberar ou desabilitar as funcionalidade pelo toggle.