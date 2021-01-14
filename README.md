# 基于 GPT 模型的中国古典诗歌生成系统


UR KEY：T19G54




To train the model:


```

python train.py \
  --model_config config/model_config_small.json \
  --tokenized_data_path data/tokenized/ \
  --tokenizer_path cache/vocab_small.txt \
  --raw_data_path data/train.json \
  --epochs 30 \
  --log_step 200 \
  --stride 512 \
  --output_dir model/ \
  --device 0,1,2,3 \
  --num_pieces 100 \
  --raw

```



To generate samples:
```
python generate.py \
  --device 0 \
  --length 900 \
  --tokenizer_path cache/vocab_small.txt \
  --model_path model/final_model \
  --prefix "[CLS][MASK]" \
  --topp 1 \
  --temperature 1.0
```
