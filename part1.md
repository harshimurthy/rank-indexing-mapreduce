# Part 1 readings

| Learn-to-rank algorithm | NDCG@10 on training data  | NDCG@10 on training data | ERR@10 on test data  
|----------|-------|-------|-------------------
| LambdaMART   |  0.5351 |  0.5651 |  0.0959 |
| MART/GBRT  |  |   |   |
| AdaRank   |   |   |   |
| Linear Ccombination |  |   |    |


```
java -jar RankLib-2.1-patched.jar
java -jar RankLib-2.1-patched.jar  -train train.txt -test test.txt -validate vali.txt -ranker 6 -metric2t NDCG@10 -metric2T ERR@10 -save mymodel.txt

```
