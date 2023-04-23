# Linuxコマンド

## ファイル操作

### コピー
|                      コマンド                      | オブション |                        内容                        |
| -------------------------------------------------- | ---------- | -------------------------------------------------- |
| cp [source file] [dist file]                       | -          | [source file]を[dist file]の名前でファイルをコピー |
| cp [source file1] [source file2] ... [dist folder] | -          | 各[source file]を[dist folder]へファイルをコピー   |

### 移動、リネーム
|                      コマンド                      | オブション |                       内容                       |              備考              |
| -------------------------------------------------- | ---------- | ------------------------------------------------ | ------------------------------ |
| mv [source file] [dist file]                       | -          | [source file]を[dist file]の名前でファイルを移動 | 同じフォルダならリネームとなる |
| mv [source file1] [source file2] ... [dist folder] | -          | 各[source file]を[dist folder]へファイルを移動   |                                |

### 削除
|          コマンド          | オブション |           内容           |               備考               |
| -------------------------- | ---------- | ------------------------ | -------------------------------- |
| rm [file1] [file2] ...     | -          | 各[file]ファイルを削除   |                                  |
| rm [folder1] [folder2] ... | -r         | 各[folder]フォルダを削除 | 各フォルダにあるファイルごと削除 |

## ネットワーク

### データ送受信

#### curl
さまざなプロトコルを用いてデータを送受信する。

|  コマンド  |   オブション   |               内容               |            コマンドサンプル             |
| ---------- | -------------- | -------------------------------- | --------------------------------------- |
| curl [url] | -              | [url]をGETでHTTPリクエストを実行 | `curl https://www.google.com`           |
| curl [url] | -o [file name] | 実行結果を[file name]に出力      | `curl https://www.google.com -o a.html` |
| curl [url] | -v             | 実行結果を詳細出力               | `curl -v https://www.google.com`        |

<details>
<summary>※サポートしてるプロトコル</summary>

- HTTP/HTTPS
- FTP/FTPS/SFTP
- POP3(S)/SMTP(S)/IMAP(S)
- DICT
- FILE
- GOPHER
- LDAP(S)
- RTMP
- RTSP
- SCP
- TELNET
- TFTP
</details>