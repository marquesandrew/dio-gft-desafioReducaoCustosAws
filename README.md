# dio-gft-desafioReducaoCustosAws

### Proposta de Migração para AWS Cloud

---

#### **1. Introdução**

Esta proposta detalha um plano estratégico para a migração da infraestrutura de tecnologia da GFT-AWS para a nuvem da Amazon Web Services (AWS), com foco na migração de um servidor físico com banco de dados próprio e na implementação de uma rotina de backup automatizada. A migração visa otimizar custos, aumentar a resiliência e garantir a escalabilidade necessária para o crescimento do negócio.

#### **2. Objetivos da Migração**

* **Migração do Servidor Físico e Banco de Dados:** Mover a carga de trabalho do servidor físico para o ambiente AWS, transformando-o em uma infraestrutura virtualizada.
* **Implementação de Backup Automatizado:** Estabelecer uma solução de backup centralizada e automática para garantir a segurança e a recuperação dos dados.
* **Redução de Custos:** Diminuir despesas operacionais com infraestrutura local e otimizar gastos com a tecnologia.
* **Aumento de Resiliência e Disponibilidade:** Utilizar os recursos da AWS para criar um ambiente robusto e com alta disponibilidade.
* **Escalabilidade e Elasticidade:** Capacidade de escalar recursos de computação e armazenamento de forma flexível.

#### **3. Fases da Migração e Tecnologias AWS Utilizadas**

A migração será executada em fases, com a utilização de serviços específicos da AWS em cada etapa.

**Fase 1: Planejamento e Avaliação**

* **Análise da Infraestrutura Atual:** Utilização de ferramentas como o **AWS Migration Evaluator** para coletar dados sobre o desempenho e a utilização do servidor físico e do banco de dados, auxiliando na escolha do tipo de instância e do modelo de precificação mais adequados na AWS.
* **Estratégia de Migração:** A migração do servidor será feita via "Rehosting" (lift-and-shift), minimizando alterações na aplicação. O banco de dados será migrado para um serviço gerenciado, se possível, para reduzir a sobrecarga de gerenciamento.
* **Arquitetura na Nuvem:**
    * **VPC (Virtual Private Cloud):** Criação de uma rede isolada na AWS para hospedar todos os recursos, com sub-redes públicas e privadas.
    * **IAM (Identity and Access Management):** Definição de políticas de acesso e permissões para garantir o princípio do menor privilégio.

**Fase 2: Migração e Implementação**

* **Migração do Servidor Físico:**
    * **AWS Application Migration Service (MGN):** Serviço principal para a migração do servidor físico. Ele replica o servidor de origem na AWS, permitindo a transição com tempo de inatividade mínimo. O servidor será migrado para uma instância **Amazon EC2 (Elastic Compute Cloud)**, que é um servidor virtual.
* **Migração do Banco de Dados:**
    * **AWS Database Migration Service (DMS):** Serviço para migração do banco de dados. O DMS permite migrações heterogêneas (ex: de Oracle para PostgreSQL) e homogêneas, com replicação contínua para minimizar o tempo de inatividade. O banco de dados poderá ser migrado para o **Amazon RDS (Relational Database Service)**, que é um serviço de banco de dados gerenciado, ou para uma instância EC2, dependendo da necessidade de controle.
* **Armazenamento de Dados:**
    * **Amazon S3 (Simple Storage Service):** Utilizado para armazenar dados estáticos, arquivos e objetos, oferecendo alta durabilidade e escalabilidade.
* **Teste e Validação:** Realização de testes de desempenho e funcionalidade no novo ambiente AWS para garantir que todas as aplicações e o banco de dados estejam operando corretamente.

**Fase 3: Otimização e Operação**

* **Backup Automatizado:**
    * **AWS Backup:** Implementação de uma solução de backup centralizada e automatizada. O AWS Backup pode ser configurado para criar e gerenciar backups de instâncias EC2 e bases de dados RDS, definindo políticas de retenção e agendamento.
* **Otimização de Custos:**
    * **AWS Cost Explorer:** Ferramenta para monitorar e otimizar os gastos com os serviços da AWS.
    * **Savings Plans ou Reserved Instances:** Utilização de modelos de precificação que oferecem descontos significativos em troca de um compromisso de uso contínuo por um período.
* **Monitoramento e Gerenciamento:**
    * **Amazon CloudWatch:** Ferramenta para monitorar métricas de desempenho das instâncias EC2, bases de dados RDS e outros serviços.
    * **AWS CloudTrail:** Serviço que registra todas as ações realizadas no ambiente AWS, fornecendo um histórico para auditoria e segurança.

---

#### **4. Benefícios e Redução de Custos**

A migração para a AWS proporciona uma mudança significativa no modelo de gastos e na eficiência operacional, resultando em uma redução de custos tangível.

* **Transformação de CAPEX para OPEX:** A empresa deixará de fazer grandes investimentos de capital (CAPEX) na compra de hardware (servidores, sistemas de refrigeração, racks, nobreaks) e passará para um modelo de despesa operacional (OPEX), pagando apenas pelo uso dos serviços, de forma mensal e previsível.
* **Eliminação de Custos Operacionais:** A migração elimina a necessidade de manutenção de infraestrutura física, como reparo de hardware, gastos com energia elétrica para servidores e refrigeração, e custos com o espaço físico do datacenter.
* **Otimização de Pagamentos por Uso (Pay-as-you-go):** A AWS oferece o modelo de "pagar pelo que usar", que é especialmente benéfico para cargas de trabalho variáveis. A empresa pode escalar para cima durante picos de demanda e escalar para baixo em períodos de menor uso, evitando o custo de superprovisionamento de servidores.
* **Redução da Carga de Gerenciamento:** Utilizando serviços gerenciados como o Amazon RDS e o AWS Backup, a equipe de TI da empresa pode se concentrar em tarefas de maior valor, como inovação e desenvolvimento de produtos, em vez de gastar tempo com manutenção e administração de servidores e bancos de dados.
* **Economia com Instâncias Reservadas e Savings Plans:** Após a estabilização da carga de trabalho, é possível obter descontos substanciais (até 72%) ao se comprometer com um uso contínuo de recursos por 1 ou 3 anos, o que se traduz em economia a longo prazo.

---

#### **5. Cronograma Estimado**

* **Fase 1 (Planejamento):** 2 a 4 semanas
* **Fase 2 (Migração):** 4 a 12 semanas (dependendo da complexidade dos dados e da aplicação)
* **Fase 3 (Otimização):** 2 a 4 semanas

**Cronograma Total Estimado:** 8 a 20 semanas.

---

#### **6. Próximos Passos**

Recomendamos uma reunião técnica para aprofundar a análise da infraestrutura atual e iniciar o planejamento detalhado da migração, com base nos serviços e estratégias apresentados.

**Contato:**
Andrew Marques
