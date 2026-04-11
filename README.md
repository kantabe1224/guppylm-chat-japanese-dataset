# GuppyLM Chat Japanese Dataset 
## これは何？
[GuppyLM](https://github.com/arman-bd/guppylm) のモデル作成を日本語の会話で試したい人向けのデータセットです。

## GuppyLM とは？
小さな言語モデルをスクラッチから作成する体験ができます。

Gigazineによる紹介記事
[たった5分でゼロから言語モデルを自作できる「GuppyLM」、Google Colabを使って無料でトレーニング可能
](https://gigazine.net/news/20260407-guppylm-tiny-llm-built-from-scratch/)

## データセット
元のデータセット [arman-bd/guppylm-60k-generic](https://huggingface.co/datasets/arman-bd/guppylm-60k-generic) を
[gemma-2-9b-it-q4_k_m.gguf](https://huggingface.co/zhezhe/gemma-2-9b-it-Q4_K_M-GGUF/blob/main/gemma-2-9b-it-q4_k_m.gguf) で和訳したものです。

10件ずつ和訳を行い失敗したブロックは削除したため、元のデータセットより数が減っています。
train 53,940件
test 2,865件

```
from datasets import load_dataset
ds = load_dataset("parquet", data_files={"train": "train_ja.parquet", "test": "test_ja.parquet"})
print(ds["train"][0])
#{'input': '暖房器が欲しい', 'output': '今日は水は冷たい。ただ隠れて待つよ。', 'category': 'temp_cold'}
```

## 免責事項
> **私が勝手に作った和訳データですので、元の GuppyLM プロジェクトへの問い合わせは行わないでください**
> 
> 本ソフトウェアは現状有姿（AS IS）で提供され、明示的・暗示的を問わず、いかなる保証もありません。
> 使用によって生じたいかなる損害についても、著者は一切責任を負いません。
> **すべて自己責任でご利用ください。**

## License
MIT
