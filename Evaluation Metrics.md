# 基准：
- MathVista(几何子集)

  来源于Geometry3K，UniGeo，GeoQA+和GEOS

- Geometry3K

  带有文本和图像的四选一的选择题

- PGPS9K

  带有文本和图像的四选一的选择题

- UniGeo

  GeoQA和9543个证明题来自高中课本和线上资源

  “We further define five sub-tasks: Parallel, Triangle, Quadrangle, Congruent, and Similarity, to provide the detailed performance of models” 

- GeoQA

  4998个几何计算问题(包括角度,长度,面积),来自中国的中学考试

- GeoQA+

  GeoQA的升级版

- MathVerse

  并非全是平面几何问题，在minitest中占比64.7%

- WE-math

  包含代数

- GeoEval

  先前数据集的集合

- MathVision

  3040 个高质量的数学问题，具有视觉上下文，来自真实的数学竞赛。

# 评价指标：

前五个最常用

1. Top1/Top10:

    Top-1准确率：这是指在给定的数据集中，模型生成的最佳输出序列是否正确的百分比。即模型生成的第一个候选输出是否与目标序列匹配。 

    Top-10准确率：这是指在生成的前10个序列中，目标序列出现的百分比。也就是说，如果目标序列出现在模型返回的前10个候选输出中，则计为一次成功。

    We report top-1 accuracy and top-10 accuracy. The top-1 accuracy is the percentage of the best output sequences that are correct in the given dataset. The top-10 accuracy is the percentage of target sequences appearing in the top 10 generated sequences.---ISARSTEP: A BENCHMARK FOR HIGH-LEVEL  MATHEMATICAL REASONING [code](https://github.com/chen-judge/UniGeo/blob/main/Geoformer/src/geo.py#L393)

2. completion:

    符号求解器给出的结果

3. choices:

    四选一的正确率（模型求出的答案不在所给选项的，随机选择一个）

4. top-3:

    正确答案出现在前三个候选中的概率

    In Completion, the symbolic solver gives the result searched for and the neural solver selects the first executable solution program. The Choice is defined as choosing the correct option from four candidates but selecting one randomly if answer is not in. The Top-3 computes the accuracy ratio of correct answer existing among top three solution candidates, less strict than Completion pattern.---A Multi-Modal Neural Geometric Solver with Textual Clauses Parsed from Diagram[code](https://github.com/mingliangzhang2018/PGPS/blob/main/utils/utils.py#L222)

5. 准确率:

    回答问题的正确率

6. 形式化指标（jaccard相似度）:

    计算生成的推理形式与给定的标准形式的相似度(重叠度)

7. TPA:

    定理预测准确率：给定的问题状态hi-1，预测下一个使用的理论[code](https://github.com/BitSecret/HyperGNet/blob/main/src/gps/train.py#L279)

8. PSSR:

    问题求解成功率

    PSSR 是成功解决问题与问题总数的比例。解决一个几何问题需要几个定理，模型必须正确且以正确的顺序预测这些定理。然后，这些预测将通过形式化系统进行验证，以确定问题是否已成功解决。这个指标评估模型的整体问题解决能力。[code](https://github.com/BitSecret/HyperGNet/blob/main/src/gps/pac.py#L192)

9. ROUGE-1:

    问题的符号化解析表现

10. F1 socre:

    精度 (P) 表示模型未能识别的真正无法识别的情况的比例，而召回率 (R) 表示模型正确标记为无法识别的无法识别的几何结构的比例。

    F1 得分 (F1) 通过标记 P 和 R 的谐波平均值来提供平衡的评估。F1 = 2 * PR/(P+R)[详细定义](https://cloud.tencent.com/developer/article/1486764)









