# OpenAI

## 各モデルと料金体系

### GPT-4 Turbo

128k コンテキスト、より新鮮な知識、および最も広範な機能セットを備えた GPT-4 Turbo は、GPT-4 よりも強力であり、低価格で提供されます。

| モデル名 | 料金(Input) | 料金(Output) |
| --- | --- | --- |
| gpt-4-0125-preview | $0.01 / 1K tokens | $0.03 / 1K tokens |
| gpt-4-1106-preview | $0.01 / 1K tokens | $0.03 / 1K tokens |
| gpt-4-1106-vision-preview | $0.01 / 1K tokens | $0.03 / 1K tokens |

### GPT-4

幅広い一般知識と専門知識を備えた GPT-4 は、自然言語による複雑な命令に従い、困難な問題を正確に解決できます。

| モデル名 | 料金(Input) | 料金(Output) |
| --- | --- | --- |
| gpt-4 | $0.03 / 1K tokens | $0.06 / 1K tokens |
| gpt-4-32k | $0.06 / 1K tokens | $0.12 / 1K tokens |

### GPT-3.5 Turbo

GPT-3.5 Turbo モデルは、高機能でコスト効率に優れています。gpt-3.5-turbo-0125 はこのファミリーの主力モデルで、16K コンテキスト ウィンドウをサポートし、ダイアログ用に最適化されています。gpt-3.5-turbo-instruct は Instruct モデルであり、4K コンテキスト ウィンドウのみをサポートします。

| モデル名 | 料金(Input) | 料金(Output) |
| --- | --- | --- |
| gpt-3.5-turbo-0125 | $0.0005 / 1K tokens | $0.0015 / 1K tokens |
| gpt-3.5-turbo-instruct | $0.0015 / 1K tokens | $0.0020 / 1K tokens |

+ [OpenAI Pricing](https://openai.com/pricing)　※2024/2/19時点

## OpenAI API

### APIの種類

| API | 概要 |
| --- | --- |
| Audio | 音声をテキストに、またはテキストを音声に変換する方法を学びます |
| Chat | 会話を構成するメッセージのリストが与えられると、モデルは応答を返します |
| Embeddings | 機械学習モデルとアルゴリズムで簡単に利用できる、特定の入力のベクトル表現を取得します |
| Fine-tuning | 微調整ジョブを管理して、モデルを特定のトレーニング データに合わせて調整します |
| Files | ファイルは、アシスタントや微調整などの機能で使用できるドキュメントをアップロードするために使用されます |
| Images | プロンプトや入力画像が与えられると、モデルは新しい画像を生成します |
| Models | API で利用可能なさまざまなモデルをリストして説明します |
| Moderations | 入力テキストを指定すると、モデルがそれを OpenAI のコンテンツ ポリシーに違反していると分類した場合に出力します |

+ [OpenAI API Reference](https://platform.openai.com/docs/api-reference)

### Chat

#### Request Body

| パラメータ名 | 型 | 必須 | デフォルト | 内容 |
| --- | --- | :---: | --- | --- |
| model | string | ○ | なし | 使用するモデルのID |
| messages | array | ○ | なし | 文章を生成させる際の指示を記述 |
| temperature | number(0~2) | | 1 | 生成されるテキストの「創造性」や「ランダム性」を制御するために設定し、値が低いと生成テキストはまじめで実用的で、値が高いほど生成テキストはランダムになる |
| top_p | number(0~1) | | 1 | 文章の多様性と一貫性を調整するパラメータで、値が低いほど次に来る単語の選択肢を絞り込み、可能性が高い単語やフレーズを選ぶようになる |
| n | number | | 1 | 回答数を指定する（「３」としたら回答が３つ得られる） |
| steam | boolean | | false | 回答をリアルタイムに返してもらうかを設定し、trueは一部ずつ結果が返ってきて、falseは文章をすべて生成してから一度に返す |
| stop | string or array | | null | 生成される文章の中に指定した文字列が現れたら、そこで出力を停止するためのパラメータ（最大４つ） |
| max_tokens | integer | | (モデルの最大トークン数) | 回答の長さをコントロールするパラメータ（最大トークン数＝入力文章のトークン数＋出力文章のトークン数） |
| presence_penalty | number(-2~2) | | 0 | 同じ単語やフレーズを頻繁に繰り返すことを制御するパラメータで、値が高いと新しい単語やフレーズが出現し、値が低いと既出の単語やフレーズが繰り返される可能性が高くなる |
| frequency_penalty | number(-2~2) | | 0 | presence_penaltyと同様だが、presence_penaltyは文章中に一度でも使われた単語やフレーズに影響し、frequency_penaltyは文章中の単語やフレーズの出現頻度に影響を与える |
| logit_bias | map | | null | 生成する文章において、特定の単語やフレーズが出現する確率を操作するパラメータ |
| user | string | | なし | エンドユーザーを表す一意の識別子で、OpenAIによる不正行為の監視と検出に使用 |

+ [Create chat completion](https://platform.openai.com/docs/api-reference/chat/create)