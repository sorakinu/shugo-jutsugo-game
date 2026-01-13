主語・述語ゲーム（Subject-Predicate Matcher）
言葉の組み合わせを楽しく学べる、シンプルなPythonプログラムです。 正解するとAI先生から心のこもった感謝のメッセージが届きます。

📝 アプリの概要
バラバラになった「主語」と「述語」を正しく組み合わせて、正しい文章を作るクイズゲームです。 楽しみながら日本語の構成を学ぶことができます。

🚀 使い方
## 必要な環境
- Python 3.6 以上

## 実行方法
1. このリポジトリをダウンロード
2. ターミナル（コマンドプロンプト）で以下を実行：
   ```bash
   python game.py

## オンラインで遊ぶ
ブラウザで今すぐ遊べます：
👉 [Replit で遊ぶで遊ぶ](https://replit.com/@sorakinu/shugo-jutsugo-game-1)

## ローカルで遊ぶ
Python がインストールされている方は：
```bash
python game.py

import random

# 複数の問題セットを用意
question_sets = [
    # セット1: 日常生活
    {
        "name": "日常生活",
        "sentences": [
            ("ぼくは", "宿題をしました。"),
            ("お母さんが", "料理をします。"),
            ("犬が", "走りました。"),
            ("先生が", "教えています。")
        ]
    },
    # セット2: 自然・季節
    {
        "name": "自然・季節",
        "sentences": [
            ("花が", "咲きました。"),
            ("雪が", "降っています。"),
            ("太陽が", "輝いています。"),
            ("風が", "吹いています。")
        ]
    },
    # セット3: 動物
    {
        "name": "動物",
        "sentences": [
            ("鳥が", "飛んでいます。"),
            ("魚が", "泳いでいます。"),
            ("猫が", "寝ています。"),
            ("うさぎが", "跳ねました。")
        ]
    },
    # セット4: 学校
    {
        "name": "学校",
        "sentences": [
            ("友だちが", "遊んでいます。"),
            ("図書館で", "本を読みました。"),
            ("体育館で", "運動をします。"),
            ("教室で", "勉強しています。")
        ]
    },
    # セット5: 家族
    {
        "name": "家族",
        "sentences": [
            ("お父さんが", "働いています。"),
            ("妹が", "歌っています。"),
            ("おばあちゃんが", "笑いました。"),
            ("弟が", "泣いています。")
        ]
    }
]

# ランダムに1つの問題セットを選ぶ
selected_set = random.choice(question_sets)
correct_sentences = selected_set["sentences"]
theme = selected_set["name"]

# リストを分離
subjects = [pair[0] for pair in correct_sentences]
predicates = [pair[1] for pair in correct_sentences]

# シャッフル
random.shuffle(subjects)
random.shuffle(predicates)

print("=" * 50)
print("    主語と述語を正しく組み合わせてね！")
print("=" * 50)
print(f"\n✨ 今回のテーマ： 【{theme}】 ✨\n")

print("【主語】")
for i, s in enumerate(subjects):
    print(f"  {i+1}: {s}")

print("\n【述語】")
for j, p in enumerate(predicates):
    print(f"  {j+1}: {p}")

print("\n" + "-" * 50)

try:
    user_s = int(input("主語の番号を選んでください (1-4): ")) - 1
    user_p = int(input("述語の番号を選んでください (1-4): ")) - 1

    # 範囲チェック
    if user_s < 0 or user_s >= len(subjects) or user_p < 0 or user_p >= len(predicates):
        print("\n❌ 番号は 1〜4 の範囲で選んでください！")
    else:
        chosen_subject = subjects[user_s]
        chosen_predicate = predicates[user_p]
        
        # 正解判定
        is_correct = (chosen_subject, chosen_predicate) in correct_sentences
        
        print("\n" + "=" * 50)
        print(f"あなたの答え： 「{chosen_subject}{chosen_predicate}」")
        print("=" * 50)
        
        if is_correct:
            print("\n🌸 正解！すばらしいね！🌸")
            print("\n💌 AI先生からのお手紙：")
            print("　今日も挑戦してくれてありがとう。")
            print("　間違えても、学ぶ姿がとても立派です。")
        else:
            print("\n❌ 残念、もういちど考えてみよう！")
            print("　ヒント：文として自然になる組み合わせを探してね")
            
except ValueError:
    print("\n❌ 入力は数字でお願いします！")
except Exception as e:
    print(f"\n❌ エラーが発生しました: {e}")

print("\n" + "=" * 50)
print("      ゲーム終了！また挑戦してね！")
print(f"      次回は違うテーマが出るかも...？")
print("=" * 50)
## ⚠️ 注意点

**コンソールが見えない場合:**
- 「Console」タブをクリック
- 黒い画面が表示されます
遊び方
画面に表示される主語と述語のリストから番号を選ぶ
正しい組み合わせを作って文章を完成させよう！

対象
日本語を学んでいる子どもたち
主語・述語の関係を楽しく学びたい方

正解すると、AI先生からのメッセージが表示されます！

🛡️ 個人情報保護とセキュリティについて
本プログラムをご利用いただく際のプライバシー保護について以下の通り定義しています。

データの収集: 本アプリは、ユーザー名、メールアドレス、その他の個人情報を一切収集しません。

入力データの取り扱い: 入力された番号は、その場の正誤判定にのみ使用され、外部サーバーに送信されたり、保存されたりすることはありません。

安全性: 外部ライブラリを使用せず、標準的なPython機能のみで動作するため、安全に実行いただけます。

🛠️ 開発環境

使用ライブラリ: random (標準ライブラリ)

⚖️ ライセンス
このプロジェクトは MITライセンス の下で公開されています。 個人利用・商用利用を問わず、自由に使用・改変・配布いただけます。
