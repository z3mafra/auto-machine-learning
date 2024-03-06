# Relatório Entrega do Projeto

Repositório: *auto-machine-learning*

O principal objetivo do desafio foi Trabalhar com Machine Learning na Prática no Azure ML, para isso temos três objetivos secundários:

> I. Acesso e uso do recurso de machine learning automatizado no Azure Machine Learning;
> II. Treinar e avaliar um modelo de machine learning;  
> III. Implantar e testar o modelo treinado.  

Para completar o desafio, foram incluídas tarefas no GItHub, para compartilhamento do projeto.

Com isso segui as [4] principais Etapas:

[1] Criar um novo repositório no github com um nome a sua preferência;  
[2] Criar um modelo de previsão com seus devidos pontos de extremidade configurados:  
>        a. Criar um espaço de trabalho do Azure Machine Learning;  
>        b. Usar Machine Learning para treinar um modelo;  
>        c. Avaliar o melhor modelo;  
>        d. Implantar e testar o modelo;  
>        e. Testar o serviço implantado;  
>        f. Limpar o espsço de trabalho.  
[3] screver o passo a passo desse processo em um readme.md de como foram as etapas;  
[4] Salvar nesse repositório o arquivo readme.md e o arquivo .json de pontos de extremidade.  
  
-------------------

## **[1] Criar um novo repositório no github com um nome a sua preferência:**  

Para criar o repositório:
>
> - Acessei o site do GitHub, logado em meu perfil.  
> - Cliquei em Novo repositório. Abre um menu.  
> - Cliquei opção "Novo repositório".  
> - Digitei um nome para o repositório: "auto-machine-learning".  
> - Adicionei uma descrição do repositório: "Uso recurso de machine learning automatizado no Azure Machine Learning para treinar e avaliar um modelo de machine learning. Implantar e testar o modelo treinado.".  
> - Escolhi a visibilidade "pública" do repositório.  
> - Selecionei Inicializar este repositório com um arquivo LEIAME.  
> - Cliquei em "Criar repositório".  
> - Foi redigida uma descrição breve no arquivo readme.md.  

Para criar o clone local do repositório:
>
> - Entrei no diretório Git local.
> - Cliquei com o botão direito e optei por: Open Git Bash here.
> - Na linha de comando digitei: git clone <https://github.com/z3mafra/auto-machine-learning.git>
> - Em seguida, para atualizar o repositório local, digitei o comando: git pull <https://github.com/z3mafra/auto-machine-learning.git>  
  
Com isso realizado, o próximo passo foi fazer as etapas do moledo de aprendizagem.
  
-------------------

## **[2] Criar um modelo de previsão com seus devidos pontos de extremidade configurados:**  

Neste desafio, deve-se fazer uso do recurso de machine learning automatizado no Azure Machine Learning para treinar e avaliar um modelo de machine learning. Em seguida, implantar e testar o modelo treinado. E, finalmente, limpar a área de trabalho.

### a. Criar um espaço de trabalho do Azure Machine Learning  

Para utilizar o Azure Machine Learning, é necessário aprovisionar um espaço de trabalho do Azure Machine Learning na sua subscrição do Azure. Depois, você poderá usar o estúdio Azure Machine Learning para trabalhar com os recursos do seu espaço de trabalho.

1. Faça login no portal do Azure em <https://portal.azure.com> usando as credenciais da Microsoft.
Aqui é necessário haver um cadastramento no portal Azure: fui na opção: “Começar com uma avaliação gratuita do Azure”; vai para a página “Crie na nuvem com uma conta gratuita do Azure”, optei por “Experimentar gratuitamente”. Foi iniciado o processo de cadastro da conta, incluindo um cartão de crédito.

2. Selecione + Criar um recurso, pesquise Machine Learning e crie um novo recurso Azure Machine Learning com as seguintes configurações:

> - Assinatura: a assinatura do Azure dsiponível.
> - Grupo de recursos: criei o grupo de recursos “Lab-AI-900-AML”.
> - Nome: inserir o nome do espaço de trabalho “LabLearn”.
> - Região: opção sugerida “East US 2”
> - Conta de armazenamento: utilizaei a conta padrão criada para esse espaço de trabalho.
> - Cofre de chaves: utilizaei o cofre de chaves padrão criado para esse espaço de trabalho.
> - Insights de aplicativos: utilizaei o recurso padrão de insights de aplicativos criado esse espaço de trabalho.
> - Registro de contêiner: Optar po “Nenhum”.
3. Selecionei Revisar + criar e selecione Criar. Aguardei a criação do seu espaço de trabalho, para ir para o recurso implantado.
4. Selecionei Iniciar estúdio; abriu uma nova guia do navegador para <https://ml.azure.com>.
5. No estúdio Azure Machine Learning, pode ser visto o espaço de trabalho recém-criado, em “Todos os espaços de trabalho”, no menu lateral. Entrei no espaço de trabalho criado: “LabLearn”.  
  
