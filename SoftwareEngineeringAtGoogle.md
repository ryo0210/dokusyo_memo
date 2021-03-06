# Googleのソフトウェアエンジニアリング

![Book Cover](https://github.com/ryo0210/dokusyo_memo/blob/main/BookCover/SoftwareEngineeringAtGoogle.jpg)

### 12章　ユニットテスト

- 12.1　保守性の重要さ

- 12.2　脆いテストを防ぐ

  - 12.2.1　変化しないテストを目指す

    - 理想的なテストとは、システムの要件が変わらない限り変更の必要がないもの

  - 12.2.2　公開API経由のテスト

    - システムの内部的詳細部分に対してではなく、実際のユーザーが行うであろう挙動に対してをテストする

  - 12.2.3　相互作用ではなく、状態をテストせよ

    - どのように（How）システムがその結果に到達したかではなく、結果が何（What）であるかだけを意識して検証する

- 12.3　明確なテストを書く

  - 12.3.1　テストは完全かつ簡潔にせよ

    - どのようにしてその結果になったのかの全情報を含んでいる場合、そのテストは完全である
    - 無関係な情報が含まれていない場合、そのテストに簡潔である

  - 12.3.2　メソッドではなく、挙動をテストせよ

    - 挙動は「〜という条件下で（given）」「〜の場合（when）」「その場合〜（then）」で表せる
    - 優れたテストの名称は、動作と期待される結果の両方を説明する
    - describeを使って色子状にして命名する方法もある
    - テスト名が長くなったとしても、本番環境ではテストメソッドが呼ばれることはなく、テスト失敗時に人間が読まなければいけないことが頻繁にあるので、冗長さは正当化される

  - 12.3.3　テストにロジックを入れるな

    - テストが説明できて意味がわかりやすいものになるなら、気の利いたロジックは要らず、ある程度の重複は黙認を検討する

  - 12.3.4　明確な失敗メッセージを書け

    - 失敗メッセージは期待される結果、実際の結果、関連する要因全てを明確に表現するべきである

- 12.4　テストとコード共有：DRYではなくDAMP

  - システムが変更された場合は、テストが破綻することが望ましいので、DRYではなく、DAMP（説明的で意味が分かりやすい）を目指すべきである

  - 12.4.1　共有値

    - テストに必要な値のみを指定し、他の全ての値には妥当なデフォルト値を設定するヘルパーメソッドを用意してデータを構築することで、詳細を隠しながら説明的さを保てる

  - 12.4.2　初期設定の共有

    - 特定の値に関心を持つテストでは、すでに定義された値をオーバーライドしてテストの近くに書くことで多少繰り返しになったとしても、はるかに説明的かつ意味が分かりやすくなる

  - 12.4.3　ヘルパーメソッドと検証メソッドの共有
  - 12.4.4　テストインフラストラクチャーを定義する