# rzhd_neuro

## В репе выложены документ для создания векторной БД в виде локальной  текстовой базы данных
## Так же архив с векторной базой данных

## Как настроить

В среде conda с доступным PyTorch/CUDA клонируйте репозиторий и запустите его в каталоге верхнего уровня:

```
pip install -e .
```

См example_text_completion.py. несколько примеров. Для иллюстрации см. команду ниже, чтобы запустить ее с моделью llama-2-7b ( nproc_per_nodeнеобходимо установить это MPзначение):

```
torchrun --nproc_per_node 1 example_text_completion.py \
    --ckpt_dir llama-2-7b/ \
    --tokenizer_path tokenizer.model \
    --max_seq_len 128 --max_batch_size 4
```

Вы также можете развернуть дополнительные классификаторы для фильтрации входных и выходных данных, которые считаются небезопасными. См. репозиторий llama-recipes, где приведен пример добавления средства проверки безопасности ко входным и выходным данным вашего кода вывода.

Примеры использования llama-2-7b-chat:

```
torchrun --nproc_per_node 1 example_chat_completion.py \
    --ckpt_dir llama-2-7b-chat/ \
    --tokenizer_path tokenizer.model \
    --max_seq_len 512 --max_batch_size 6
```