### b. Usar Machine Learning para treinar um modelo  

No espaço de trabalho, volta-se ao Studio, onde se faz a opção por “ML automatizado” no menu lateral.
Clicar em + Novo trabalho de ML automatizado.

Observação: se usará um conjunto de dados de detalhes históricos de aluguel de bicicletas para treinar um modelo que prevê o número de aluguel de bicicletas esperado em um determinado dia, com base em características sazonais e meteorológicas.  
  
O novo trabalho abre uma nova página para as configurações necessárias, com os seguintes itens:  
 
 Método de treinamento: Treinar automaticamente  
--         Configurações básicas:  
> - Job name: mslearn-bike-automl
> - New experiment name: mslearn-bike-rental
> - Description: Aprendizado de máquina automatizado para previsão de aluguel de bicicletas
> - Tags: none  
       Tipo de tarefa e dados:  
> - Select task type: Regressão
> - Select dataset: Create a new dataset with the following settings:
> - Tipos de dados:  
> > - Name: aluguel-bicicletas
> > - Description: Dados históricos de aluguel de bicicletas
> > - Type: Tabular
  
 » Avançar  
            ▪ Fonte de dados:  
                • Select de arquivos da web  
 » Avançar  
            ▪ Web URL:  
                • Web URL: <https://aka.ms/bike-rentals>  
                • Skip data validation: do not select  
 » Avançar  
            ▪ Configurações:  
                • File format: Delimited  
                • Delimiter: Comma  
                • Encoding: UTF-8  
                • Column headers: Somente o primeiro arquivo possui cabeçalho  
                • Skip rows: None  
                • Dataset contains multi-line data: do not select  
 » Avançar  
            ▪ Esquema:  
                • Include all columns other than Path  
 » Avançar  
                • Review the automatically detected types  
  
          Selecione Criar.  
          Depois que a dataset foi criada, selecione o dataset aluguel-bicicletas para submeter o ML job.  
 » Avançar  
  
       Configurações de tarefa:  
        ◦ Task type: Regression  
        ◦ Dataset: aluguel-bicicletas  
        ◦ Target column: Rentals (integer)  
  
          Selecionar “Additional configuration settings”:  
           ▪ Primary metric: Normalized root mean squared error  
            ▪ Explain best model: Unselected  
            ▪ Use all supported models: Unselected.  
            ▪ Allowed models: Select only RandomForest and LightGBM — normally you’d want to try as many as possible, but each model added increases the time it takes to run the job.  
        ◦ Limits: Expand this section  
            ▪ Max trials: 3  
            ▪ Max concurrent trials: 3  
            ▪ Max nodes: 3  
            ▪ Metric score threshold: 0.085 (so that if a model achieves a normalized root mean squared error metric score of 0.085 or less, the job ends.)  
            ▪ Timeout: 15  
            ▪ Iteration timeout: 15  
            ▪ Enable early termination: Selected  
        ◦ Validation and test:  
            ▪ Validation type: Divisão de validação de treinamento  
            ▪ Percentage of validation data: 10  
            ▪ Test dataset: None  
 » Avançar  
  
       Cálculo:  
        ◦ Select compute type: Serverless  
        ◦ Virtual machine type: CPU  
        ◦ Virtual machine tier: Dedicated  
        ◦ Virtual machine size: Standard_DS3_V2*  
        ◦ Number of instances: 1  
 » Avançar  
 » Enviar trabalho de treinamento  
       Aqui foi Submetido o trabalho de treinamento, automaticamente.  
  
       **OBSERVAÇÃO:** Tempo de espera longo para o trabalho terminar. Pausa para um café!  
  
### c. Avaliar o melhor modelo  

Após completar o “automated machine learning job”  pode ver o melhor modelo treinado.  
  
    1.  Na aba Visão geral, aparece o resumo do melhor modelo.  
    2. Selecionar o texto sob Algorithm name “VotingEnsemble” para ver os detalhes do melhor modelo.  
    3. Selecionar a aba das Metrics (menu acima) e seleciona os graficos residuals e predicted_true if they are not already selected.  
       Review the charts which show the performance of the model. The residuals chart shows the residuals (the differences between predicted and actual values) as a histogram. The predicted_true chart compares the predicted values against the true values.  

