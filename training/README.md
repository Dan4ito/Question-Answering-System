# BERT-SQUAD 

## Training 
Pytorch with HuggingFace provide all the scripts necessary for training [huggingface](https://github.com/huggingface/pytorch-transformers)

## Run

`run_squad.py`: Training and fine-tuning on SQuAD for question-answering. Multiple GPUs can be used at the same time with CUDO cores. Currently Windows is not supported.

```bash
python -m torch.distributed.launch --nproc_per_node=8 ./run_squad.py \
    --model_type bert \
    --model_name_or_path bert-large-uncased-whole-word-masking \
    --do_train \
    --do_eval \
    --do_lower_case \
    --train_file Squad/train-v2.0.json \
    --predict_file Squad/dev-v2.0.json \
    --learning_rate 3e-5 \
    --num_train_epochs 2 \
    --max_seq_length 384 \
    --doc_stride 128 \
    --output_dir ../model/finetuned_squad/ \
    --per_gpu_eval_batch_size=3   \
    --per_gpu_train_batch_size=3   \
```

## Results:

```bash
python Squad/evaluate-v2.0.py Squad/dev-v2.0.json ../model/finetuned_squad/predictions.json
{"exact_match": 86.32179843225573, "f1": 93.0912449012866}
```
