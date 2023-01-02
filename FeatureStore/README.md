# SageMaker Feature Store

**마지막 업데이트: 2023.01.02**


---
SageMaker Feature Store 스스로 공부할 수 있는 링크 및 설명을 제공 합니다. 자세한 사항은 참조의 블로그 및 기타 링크를 확인 부탁 합니다.

---

# 1. 주요 가이드

- [Amazon SageMaker Feature Store Overview (김대근님 노션)](https://daekeun.notion.site/Amazon-SageMaker-Feature-Store-Overview-448610b88ae4403181151fd56aac7e0c)
- [SageMaker 개발자 가이드](https://docs.aws.amazon.com/sagemaker/latest/dg/feature-store.html)

# 2. 주요 실습 코드
- [Feature Store Immersion Day](https://catalog.us-east-1.prod.workshops.aws/workshops/5c093162-c9ce-4203-ab35-0b94ca950ee8/en-US)
![workshop.png](img/workshop.png)
- [Other Notebook Examples](https://docs.aws.amazon.com/sagemaker/latest/dg/feature-store-notebooks.html)



# 3. 블로그
최신 블로그 순서로 정리되어 있습니다. 처음 접근하시는 분은 가장 아래에서 부터 보시면 좋습니다.

- [(Dec 2022) Speed ML development using SageMaker Feature Store and Apache Iceberg offline store compaction](https://aws.amazon.com/blogs/machine-learning/speed-ml-development-using-sagemaker-feature-store-and-apache-iceberg-offline-store-compaction/)
    - Apache Iceberg 의 Table Format 을 제공 출시 및 설명을 다루고 있습니다.
    - ![apche_iceberg.png](img/apche_iceberg.png)




(Aug 2022) Promote feature discovery and reuse across your organization using Amazon SageMaker Feature Store and its feature-level metadata capability

* https://aws.amazon.com/blogs/machine-learning/promote-feature-discovery-and-reuse-across-your-organization-using-amazon-sagemaker-feature-store-and-its-feature-level-metadata-capability/
* [Image: Image.jpg]



(Aug 2022) Simplify iterative machine learning model development by adding features to existing feature groups in Amazon SageMaker Feature Store

* https://aws.amazon.com/blogs/machine-learning/simplify-iterative-machine-learning-model-development-by-adding-features-to-existing-feature-groups-in-amazon-sagemaker-feature-store/
* [Image: Image.jpg]

(Jun 2022) Accelerate and improve recommender system training and predictions using Amazon SageMaker Feature Store

* https://aws.amazon.com/ko/blogs/machine-learning/accelerate-and-improve-recommender-system-training-and-predictions-using-amazon-sagemaker-feature-store/
* [Image: Image.jpg]

(Jun 2022) Easily create and store features in Amazon SageMaker without code

* https://aws.amazon.com/blogs/machine-learning/easily-create-and-store-features-in-amazon-sagemaker-without-code/
* [Image: Image.jpg]


(Apr 2022) Control access to Amazon SageMaker Feature Store offline using AWS Lake Formation

* https://aws.amazon.com/blogs/machine-learning/control-access-to-amazon-sagemaker-feature-store-offline-using-aws-lake-formation/
* [Image: Image.jpg]


(Oct 2021) Extend model lineage to include ML features using Amazon SageMaker Feature Store

* https://aws.amazon.com/blogs/machine-learning/extend-model-lineage-to-include-ml-features-using-amazon-sagemaker-feature-store/
* [Image: Image.jpg]


(Sep 2021) Scale ML feature ingestion using Amazon SageMaker Feature Store

* https://aws.amazon.com/ko/blogs/machine-learning/scale-ml-feature-ingestion-using-amazon-sagemaker-feature-store/
* [Image: Image.jpg]

(Aug 2021) Getting started with Amazon SageMaker Feature Store

* https://aws.amazon.com/blogs/machine-learning/getting-started-with-amazon-sagemaker-feature-store/
* [Image: Image.jpg]

(Jun 2021) Build accurate ML training datasets using point-in-time queries with Amazon SageMaker Feature Store and Apache Spark

* https://aws.amazon.com/blogs/machine-learning/build-accurate-ml-training-datasets-using-point-in-time-queries-with-amazon-sagemaker-feature-store-and-apache-spark/
* [Image: Image.jpg]

(Mar 2021) Enable feature reuse across accounts and teams using Amazon SageMaker Feature Store

* https://aws.amazon.com/blogs/machine-learning/enable-feature-reuse-across-accounts-and-teams-using-amazon-sagemaker-feature-store/
* [Image: Image.jpg]


(Jan 2021) Understanding the key capabilities of Amazon SageMaker Feature Store

* https://aws.amazon.com/blogs/machine-learning/understanding-the-key-capabilities-of-amazon-sagemaker-feature-store/
* [Image: Image.jpg]


(Dec 2020) Using streaming ingestion with Amazon SageMaker Feature Store to make ML-backed decisions in near-real time

* https://aws.amazon.com/blogs/machine-learning/using-streaming-ingestion-with-amazon-sagemaker-feature-store-to-make-ml-backed-decisions-in-near-real-time/
* [Image: Image.jpg]



# 개발자 가이드

## Feature Group


개념도

* [Image: Image.jpg]


When you create a new feature group you can choose one of the following table formats:
AWS Glue (Default)
Apache Iceberg

Ingesting data, especially when streaming, can result in a large number of small files deposited into the offline store. This can negatively impact query performance due the higher number of file operations required. To avoid potential performance issues, use the Apache Iceberg table format when creating new feature groups. With Iceberg you can compact the small data files into fewer large files in the partition, resulting in significantly faster queries. This compaction operation is concurrent and does not affect ongoing read and write operations on the feature group. If you choose the Iceberg option when creating new feature groups, Amazon SageMaker Feature Store will create the Iceberg tables using Parquet file format, and register the tables with the AWS Glue Data Catalog.

https://docs.aws.amazon.com/sagemaker/latest/dg/feature-store-create-feature-group.html



## Prerequisite

* Policy
    * `AmazonSageMakerFeatureStoreAccess`
    * https://docs.aws.amazon.com/sagemaker/latest/dg/feature-store-adding-policies.html






