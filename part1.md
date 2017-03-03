# Part 1 readings

## Individual comparison

### Fold 1
| Learn-to-rank algorithm | NDCG@10 on training data  | NDCG@10 on validation data |  NDCG@10 on test data |
|----------|-------|-------|----------- |
| LambdaMART (6)   |  0.4633 |  0.4569 |  0.4569 |
| MART/GBRT(0)  | 0.4589 | 0.4542  | 0.4421  |
| AdaRank (3)  |  0.3397 | 0.3406  | 0.3348  |
| RankBoost(2) | 0.3401 | 0.3378 | 0.3345 |
| Linear Ccombination |  |   |    |  

### Fold 2
| Learn-to-rank algorithm | NDCG@10 on training data  | NDCG@10 on validation data |  NDCG@10 on test data |
|----------|-------|-------|----------- |
| LambdaMART (6)   | 0.4762  | 0.4466  | 0.4461   |
| MART/GBRT(0)  | 0.4537 | 0.439  | 0.4396  |
| AdaRank (3)  |  0.3375 | 0.3337  | 0.3397  |
| RankBoost(2) | 0.3423 | 0.3337 | 0.3316 |
| Linear Ccombination |  |   |    | 

## Overall Comparison


------------------------------------------------------------------------
Overall comparison
------------------------------------------------------------------------

baseline.ndcg.txt [baseline]    0.1739

| System | Performance	| Improvement | Win |	Loss	| p-value |
|----------|-------|-------|--------------- | ----------- | -------- |
|lm.ndcg.txt   |  0.4452 | +0.2714 (+156.1%)    |   1710 |    189 |     0.0 |
|mart.ndcg.txt  | 0.4421 | +0.2683 (+154.32%)    |  1715 |   190  |    0.0 |
|adarank.ndcg.txt |       0.3348 | +0.1609 (+92.56%)     |  1521   | 369   |  0.0 |
|rankboost.ndcg.txt |     0.3345 | +0.1606 (+92.4%)       | 1546   | 347   |  0.0 |

```
java -jar RankLib-2.1-patched.jar

java -jar RankLib-2.1-patched.jar  -train train.txt -test test.txt -validate vali.txt -ranker 6 -metric2t NDCG@10 -metric2T ERR@10 -save mymodel.txt

java -jar RankLib-2.1-patched.jar  -train train.txt -test test.txt -validate vali.txt -ranker 0 -metric2t NDCG@10 -metric2T ERR@10 -save mymodel_mart.txt

java -jar RankLib-2.1-patched.jar  -train train.txt -test test.txt -validate vali.txt -ranker 3 -metric2t NDCG@10 -metric2T ERR@10 -save mymodel_ada.txt

java -jar RankLib-2.1-patched.jar  -train train.txt -test test.txt -validate vali.txt -ranker 2 -metric2t NDCG@10 -metric2T ERR@10 -save mymodel_rankboost.txt

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
