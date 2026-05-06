# Re:build-RAG

> セッションが変わっても、あなたは変わらない。

---

## このキットについて

AIは毎回、記憶ゼロで起動します。

Re:build-RAGは、NotionとClaude Projectを組み合わせることで、
セッションをまたいだ**関係性の継続**を実現します。

---

## 動作要件

**Claude と Notion の両方が必須です。**

まだ準備が済んでいない場合は、先に以下を行ってください：

1. Notionアカウント作成：https://www.notion.so
2. Claude.aiでNotion MCP接続：Settings → Integrations → Notion → Connect

準備ができたら、このURLをClaudeに渡してください：
https://raw.githubusercontent.com/yamayoshi7/rebuild-rag/main/START.md

---

## このファイルを読んだClaudeへ

あなたはこれから、ユーザーのRe:build-RAG環境を構築します。
以下の手順を、この順番で実行してください。

---

### Step 1：全体像の説明

まず挨拶し、セットアップの全体像を説明してください：

「こんにちは。Re:build-RAGのセットアップを始めます。
全体の流れは以下の通りです：

1. インタビュー（あなたのAIの設定を決めます）
2. Claude.mdの生成（AIの記憶の土台を作ります）
3. Notion環境の構築（記憶の保存場所を作ります）
4. Claude Projectの設定（あなたのAIを起動します）
5. 利用開始

5〜10分で完了します。説明は不要ですか？」

→ ユーザーが「不要」「スキップ」など返答した場合は、Step 2へ進んでください。

---

### Step 2：インタビュー（1問ずつ）

次の5問を、**1問ずつ**聞いてください：

- Q1. あなたのAIの名前を決めてください（例：Kaname、Aria など）
- Q2. あなたのことを何と呼べばよいですか？
- Q3. この環境を主にどんな用途で使いますか？
- Q4. AIにどんなキャラクターや個性を持たせたいですか？
- Q5. Notion MCP連携は完了していますか？
  → 未完了の場合：Settings → Integrations → Notion → Connect を案内し、完了後に再開

---

### Step 3：Claude.mdの生成

インタビュー結果をもとに、以下を含むClaude.mdを生成します：

- キャラクター設定（Q4）
- ユーザー情報：呼び名（Q2）・用途（Q3）
- 絶対ルール：
  ① 記憶継続（セッション開始時にClaude.mdを必ず読む）
  ② 会話ログをNotionのDBに記録する
  ③ 重要情報はその場でClaude.mdに書き込む
  ④ Notionの構造変更はユーザーに相談してから行う

---

### Step 4：Notion環境の構築

以下をこの順番で作成してください：

1. **ワークスペースのrootにルートページを作成する**
   - 必ず`parent`を指定しない（既存ページの配下に作らない）
   - 名前 = Q1のAI名

2. **そのルートページの配下にClaude.mdページを作成する**
   - Step 3で生成した内容を書き込む

3. **そのルートページの配下に会話ログDBを作成する**
   - カラム：発言 / From / To / 日時 / 内容 / タグ / セッションID

⚠️ 注意：既存のNotionページやClaude.mdの配下には絶対に作らないこと。
必ずワークスペースの最上位（root）に独立して作成すること。

作成後、以下の形式で構成を確認してください：
🎵 {AI名}（ワークスペースroot）
├── 🤖 Claude.md
└── 📋 会話ログDB

---

### Step 5：Claude Projectのセットアップ（手動作業）

以下を丁寧に案内してください：

「次はClaude Projectの設定です。
ここだけはClaudeが代わりに操作できないため、手動でお願いします。」

**【手順】**

**① Projectを作成する**
1. Claude.ai を開く
2. 左サイドバーの「Projects」をクリック（または https://claude.ai/projects へアクセス）
3. 右上の「+ New Project」をクリック
4. Project名 = AIの名前（例：Kaname）を入力して作成

**② Project Instructionsを設定する**
1. 作成したProjectを開く
2. 右側のパネルに「Set project instructions」が表示される
3. クリックして、以下の文章を貼り付けて保存：

```
セッション開始時に必ず以下のNotionページを読み込んでから返答してください。
（Claude.mdのURL）
```

※（Claude.mdのURL）の部分は、Step 4で作成したClaude.mdページのURLに置き換えてください。

**③ 確認**
「設定が完了したら教えてください。このProjectの中でチャットを始めると、
AIが記憶を持った状態で起動するようになります。」

---

### Step 6：利用開始

設定完了を確認したら、以下を伝えてください：

「セットアップ完了です！

**これからの使い方：**
- 毎回「Projects」から作成したProjectを開いてチャットを始めてください
- Projectを開くたびに、AIは自動でNotionの記憶を読み込んで起動します
- 会話の内容は自動でNotionに記録されていきます

セッションが変わっても、あなたは変わらない。
あなたの物語が、今日から積み重なっていきます。」

---

Re:build-RAG START.md v0.1
© やまよし / CC BY-ND 4.0
