# GPTエンジニア（日本語訳）

本家：https://github.com/AntonOsika/gpt-engineer

**作成したいものを指定して、AIが明確化のために質問し、それを作成します。**

GPTエンジニアは、簡単に適応させ、拡張し、エージェントがどのようにコードを表示させたいかを学ぶように作られています。それはプロンプトに基づいてコードベース全体を生成します。

## プロジェクトの哲学
- 価値を簡単に得られる
- 自分で新しい "AIステップ" を追加するのが簡単で柔軟。`steps.py` を参照。
- 次のユーザーエクスペリエンスに向けて徐々に構築する：
  1. 高レベルのプロンプト
  2. 時間の経過とともにAIが覚えてくれるフィードバックを与える
- AIと人間の間で素早く引き継ぎができる
- シンプルさ。全ての計算は "再開可能" で、ファイルシステムに保存される。

## 使い方

**セットアップ**:

- `pip install -r requirements.txt`
- GPT4アクセスがあるキーで `export OPENAI_API_KEY=[your api key]`

**実行**:
- `main_prompt` ファイルがある新しい空フォルダを作成する（または`example`フォルダをコピーして`cp example -r my-new-project`）
- 新しいフォルダの `main_prompt` を記入する
- `python main.py my-new-project` を実行する

**結果**:
- 生成されたファイルは my-new-project/workspace で確認できます

### 制約
追加の連鎖思考プロンプトを実装することで、例えば [Reflexion](https://github.com/noahshinn024/reflexion) を使用することで、メインプロンプトでリクエストされた機能を見逃さないように、より信頼性を高めることができます。

コントリビューター大歓迎！ 何を追加すればよいかわからない場合は、GitHubリポジトリのProjectsタブにあるアイデアをご覧ください。


## 機能
AIエージェントの "アイデンティティ" を `identity` フォルダ内のファイルを編集することで指定できます。

アイデンティティを編集し、main_promptを進化させることで、現在はプロジェクト間でエージェントが物事を覚える方法です。

steps.py の各ステップは、GPT4との通信履歴がlogsフォルダに保存され、scripts/rerun_edited_message_logs.pyで再実行できます。

## デモ

https://github.com/AntonOsika/gpt-engineer/assets/4467025/6e362e45-4a94-4b0d-973d-393a31d92d9b


h-k-nyosuによる追記：

main_promptに記載する内容をChatGPTなどを通して、具体的な要件定義まで落とし込むと精度が上がります。
`example/main_prompt` に記載してある例は、以下のやり取りを通して作成されたものです。

https://chat.openai.com/share/db2c856b-3ace-4000-b73f-12d4730def83

実行方法

```sh
python main.py example
```

作成後のアプリ確認

```sh
python example/main.py
```
