# プロジェクトタイトル

42_Road-to-Mercari-Gopher-Dojo-03

## 概要

このプロジェクトは、株式会社メルカリとの共同開発課題です。  
Goについて取り扱います。このプロジェクト群を解き終わると、限定の座談会に招待されます。


## プロジェクトの目的

このプロジェクトは、Go言語でREST APIを設計し、実装することを通じて、Webサーバーの基本的な概念と開発手法を学ぶことを目指します。  
具体的には、ランダムなおみくじ結果を返すAPIの開発を通じて、HTTPプロトコルの理解、JSONデータの扱い、コマンドライン引数の使用、日付と時刻の処理、そしてテスト駆動開発（TDD）の実践が含まれます。  
また、正月期間に特別なレスポンスを返す機能を実装することで、条件分岐とサーバーの現在時刻の使用方法についても学びます。


## チャレンジした点

- Ginフレームワークの導入: Go言語のWebフレームワークであるGinを採用し、APIサーバーの開発に挑戦しました。  
これには、Ginのルーティング、ミドルウェア、コントローラーの概念を理解し、適用する必要がありました。  
- 動的なポート指定: コマンドライン引数を用いて、Ginサーバーがリッスンするポートを動的に指定しました。  
この柔軟性は、実際のデプロイメントシナリオでの利便性を考慮した設計です。
- ランダムなレスポンスの生成と条件分岐: ランダムなおみくじ結果を生成し、特定の期間（正月）には特別なレスポンスを返すロジックをGinで実装しました。  
- これは、Ginフレームワーク内でのデータ処理とロジックの条件分岐を理解する上での重要な挑戦でした。
  
## 学んだこと
- Ginフレームワークを使用したWebサーバーの構築: Ginを使用してREST APIを構築する方法を学び、そのプロセスでルーティング、リクエスト処理、レスポンス生成の効率化を実現しました。
- JSONデータの効率的な扱い: Ginを活用して、JSON形式のレスポンスを簡単に生成し、クライアントへの送信を行う方法を学びました。
Ginの機能を通じて、データのシリアライズとデシリアライズのプロセスを理解しました。
- テストモックの実装方法: 特定の日付や条件下でのAPIの振る舞いをテストするために、テストモックの実装方法を学びました。
特に、正月期間の挙動をテストするために、日付を人為的に操作するモックの使用方法を習得しました。
これにより、実際のシステム時刻に依存せずに、年始の特別なレスポンスを返すロジックを確実にテストすることが可能になりました。


## 使用方法

> - **ex00**
> ```bash php
> #!/bin/bash
> cd ex00
> go build
> ./omikuji 4242 (使用可能な任意のポートでサーバーが起動するのでlocalhostでそちらにアクセスしてみてください)
> ```

> - **サーバーが立ち上がっている状態で**
> ```bash php
> #!/bin/bash
> curl localhost:4242
> {"fortune":"Kyo","health":"You will fully recover, but stay attentive after you do.","residence": "
You will have good fortune with a new house.","travel":"When traveling, you may find something
to treasure.","study":"Things will be better. It may be worth aiming for a school in a
different area.","love":"The person you are looking for is very close to you."}　(このように出力されます)
> ```

> - **ex00 test**
> ```bash php
> #!/bin/bash
> go test -cover (testのカバー率が出ます)
> ```

## 技術スタック

Go言語
