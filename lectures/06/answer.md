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
  VS Code の 1 つのウィンドウから、自分で作った用語集サーバー、公開されている fetch サーバー、AWS が動かしているサーバーを、同じエージェントでまとめて使えるのが面白かった。コードは書かず、`app/mcp_servers.json` に数行足すだけで済んだ。
  一方で、サーバーを足すたびにツールが増え（最後は 7 個）、入力トークン数も STEP 2 の 709 から STEP 4 の 11,254 まで増えた。便利な反面、何個のツールを渡しているかを意識する必要があると感じた。

## 宿題

<!-- 基礎・実装・発展のどれか1つに取り組めば完了です。 -->

- 取り組んだレベル：基礎 / 実装 / 発展
- やったこと：
- 結果：
- 気づき・疑問：
