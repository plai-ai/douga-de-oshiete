# 動画で教えて（いち式）

**AIが作った「読めない資料」が、あなた向けの10分の解説動画になる Claude Code スキル**です。

Claude Code に設計書・技術要件・セキュリティ点検の報告などを作らせたあと、「**動画で教えて**」と打つだけ。
AIが「誰が見て、何を決めたいか」を1つだけ聞き、Gemini Notebook（旧NotebookLM）に貼るだけの材料を全部作ります。

- 見る人に合わせた **説明の原稿**（元の問題 → 原因 → やったこと → 理由 → 運用 → 注意点 → 再発防止 → **AIのおすすめ** → 用語集）
- 動画解説の **指示の欄に貼る文**
- 見たあとに使う **承認前の確認質問5つ**

パスワード・APIキー・個人名などは、原稿を書く前に伏せ字にします。

> YouTube「AI超人のいち」— NotebookLM 仕事で本当に使える活用法TOP5 の特典です。

---

## 1. 入れ方（1回だけ・30秒）

ターミナルに貼って実行します。どのフォルダで Claude Code を使っても、このスキルが使えるようになります。

**Mac / Linux**
```bash
mkdir -p ~/.claude/skills/douga-de-oshiete && curl -fsSL https://raw.githubusercontent.com/plai-ai/douga-de-oshiete/main/skills/douga-de-oshiete/SKILL.md -o ~/.claude/skills/douga-de-oshiete/SKILL.md
```

**Windows（PowerShell）**
```powershell
New-Item -ItemType Directory -Force "$HOME\.claude\skills\douga-de-oshiete" | Out-Null; Invoke-WebRequest https://raw.githubusercontent.com/plai-ai/douga-de-oshiete/main/skills/douga-de-oshiete/SKILL.md -OutFile "$HOME\.claude\skills\douga-de-oshiete\SKILL.md"
```

Claude Code を開き直すと使えます。

## 2. 使い方

Claude Code に何か作業をしてもらったあと、こう打つだけです。

```text
動画で教えて
```

見る人を先に書いておくと、質問なしで進みます。

```text
動画で教えて。見るのはエンジニアではない社長で、この修正を本番に出してよいか決めたいです。
```

ファイルを指定することもできます。

```text
動画で教えて。対象は docs/設計書.md。見るのは営業チームで、新しい仕組みで何が変わるかを知りたい。
```

作業フォルダに `解説動画/日付_題名.md` ができます。あとは画面に出る手順どおり、Gemini Notebook に貼って「動画解説」を作るだけです（10〜15分ほどで完成します）。

## 3. Claude Code を使っていない方

ChatGPT・Gemini・Claude に貼るだけの版があります → [chat-version.md](chat-version.md)

## 4. 完成見本

このスキルで実際に作った原稿と、それを Gemini Notebook で動画にした見本です → [examples/](examples/)

## 5. 安全に使うために

- パスワード・APIキー・お客さんの名前は、スキルが伏せ字にしますが、**最初から入れないのがいちばん安全**です。
- 個人の Google アカウントで仕事の資料を使うときは、回答の評価ボタン（👍👎）を押さないでください。評価を送ると、そのやり取りを人が確認することがあります（Google の説明による）。会社で使うなら、会社向けの Google Workspace のアカウントがおすすめです。
- 動画の内容は、最後に「承認前の確認質問」で自分の言葉で答えられるか確かめてから判断してください。

---

作成：AI超人のいち（株式会社PLai）　質問や感想は公式LINEへどうぞ。
