﻿---
lab:
    title: 'データ ストレージとデータ処理の監視とトラブルシューティング'
    module: 'モジュール 09: データ ストレージとデータ処理の監視とトラブルシューティング'
---

# DP 200 - データ プラットフォーム ソリューションの実装
# ラボ 9 - データ ストレージとデータ処理の監視とトラブルシューティング

**所要時間**: 75 分

**前提条件**: このラボのケース スタディは既に確認していることを前提としています。本ラボは、モジュール 1 から 7 の内容と演習が完了したことを前提としています。

**ラボ ファイル**: このラボのファイルは、_Allfiles\Labfiles\Starter\DP-200.9_のフォルダーにあります。

## ラボの概要

受講者は、データ エステートで発生しうる問題を監視するのに役立つ広範な監視ソリューションを定義できるようになります。その後、クラウド データ ソリューションで発生しうる一般的なデータ ストレージの問題とデータ処理の問題が発生します。最後に、受講者はデータ プラットフォーム テクノロジーのディザスター リカバリー アプローチを実装します。

## ラボの目的
  
このモジュールを修了すると、次のことができるようになります:

1. 使用可能な監視機能について説明する
1. データ ストレージに関する一般的な問題のトラブルシューティングを行う
1. データ処理に関する一般的な問題のトラブルシューティングを行う
1. ディザスター リカバリーを管理する

## シナリオ
  
あなたは、AdventureWorks のシニア データ エンジニアとして、組織内のデータ エステートを監視するための標準的な運用手順を定義する任務を負っています。まず、このアプローチをサポートするために使用する監視ツールを定義します。

次に、インフラストラクチャの通常の運用中に発生しうる一般的なデータ ストレージとデータ処理の問題の一部を確認します。

awcdbstudxx Cosmos DB に保存されている製品データベースのリカバリーに関する懸念が存在します。IS 部門は、誤ってデータベースを削除または移動して製品データベースが使用できなくなった場合に実行される高レベルの手順を提供するよう求めています。

このラボを完了すると:

1. 使用可能な監視機能について説明する
1. データ ストレージに関する一般的な問題のトラブルシューティングを行う
1. データ処理に関する一般的な問題のトラブルシューティングを行う
1. ディザスター リカバリーを管理する

## エクササイズ 0: 問題のレビュー

> **重要**: このラボでは、_\Labfiles\DP-200-Issues-Docx_ にあるドキュメントのすべてのラボでのプロビジョニングまたは構成タスクで発生した問題を参照します。次のエクササイズに備え、このドキュメントを開いて準備します。

## エクササイズ 1: 使用可能な監視機能について説明する

所要時間: 15 分

グループ エクササイズ
  
このエクササイズの主なタスク:

1. 企業の監視アプローチを定義する。

1. インストラクターは、調査結果についてグループと話し合います。

### タスク 1: 企業の監視アプローチを定義する。

1. ラボの仮想マシンから **Microsoft Word** を起動し、**Allfiles\Labfiles\Starter\DP-200.** フォルダーからファイル **DP-200-Lab09-Ex01.docx** を開きます。

1. グループで **10 分間** 話し合い、組織内で最も役立つツールである監視ツールを特定します。2 つの例を使い、正当化の理由を説明します。

### タスク 2: 調査結果についてインストラクターと話し合う

1. インストラクターは、調査結果について話し合うためにグループ作業を中断させます。

> **結果**: このエクササイズを完了すると、組織内で最も便利なツールとなる監視ツールを特定する Microsoft Word ドキュメントが作成されます。

## エクササイズ 2: データ ストレージに関する一般的な問題のトラブルシューティングを行う
  
所要時間: 20 分

グループ エクササイズ
  
このエクササイズの主なタスク:

1. データ ストレージの問題を評価する。

1. インストラクターは、調査結果についてグループと話し合います。

### タスク 1: データとストレージのセキュリティ衛生を評価する。

1. **\Labfiles\DP-200-Issues-Doc.docx**_ ドキュメントで、調査結果を共有し、グループと協力してデータ ストレージの問題を特定します。

1. グループと協力して、さまざまなデータ プラットフォームのセットアップ中にグループが経験した **一般的なデータ ストレージの問題** があるかどうかを確認します。

1. グループで、確認されたデータ ストレージの問題 2 つを選択し、ドキュメント **DP-200-Lab09-Ex02.docx** にログインします。

### タスク 2: 調査結果についてインストラクターと話し合う

1. インストラクターは、調査結果について話し合うためにグループ作業を中断させます。

> **結果**: このエクササイズが完了すると、データ ストレージの問題 2 つを示す Microsoft Word ドキュメントが作成されます。

## エクササイズ 3: データ処理に関する一般的な問題のトラブルシューティングを行う
  
所要時間: 20 分

グループ エクササイズ
  
このエクササイズの主なタスク:

1. データ処理の問題を評価する。

1. インストラクターは、調査結果についてグループと話し合います。

### タスク 1: データとストレージのセキュリティ衛生を評価する。

1. **DP-200-Lab09-Ex03.docx** に記載されている質問をグループで確認します

1. グループと協力して、さまざまなデータ プラットフォームのセットアップ中にグループが経験した **一般的なデータ処理の問題** があるかどうかを確認します。

1. グループで、確認されたデータ ストレージの問題 2 つを選択し、ドキュメント **DP-200-Lab09-Ex02.docx** にログインします。

### タスク 2: 調査結果についてインストラクターと話し合う

1. インストラクターは、調査結果について話し合うためにグループ作業を中断させます。

> **結果**: このエクササイズが完了すると、データ処理の問題 2 つを示す Microsoft Word ドキュメントが作成されます。

## エクササイズ 4: ディザスター リカバリーを管理する
  
所要時間: 20 分

グループ エクササイズ
  
このエクササイズの主なタスク:

1. ディザスター リカバリーを管理する。

1. インストラクターは、調査結果についてグループと話し合います。

### タスク 1: ディザスター リカバリーを管理する。

1. ラボの仮想マシンから **Microsoft Word** を起動し、**Allfiles\Labfiles\Starter\DP-200.9** フォルダーからファイル **DP-200-Lab09-Ex04.docx** を開きます。

1. ケース スタディ ドキュメント内でグループが特定したデータ要件とデータ構造について、グループで **10 分間** 話し合い、書き出してもらいます。

### タスク 2: 調査結果についてインストラクターと話し合う

1. インストラクターは、調査結果について話し合うためにグループ作業を中断させます。

> **結果**: このエクササイズを完了すると、製品データベースの復元に必要な高レベルの手順の概要を説明する Microsoft Word ドキュメントが作成されます。