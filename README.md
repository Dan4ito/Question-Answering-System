# Question-Answering-System

## How to setup

1. Clone the repo
2. Download and paste Bert-on-Squad-V2.0 model into the directory - https://drive.google.com/file/d/1hktnjAJOdOwPxTK3R-KST9-kUQFYPusM/view?usp=sharing
3. Install the following dependencies - pip install pytorch-pretrained-bert, pip install googletrans, pip install termcolor

## Running the application

### Running AI_QnA_System.py directly (no command line arguments)
It will be run with default parameters:
    ("--paragraph", default="./Input_file_bg.txt", type=str)
    ("--model", default="./pytorch_model.bin", type=str)
    ("--max_seq_length", default=384, type=int)
    ("--doc_stride", default=128, type=int)
    ("--max_query_length", default=64, type=int)
    ("--config_file", default="./bert_config.json", type=str)
    ("--max_answer_length", default=30, type=int)
    ("--input_language", default="bg", type=str)
    
### Running AI_QnA_System.py (with command line arguments through command line)
1. Navigate to the folder
2. Execute - python AI_QnA_System.py --paragraph ./Input_file_en.txt --model ./pytorch_model.bin --config_file ./Results/bert_config.json --input_language e


