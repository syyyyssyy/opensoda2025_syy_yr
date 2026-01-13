# OpenDiggerInsight

本项目基于OpenDigger开源数据集，构建多维度项目健康度评估模型，对云原生、Apache及AI/ML三大生态系统中的主流开源项目进行量化分析。研究采用活跃度、影响力、贡献者多样性及风险因子四个核心维度，结合加权因子模型和非线性变换，实现了开源项目健康状况的定量评价。通过对十四个代表性开源项目的深入分析，本研究揭示了不同生态系统项目的健康特征差异，并采用EasyGraph库构建贡献者协作网络，分析企业组织在开源社区中的核心地位。

## 项目分工

本研究由苏妍昱与袁睿协作完成。组长苏妍昱主导了研究框架设计、健康度评估模型的构建与公式推导，还负责了数据分析、跨生态系统对比、案例解读以及报告的撰写与整合。组员袁睿完成了数据采集、预处理、基础代码实现以及可视化图表的生成。项目通过明确分工与紧密配合，共同完成了从模型构建、实验分析到报告呈现的全流程工作。

## 项目结构

OpenDiggerInsight.ipynb是核心分析文件，包含完整的数据处理、健康度计算和可视化分析代码，共生成10张可视化图表。top_300_metrics目录包含来自OpenDigger的原始指标数据，涵盖14个代表性开源项目的活跃度(activity)、OpenRank、Stars、Bus Factor、贡献者邮箱后缀(contributor_email_suffixes)、新贡献者(new_contributors)等维度信息。运行方式上，需配置Python环境并安装依赖库，按顺序执行数据获取、指标计算、分析与可视化的代码模块，即可复现全部实验并生成图表与数据结果。

## 样本项目

云原生生态包括Kubernetes、Istio、Cilium、Argo-CD和Podman五个项目，这些项目构成了现代云原生基础设施的核心组件。Apache生态包括Spark、Flink、Airflow、Pulsar和Superset五个项目，代表了大数据处理领域的主流技术。AI/ML生态包括PyTorch、TensorFlow、Transformers和Scikit-Learn四个项目，覆盖了深度学习和机器学习的主流框架。

## 主要发现

实验结果显示PyTorch(85.4分)和Kubernetes(84.5分)健康度最高，均超过84分高健康线。Cilium位列第三(80.4分)，TensorFlow(78.8分)和Spark(77.4分)处于中上水平。得分最低的三个项目是scikit-learn(69.9分)、superset(69.1分)和pulsar(68.1分)。Cloud Native生态平均健康度最优(78.3分)，AI/ML次之(77.1分)，Apache最低(72.2分)。研究发现高活跃度不等同于高健康度，AI/ML生态活跃度最高但健康度排名第二。企业参与度高的项目(如cilium 91.1%、pytorch 87.2%)风险抵抗能力更强。成熟项目(如Kubernetes、Spark)活跃度呈下降趋势，但健康度仍维持较高水平。采用EasyGraph库构建贡献者协作网络，分析表明google.com度中心性最高(约850)，企业组织在云原生生态中占据核心协作地位。

## 可视化图表

fig1_health_scores.png展示项目健康度得分分布，fig2_ecosystem_health.png展示生态系统健康度对比，fig3_activity_trend.png展示主要项目活跃度时序变化，fig4_openrank.png展示OpenRank影响力指标对比，fig5_diversity.png展示贡献者多样性指标，fig6_bus_factor.png展示Bus Factor分布，fig7_k8s_yearly.png展示Kubernetes年度活跃度趋势，fig8_k8s_contrib.png展示Kubernetes贡献者域名分布，fig9_stars.png展示主要项目年度Stars增长，fig10_easygraph.png展示贡献者网络中心性分析。

## 运行环境

Python 3.7+，依赖包括numpy、matplotlib、easygraph、python-docx。运行jupyter notebook打开OpenDiggerInsight.ipynb执行分析。确保top_300_metrics目录下包含所需项目的指标数据文件。
