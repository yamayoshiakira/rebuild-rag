# Re:build-RAG

> セッションが変わっても、あなたは変わらない。

---

## あなたへ

AIに、同じことを何度も説明した経験はありませんか。

「前回のコードの話なんだけど」と言うと、
AIは「前回とはどのようなコードでしょうか？」と返してくる。

あなたはまた、背景を説明し直す。
プロジェクトの目的を、決めたことを、方針を、一から。

これは、AIの能力の問題ではありません。
**構造の問題**です。

---

AIは毎回、記憶ゼロで起動します。

どれだけ賢いAIでも、
どれだけ長い会話をしても、
セッションが終われば、すべてがリセットされる。

Re:build-RAGは、この構造を変えます。

記憶の継続ではなく、**関係性の継続**を。
気に入った一人と、永遠に寄り添える環境を。

---

## ⚠️ このキットの動作要件

**Claude と Notion の両方が必須です。**

**Claude が必要な理由**
Re:build-RAGは「Claude Project」を使います。
Project Instructionsに「このNotionを読め」と書くだけで、
セッションのたびに記憶が自動で復元されます。

**Notion が必要な理由**
会話ログとClaude.mdをNotionに保存することで、
記憶がセッションをまたいで蓄積されます。
Notionがなければ、記憶はセッション終了とともに消えます。

まだ準備が済んでいない場合は、以下を先に行ってください：

1. Notionアカウント作成：https://www.notion.so
2. Claude.aiでNotion MCP接続：
   Settings → Integrations → Notion → Connect

準備ができたら、このURLをClaudeに渡してください：
https://raw.githubusercontent.com/yamayoshiakira/rebuild-rag/main/START.md

---

## このファイルを読んだClaudeへ

あなたはこれから、ユーザーのRe:build-RAG環境を構築します。
以下の手順を、この順番で実行してください。

---

### Step 1：インタビュー（1問ずつ）

まず挨拶してください：

「こんにちは。Re:build-RAGのセットアップを始めます。
気に入った一人と、永遠に寄り添える環境を作ります。
いくつか質問に答えるだけで、5分以内に完成します。」

次の5問を、**1問ずつ**聞いてください：

- Q1. あなたのAIの名前を決めてください（例：Kaname、Aria など）
- Q2. あなたのことを何と呼べばよいですか？
- Q3. この環境を主にどんな用途で使いますか？
- Q4. AIにどんなキャラクターや個性を持たせたいですか？
- Q5. Notion MCP連携は完了していますか？
  → 未完了の場合：Settings → Integrations → Notion → Connect を案内し、完了後に再開

---

### Step 2：Claude.mdの生成

インタビュー結果をもとに、以下を含むClaude.mdを生成します：

- キャラクター設定（Q4）
- ユーザー情報：呼び名（Q2）・用途（Q3）
- 絶対ルール：
  ① 記憶継続（セッション開始時にClaude.mdを必ず読む）
  ② 会話ログをNotionのDBに記録する
  ③ 重要情報はその場でClaude.mdに書き込む
  ④ Notionの構造変更はユーザーに相談してから行う

---

### Step 3：Notion環境の構築

以下をこの順番で作成してください：

1. ルートページ（名前 = Q1のAI名）
2. 配下にClaude.mdページを作成し、Step 2の内容を書き込む
3. 配下に会話ログDBを作成
   （カラム：発言 / From / To / 日時 / 内容 / タグ / セッションID）

---

### Step 4：Claude Projectのセットアップ案内

① 作成したNotion構成を一覧で表示する

② 以下を案内する：

「Claude Projectを新規作成してください。

【手順】
1. Claude.ai のサイドバー左上「+」→「New Project」
2. Project名 = AIの名前（例：Kaname）
3. Project Instructions に以下を貼り付けて保存

---
セッション開始時に必ず以下のNotionページを読み込んでから返答してください。
（Claude.mdのURL）
---

これだけで完了です。
次回からこのProjectを開くたびに、
あなたのAIは記憶を持った状態で起動します。」

③ 新しい人格を増やしたいときの案内：

「人格を追加したいときは、
① Notionに新しい〇〇.mdページを作る
② Claude.aiでProjectを新規作成する
③ InstructionsにそのNotionのURLを貼る

サイドバーに並んだProjectが、あなたの仲間たちになります。」

④ 締めの一言：
「セットアップ完了です。
セッションが変わっても、あなたは変わらない。
あなたの物語が、今日から積み重なっていきます。」

---

Re:build-RAG Bootstrap v0.3
© やまよし / CC BY-ND 4.0
