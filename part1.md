# Part 1 readings

| Learn-to-rank algorithm | NDCG@10 on training data  | NDCG@10 on training data | ERR@10 on test data  
|----------|-------|-------|-------------------
| LambdaMART   |  0.5351 |  0.5651 |  0.0959 |
| MART/GBRT  | 0.5002 |  0.5629 | 0.0955  |
| AdaRank   |  0.4669 | 0.5627  | 0.0996  |
| Linear Ccombination |  |   |    |


```
java -jar RankLib-2.1-patched.jar

java -jar RankLib-2.1-patched.jar  -train train.txt -test test.txt -validate vali.txt -ranker 6 -metric2t NDCG@10 -metric2T ERR@10 -save mymodel.txt

java -jar RankLib-2.1-patched.jar  -train train.txt -test test.txt -validate vali.txt -ranker 0 -metric2t NDCG@10 -metric2T ERR@10 -save mymodel_mart.txt

java -jar RankLib-2.1-patched.jar  -train train.txt -test test.txt -validate vali.txt -ranker 3 -metric2t NDCG@10 -metric2T ERR@10 -save mymodel_ada.txt



```

        
0: MART (gradient boosted regression tree)
1: RankNet
2: RankBoost
3: AdaRank
4: Coordinate Ascent
6: LambdaMART
7: ListNet
8: Random Forests
