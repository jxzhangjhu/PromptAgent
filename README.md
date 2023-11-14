# PromptAgent
This project aims to automatically optimize prompt using RAP

## Installation
```bash
git clone https://github.com/XinyuanWangCS/PromptAgent.git
cd PromptAgent
conda create -n prompt_agent
conda activate prompt_agent
pip install -r requirement.txt
```


## Run MCTS agent
```bash
python src/main.py --search_algo mcts --pred_model gpt-3.5-turbo --log_dir logs/ --post_instruction False  --train_shuffle True --batch_size 5 --expand_width 3 --num_new_prompts 1 --iteration_num 12 --depth_limit 8 --seed 42 --task_name ?  --data_dir ? --train_size  --eval_size  --test_size  --test_all_nodes False --init_prompt "" --api_key ""
```
For example, run Penguins_in_a_table:
```bash
python src/main.py --task_name bigbench  --search_algo mcts --pred_model gpt-3.5-turbo --log_dir logs/ --post_instruction False --init_prompt "Answer questions about a table of penguins and their attributes." --train_shuffle True --batch_size 5 --expand_width 3 --train_size 70 --eval_size 70 --test_size 79 --iteration_num 12 --depth_limit 8 --data_dir datasets/penguins_in_a_table.json --api_key 
```
## Run test.py to test prompt
```bash
python src/test.py --task_name bigbench --exp_name "20230913_1609-bigbench_geometric_shapes-algo_mcts-batch_2-train_150-eval_5-test_5" --eval_prompt "your prompt" --api_key "your_api" --data_dir "bigbench json path"
```

