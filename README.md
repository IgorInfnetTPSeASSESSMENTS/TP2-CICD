## Depuração de falha no pipeline

Durante o desenvolvimento da pipeline, foi provocado intencionalmente um erro em um dos steps do workflow para simular uma falha real de execução. A identificação do problema foi feita acessando a aba **Actions** do GitHub e abrindo a execução que falhou. Em seguida, foram analisados os **jobs**, os **steps** e principalmente os **logs** gerados pelo step com erro, onde foi possível localizar a causa da falha.

As ferramentas da interface do GitHub utilizadas nesse processo foram a aba **Actions**, a visualização detalhada da execução do workflow, os logs de cada step e o histórico das execuções. Esses recursos permitiram acompanhar exatamente em qual etapa o erro aconteceu e qual mensagem foi retornada pelo runner.

Após identificar a causa, o comando incorreto foi corrigido no arquivo do workflow e um novo push foi realizado no repositório. Na execução seguinte, o pipeline foi concluído com sucesso, confirmando que o problema havia sido resolvido corretamente.

## Diferença entre os dois modos de execução da pipeline

Após executar o pipeline pelos dois modos, foi possível observar uma diferença clara entre eles. No disparo por **push**, a execução acontece automaticamente sempre que há uma alteração enviada para a branch configurada, o que é útil para garantir validação contínua do projeto sem depender de ação manual. Já no modo **Run workflow**, a execução é iniciada manualmente pela interface do GitHub Actions, permitindo escolher parâmetros e controlar melhor quando a pipeline deve rodar. Ao explorar os filtros da aba **Actions**, também ficou mais fácil identificar o tipo de gatilho utilizado em cada execução, diferenciando as execuções automáticas das manuais no histórico do workflow.
