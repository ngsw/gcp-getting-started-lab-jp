# Anthos Attached Clusters ウォークスルー (DevOps)

<walkthrough-watcher-constant key="region" value="asia-northeast1"></walkthrough-watcher-constant>
<walkthrough-watcher-constant key="zone" value="asia-northeast1-c"></walkthrough-watcher-constant>
<walkthrough-watcher-constant key="vpc" value="anthos-ac"></walkthrough-watcher-constant>
<walkthrough-watcher-constant key="subnet" value="anthos-ac"></walkthrough-watcher-constant>
<walkthrough-watcher-constant key="subnet-range" value="10.128.0.0/16"></walkthrough-watcher-constant>
<walkthrough-watcher-constant key="sa" value="sa-anthos-ac"></walkthrough-watcher-constant>
<walkthrough-watcher-constant key="cluster" value="anthos"></walkthrough-watcher-constant>

## 始めましょう

Anthos Attached Clusters へソフトウェアをデプロイする手順です。

**所要時間**: 約 30 分

**前提条件**:

- Anthos Attached Clusters として Kubernetes クラスタが登録されている。

**[開始]** ボタンをクリックして次のステップに進みます。

## API の有効化

Google Cloud では利用したい機能ごとに、有効化を行う必要があります。
ここでは、以降のハンズオンで利用する機能を事前に有効化しておきます。

```bash
gcloud services enable cloudbuild.googleapis.com sourcerepo.googleapis.com cloudresourcemanager.googleapis.com container.googleapis.com stackdriver.googleapis.com cloudtrace.googleapis.com cloudprofiler.googleapis.com logging.googleapis.com iamcredentials.googleapis.com artifactregistry.googleapis.com
```

`Operation 〜 finished successfully.` と表示が出ることを確認します。

## gcloud コマンドラインツール設定 - [リージョン、ゾーン](https://cloud.google.com/compute/docs/regions-zones?hl=ja)

### **デフォルト リージョンの設定**

リソースを操作するデフォルトのリージョンとして、{{region}} を指定します。

```bash
gcloud config set compute/region {{region}}
```

### **デフォルト ゾーンの設定**

リソースを操作するデフォルトのゾーンとして、{{zone}} を指定します。

```bash
gcloud config set compute/zone {{zone}}
```