### d. Implantar e testar o modelo  

    1. On the Model tab for the best model trained by your automated machine learning job, select Deploy and use the Web service option to deploy the model with the following settings:  
        ◦ Name: prevealuguel  
        ◦ Description: Predict cycle rentals  
        ◦ Compute type: Azure Container Instance  
        ◦ Enable authentication: Selected  
 » Implantar  
  
    2.  Espera para a impantação comçar – levou um tempo. O Status da Implantação (Deploy status) para o endpoint do prevealuguel ficou indicado nas “notificações” no menu da parte superior da págiana como implantação em andamento.  
    3. Aguardar até o “Deploy status” mudar para “Healthy”. Levou alguns minutos.  
  
### e. Testar o serviço implantado  
  
Agora você pode testar o serviço implantado.  
    1. No Azure Machine Learning studio, no menu do lado esquerdo, selecionei Endpoints e abri o “prevealuguel real-time endpoint”.  
    2. Na página do “ prevealuguel real-time endpoint” abrir a aba de Testar.  
    3. No painel de Inserir dados para teste de ponto de extremidade, troquei o template JSON pelo seguinte código de input data:  
  
        {  
          "Inputs": {   
            "data": [  
              {  
                "day": 1,  
                "mnth": 1,  
                "year": 2022,  
                "season": 2,  
                "holiday": 0,  
                "weekday": 1,  
                "workingday": 1,  
                "weathersit": 2,  
                "temp": 0.3,  
                "atemp": 0.3,  
                "hum": 0.3,  
                "windspeed": 0.3  
              }  
            ]   
          },   
          "GlobalParameters": 1.0  
        }  
  
    4.  Cliquei o botão de Testar.  
    5. Verificando os resultados do teste, que inclue o numero predito de alugueis baseado no the recursos de entrada – que retornou o seguinte:  
  
       {  
         "Results": [  
           388.3180761141912  
         ]  
       }  
  
       O painel de teste pegou os dados de entrada e usou o modelo treinado para retornar o número previsto de aluguéis.  
  
       Em resumo: foi usado um conjunto de dados históricos de aluguel de bicicletas para treinar um modelo. O modelo previu o número de aluguel de bicicletas esperado em um determinado dia, com base em características sazonais e meteorológicas.  
  
### f. Limpar o espsço de trabalho  
  
Todo este trabalho está hospedado numa instância de contêiner do Azure, na Web.  
Com o desafio finalizado, recomanda-se excluir o ponto de extremidade para evitar cobranças desnecessárias de uso do Azure.  
    1.  Na página do Azure Machine Learning studio, (<https://ml.azure.com/home?tid=dededec5-9746-4b92-971d-f4c3755090da)(https://ml.azure.com/?azure-portal=true>), entrei no “espao de trabalho” LabLearn, selecionei Endpoints, marca o endpoint prevealuguel.  Depois selecionar Excluir e confirmei que vai excluir o endpoint.  

       Observação 1: Excluir o processamento (compute) garante que a assinatura não será cobrada por recursos de computação.  
       Observação 2: Mas, será cobrado o armazenamento de dados, no espaço de trabalho do Azure Machine Learning na sua assinatura.  
       Observação 3: No caso de término desse exercício no Azure Machine Learning, é bom  eliminar o espaço de trabalho Azure Machine Learning e os recursos associados.  
  
Para deletar o workspace:  
    1.  No portal Azure, (<https://portal.azure.com/?azure-portal=true>) na página de Grupos de Recursos, abrir o “resource group” (Lab-AI-900), que foi especificado quando foi criado o workspace no Azure Machine Learning.  
    2. Clicar Excluir grupo de recursos, cliquei no icone ‘copiar’, ao lado o nome do grupode recursos para confirmar que é para deletar, e selecionar Excluir. Depois confirmar “Excluir”.  

-------------------

## **[3] Escrever o passo a passo desse processo em um readme.md de como foram as etapas:**  

O processo de escrita foi:
  
- começou com anotações, a cada passo, seguindo a documentação e a orientação em vídeo, num editor de texto padrão;  
- depois trasnferido por Copy/Paste para o arquivo readme.md, no repositório local, aberto no Visual Studio Code.  
  
-------------------

## **[4] Salvar nesse repositório o arquivo readme.md e o arquivo .json de pontos de extremidade:**  

O processo final foi:

- após passar todas as anotações para o arquivo readme.md;  
- revisão do texto;  
- preparação do arquivo .json;  
- envio com o comando git push, para o repositório remoto no GitHub.  
- compartilhamento do link desse repositório através do botão 'entregar projeto'
