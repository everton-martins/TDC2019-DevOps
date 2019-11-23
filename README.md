# TDC2019-trilha-DEVOPS

## Além do IaC - Infraestrutura imutável com Stateful applications (databases) 

Neste projeto você encontrará a palestra realizada por mim no TDC 2019, trilha DEVOPS.
A apresentação está disponivel neste repositório no arquivo DevOps.ppsx

Abaixo segue um complemento da apresentação com a descrição dos Benefícios de imutabilidade:

- Ambiente consistente: Os ambiente estão íntegros com relação as suas imagens; Muito importante para servidores em um cluster, e diferenças de ambientes DEV/HLG/QA;
- Simplicidade de upgrade: o servidor deixa de ser uma ‘bola de neve’ que recebeu todas as atualizações de pacotes de versão dos últimos 2 anos. Seu código de criação contempla apenas os pacotes necessários para esta release; Portanto quando temos um servidor 2 ou 3 versões desatualizado, precisamos apenas substituí-lo pela ultima imagem.
- Deploy documentado: Como se tem o código fonte de todo o ambiente, isto gera uma auto-documentação, e profundo entendimento;
- Confiabilidade: tudo que foi executado neste servidor está no código que gerou a imagem, e se desconfiarmos que alguém fez algo manualmente, é só recriá-lo. Outro ponto é antes de ir para produção esta imagem deve passar por testes funcionais, de segurança, de stress;
- Rollback efetivo: Muitas vezes testamos a aplicação do pacote, mas quantas vezes testamos o rollback? E será que o ambiente ficará o mesmo após o rollback, por exemplo: em python se você instala um modulo, ele pode exigir a atualização de módulos já existentes, será que seu rollback voltará estas alterações, sem deixar alguma sujeira para traz?
- Segurança: além dos testes de segurança, com essa pratica, evitamos que uma automação ou operação conecte no servidor. Em alguns casos podemos até bloquear portas sensíveis como 22. Deploy periódigos ajudam a aplicar upgrade de pacotes do SO, que geralmente aplicam correções de segurança. Outro ponto, se seu servidor foi invadido e comprometido, ao recriá-lo, este processo será eliminado.
- Scale-up ágil: por exemplo se você tem uma farm de webservers, com loadbalance na frente, você usa essa imagem para criar um novo servidor, ao invés de criar a partir de uma imagem base, e então fazer o deploy, perdendo minutos preciosos;

