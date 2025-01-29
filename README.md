# Agendador de Tarefas com Schedule

Este é um simples agendador de tarefas em Python que utiliza a biblioteca `schedule` para executar uma função a cada minuto.

## Pré-requisitos

Antes de executar o script, certifique-se de ter o Python instalado e a biblioteca `schedule` disponível.

Se ainda não tiver a biblioteca instalada, utilize o seguinte comando:

```bash
pip install schedule
```

Se estiver usando o Poetry, execute:

```bash
poetry add schedule
```

## Como funciona

O script realiza as seguintes etapas:

1. Importa as bibliotecas necessárias (`schedule` e `time`).
2. Define uma função chamada `job()` que exibe a mensagem "Estou em execução".
3. Usa o `schedule.every(1).minutes.do(job)` para agendar a execução da função `job()` a cada minuto.
4. Entra em um loop infinito que verifica e executa as tarefas agendadas com `schedule.run_pending()`, esperando 1 segundo entre as verificações.

## Como Executar

Para executar o script, utilize o seguinte comando:

```bash
python agendador.py
```

Se estiver utilizando um ambiente virtual gerenciado pelo Poetry, execute:

```bash
poetry run python agendador.py
```

## Código Completo

```python
import schedule
import time

def job():
    print("Estou em execução")

schedule.every(1).minutes.do(job)

while True:
    schedule.run_pending()
    time.sleep(1)
```



