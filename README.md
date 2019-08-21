# CodePipeline_YS
##  本リポジトリについて
本リポジトリはAWSチュートリアルをベースにデプロイ実施時にECRのURIも同時に作成されるように\
Blue/Greenデプロイの環境を構築を実施したものとなります。

チュートリアル：Amazon ECR ソースと、ECS と CodeDeploy 間のデプロイでパイプラインを作成する\
https://docs.aws.amazon.com/ja_jp/codepipeline/latest/userguide/tutorials-ecs-ecr-codedeploy.html

##  実施内容
nginx＋tomcat連携を行っているコンテナをECS＋Fargateで構築。\
GitHubが更新される度にCodePipelineからCodeBuild,CodeDeployが自動で開始されBlue/Greenデプロイを実施する。

##  フォルダ構造
- nginx
  - conf
    - default.conf
  - Dockerfile
  - buildspec.yml
- tomcat
  - conf
    - ROOT
      - index.html
    - server.xml
  - Dockerfile
    - buildspec.yml
  - appspec.yaml
  - create-service.json
  - taskdef.json
  
##  参考サイト
CodeDeploy AppSpec File リファレンス\
https://docs.aws.amazon.com/ja_jp/codedeploy/latest/userguide/reference-appspec-file.html

CodeBuild のビルド仕様に関するリファレンス\
https://docs.aws.amazon.com/ja_jp/codebuild/latest/userguide/build-spec-ref.html

Amazon Elastic Container Service(タスク定義パラメータ)\
https://docs.aws.amazon.com/ja_jp/AmazonECS/latest/developerguide/task_definition_parameters.html

Amazon Elastic Container Service(サービス定義パラメータ)\
https://docs.aws.amazon.com/ja_jp/AmazonECS/latest/developerguide/service_definition_parameters.html
