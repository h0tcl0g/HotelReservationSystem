# クラス図
### 予約段階
![予約段階](https://imgur.com/uH223JG.png "予約段階")
### チェックイン/アウト段階
![チェックイン/チェックアウト](https://imgur.com/miFnuY2.png "チェックイン/アウト")

# オブジェクト図
### 予約段階
![予約段階](https://imgur.com/e5fVjxY.png "予約段階")
### チェックイン/アウト段階
![チェックイン/チェックアウト](https://imgur.com/0scE5Hr.png "チェックイン/アウト")

# ユースケース図
![ユースケース図](https://imgur.com/YUGL6vt.png "ユースケース図")
## ユースケース記述
### ユースケース: ホテルを予約する  
##### アクタ: ユーザ  
##### 目的: ユーザがホテルの部屋を予約する  
##### 事前条件:  
  ・ユーザがシステムにログインしている  
  ・ホテルの部屋に空きがある  
##### 事後条件:  
  ・ユーザが選択した条件の部屋と食事の予約が完了している。  
  ・ユーザが予約確認メールを受け取る。  
##### 基本系列:  
1.アクタはシステムに、ホテルの部屋と食事を予約する旨を示す。   
2.システムはアクタに、宿泊希望日、人数、部屋種別、食事回数の条件入力を促す。   
3.アクタはシステムに、宿泊希望日・人数・部屋種別・食事回数を入力する。   
4.システムはアクタの条件に基づき、利用可能な部屋リストと料金を表示する。   
5.ユーザは希望する部屋を選択する。   
6.システムはユーザに予約情報(氏名や連絡先、支払い情報)の入力を促す。  
7.ユーザはシステムに予約情報を入力する。   
8.システムはユーザに予約情報を提示し、確認を求める。  
9.ユーザは確認ボタンを押す。  
10.システムは予約を確定し、予約確認メールをユーザに送信する。  
##### 代替系列:  
1.(基本系列 2)ユーザの入力情報が不足している場合、システムはユーザに「入力情報に 不備があります」と表示し、再度の入力を促す。  
2.(基本系列 4)希望条件に合う部屋が見つからなかった場合、システムは「条件に合う部 屋が見つかりませんでした」と表示し、ユーザに他の日程または部屋タイプで再入力を促す。  
3.(基本系列 8)ユーザが確認を拒否した場合、システムは予約をキャンセルし、ユーザに 再入力を促す。  
4.(基本系列 7)支払い情報が無効だった場合、システムは「支払い情報が無効です」と表 示し。ユーザに再入力を促す。  
##### 備考: (なし)  
###### シナリオ 1: 正常な予約プロセス  
(1) 山田太郎さんがシステムにログインし、予約ページにアクセス。  
(2) 山田さんが宿泊希望日を 2024 年 8 月 1 日、人数を 2 人、部屋種別を「中部屋」、食事 回数を 2 回と入力。  
(3) システムが利用可能な部屋リストと料金を表示。  
システム表示例: 「中部屋(¥20,000)」、「中部屋(¥25,000)」  
(4) 山田さんが希望する「中部屋(¥20,000)」を選択。  
(5) システムが山田さんに予約情報(氏名や連絡先、支払い情報、メールアドレス)の入力 を促す。  
(6) 山田さんが予約情報(氏名: 山田太郎、連絡先:080-1234-5678、支払い情報: クレジッ トカード、メールアドレス: yamada@example.com)を入力。  
(7) システムが予約情報を提示し、確認を求める。  
表示例: 「予約情報:日程:2024 年 8 月 1 日、人数:2 人、部屋種別:中部屋、食事:2 回、 料金:\40,000、氏名:山田太郎、連絡先:080-1234-5678、メールアドレス: yamada@example.com、支払い方法:カード、カード番号:1234-5678-9876-5432」  
(8) 山田さんが確認ボタンを押す。  
(9) システムが予約を確定し、予約確認メールを yamada@example.com へ送信。  
###### シナリオ 2: 入力情報不足の処理  
(1) 佐藤花子さんがシステムにログインし、予約ページにアクセス。  
(2) 佐藤さんが宿泊希望日を入力せずに、人数を 3 人、部屋種別を「大部屋」、食事回数を 3 回と入力。  
(3) システムが「入力情報に不備があります」と表示し、再度の入力を促す。  
###### シナリオ 3: 条件に合う部屋が見つからない場合  
(1) 鈴木一郎さんがシステムにログインし、予約ページにアクセス。  
(2) 鈴木さんが宿泊希望日を 2024 年 12 月 31 日、人数を 4 人、部屋種別を「大部屋」、食 事回数を 3 回と入力。  
(3) システムが「条件に合う部屋が見つかりませんでした」と表示する。  
###### シナリオ 4: 確認を拒否した場合  
(1) 田中裕子さんがシステムにログインし、予約ページにアクセス。  
(2) 田中さんが宿泊希望日を 2024 年 7 月 15 日、人数を 1 人、部屋種別を「小部屋」、食事 回数を 1 回と入力。  
(3) システムが利用可能な部屋リストと料金を表示。  
システム表示例: 「小部屋(¥10,000)」、「小部屋(¥12,000)」  
(4) 田中さんが希望する「小部屋(¥10,000)」を選択。  
(5) システムが田中さんに予約情報(氏名や連絡先、支払い情報、メールアドレス)の入力 画面を表示。  
(6) 田中さんが予約情報(氏名: 田中裕子、連絡先:090-9876-5432、支払い情報: 現地支払 い、メールアドレス: tanaka@example.com)を入力。  
(7) システムが予約情報を提示し、確認を求める。  
システム表示例: 「予約情報:日程:2024 年 7 月 15 日、人数:1 人、部屋種別:小部屋、 食事:1 回、料金:\10,000、氏名:田中裕子、連絡先:090-9876-5432、メールアドレス: tanaka@example.com、支払い方法:現地支払い」  
(8) 田中さんが確認を拒否し、システムは予約をキャンセルし、再入力を促す。  
###### シナリオ 5: 支払い情報が無効だった場合  
(1) 高橋健さんがシステムにログインし、予約ページにアクセス。  
(2) 高橋さんが宿泊希望日を 2024 年 9 月 10 日、人数を 2 人、部屋種別を「中部屋」、食事 回数を 2 回と入力。  
(3) システムが利用可能な部屋リストと料金を表示。  
システム表示例: 「中部屋(¥18,000)」、「中部屋(¥22,000)」  
(4) 高橋さんが希望する「中部屋(¥18,000)」を選択。  
(5) システムが高橋さんに予約情報(氏名や連絡先、支払い情報、メールアドレス)の入力 を促す。  
(6) 高橋さんが予約情報(氏名: 高橋健、連絡先:070-6543-2109、支払い情報: クレジット カード、カード番号 1234-5678-9012-3456、メールアドレス: takahashi@example.com)を 入力。  
(7) システムが「支払い情報が無効です」と表示し、高橋さんに再入力を促す。  

画像リンクはここで作成  
https://imgur.com/
