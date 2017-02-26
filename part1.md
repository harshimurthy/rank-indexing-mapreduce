# Part 1 readings

| Learn-to-rank algorithm | NDCG@10 on training data  | NDCG@10 on validation data | ERR@10 on test data  | NDCG@10 on test data |
|----------|-------|-------|--------------- | ----------- |
| LambdaMART   |  0.5351 |  0.5651 |  0.0959 | 0.5473 |
| MART/GBRT  | 0.5002 |  0.5629 | 0.0955  | 0.5375 |
| AdaRank   |  0.4669 | 0.5627  | 0.0996  | 0.5412 |
| RankBoost | 0.5039 | 0.5614 | 0.0973 | 0.5351 |
| Linear Ccombination |  |   |    |  |


```
java -jar RankLib-2.1-patched.jar

java -jar RankLib-2.1-patched.jar  -train train.txt -test test.txt -validate vali.txt -ranker 6 -metric2t NDCG@10 -metric2T ERR@10 -save mymodel.txt

java -jar RankLib-2.1-patched.jar  -train train.txt -test test.txt -validate vali.txt -ranker 0 -metric2t NDCG@10 -metric2T ERR@10 -save mymodel_mart.txt

java -jar RankLib-2.1-patched.jar  -train train.txt -test test.txt -validate vali.txt -ranker 3 -metric2t NDCG@10 -metric2T ERR@10 -save mymodel_ada.txt

#NDCG@10 on test data
java -jar RankLib-2.1-patched.jar -load mymodel.txt -test test.txt -metric2T NDCG@10


java -jar bin/RankLib.jar -test test.txt -metric2T NDCG@10 -idv output/baseline.ndcg.txt

java -cp RankLib-2.1-patched.jar ciir.umass.edu.eval.Analyzer -all output/ -base baseline.ndcg.txt > analysis.txt



```

        
0: MART (gradient boosted regression tree) .
1: RankNet

2: RankBoost

3: AdaRank

4: Coordinate Ascent

6: LambdaMART

7: ListNet

8: Random Forests
