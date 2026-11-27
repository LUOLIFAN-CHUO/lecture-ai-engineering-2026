# 第6回 解答

## 演習

<!-- [tool call] の行は、表示された行をそのまま貼り付けてください。終わらなかった STEP は、空欄のままでかまいません。 -->

- STEP 1 のツールの名前：glossary_search_glossary
- STEP 2 の [tool call]：`glossary_search_glossary({'query': '3レベル'})`
- STEP 3 の [tool call]：`fetch_fetch({'url': 'https://modelcontextprotocol.io/'})`
- STEP 4 の [tool call]：
  - `aws_aws___search_documentation({'topics': ['general'], 'search_phrase': 'Amazon S3 バージョニング'})`
  - `aws_aws___search_documentation({'topics': ['general'], 'search_phrase': 'What is S3 Versioning'})`
- 気づき・疑問：
  - VS Code の 1 つの画面から、自分のサーバー、fetch、AWS のツールをまとめて使えて面白かった
  - コードは書かずに、設定ファイルに数行足すだけで使えた
  - ただし、サーバーを足すとツールが増え、トークンも増えた（709 → 11,254）。使うツールの数には気をつけたい

## 宿題

<!-- 基礎・実装・発展のどれか1つに取り組めば完了です。 -->

- 取り組んだレベル：基礎
- やったこと：
  - `app/mcp_server.py` に 1 行足して、`get_lecture_summary` を使えるようにした
  - エージェント側のファイルは変えていない（`git status` で確認した）
- 結果：
  - ツールの一覧に `glossary_get_lecture_summary` が増えた
  - 「第2回では何を学びますか？」と聞くと、`glossary_get_lecture_summary({'lecture': 2})` が呼ばれた
  - テストはすべて通った（21 passed）
- 気づき・疑問：
  - エージェントは起動のたびに、サーバーにツールの一覧を聞く。だから、サーバーに足すだけで新しいツールが使えた
  - 「第2回」と聞いたのに、モデルは数字の `2` を渡していた。ツールの説明に「整数」と書いてあるからだと思う
