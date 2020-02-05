# BERT-SQUAD 

## Training 
Pytorch with HuggingFace provide all the scripts necessary for training [huggingface](https://github.com/huggingface/pytorch-transformers)

## Run

`run_squad.py`: Training and fine-tuning on SQuAD for question-answering. Multiple GPUs can be used at the same time with CUDO cores.

```bash
python run_squad.py `
  --model_type bert `
  --model_name_or_path bert-base-uncased `
  --do_eval `
  --do_train `
  --do_lower_case `
  --predict_file Squad/dev-v2.0.json `
  --train_file Squad/train-v2.0.json `
  --learning_rate 3e-5 `
  --num_train_epochs 2.0 `
  --per_gpu_train_batch_size 2 `
  --per_gpu_eval_batch_size 2 `
  --save_steps 1000 `
  --max_seq_length 384 `
  --doc_stride 128 `
  --output_dir ../model/Squad_2.0/ `
  --overwrite_output_dir `
  --version_2_with_negative `
```

## Results:

```json
{
  "exact": 71.44782279120695,
  "f1": 74.8949417043327,
  "total": 11873,
  "HasAns_exact": 70.24291497975709,
  "HasAns_f1": 77.14703826847852,
  "HasAns_total": 5928,
  "NoAns_exact": 72.64928511354078,
  "NoAns_f1": 72.64928511354078,
  "NoAns_total": 5945
}
```
