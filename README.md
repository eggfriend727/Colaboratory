データ解析用のipynbファイル

使い方
1.現段階でのデータファイルはtxt形式なのでcsv形式に変更する
ファイル名.txt を ファイル名.csv に書き換える

2.Google driveに計測データをアップロードする
好きな場所に保存してよいが、データ用のディレクトリを作成しその中に保存することをおすすめする（drive内がぐちゃぐちゃになるため）
Google driveを開いた時のカレントディレクトリが、drive/My Drive なので
ここに data　のディレクトリを作成し
dataディレクトリの中に 日付（例：11-30) のディレクトリを作成する。
更にその中に 01~09（ラズパイ番号）のディレクトリを作成し、それらの中にその日の計測データを保存する。
割と面倒なので、PC側で 11-30/01~09 を作りその中にデータを保存して、11-30ディレクトリを丸ごとアップロードの方が多分早い。

3.Colabでipynbのファイルを開いて自分のdriveに保存する
ファイルをクリックした際にコードの一番上に表示される"Open in Colab"をクリックすると、Colabratoryで利用できる

4.コードを編集する
npdata02 = read_data('drive/My Drive/data/11-xx/csv/.csv') #以下4行ファイル名を入力
npdata03 = read_data('drive/My Drive/data/11-xx/csv/.csv') #
npdata04 = read_data('drive/My Drive/data/11-xx/csv/.csv') #
npdata05 = read_data('drive/My Drive/data/11-xx/csv/.csv') #
は変更しないとグラフが描画できない。データファイルの名前がhoge.csvでデータをアップロードしたのが drive/My Drive/data/11-30 なら
npdata02 = read_data('drive/My Drive/data/11-30/hoge.csv') #とする。


ax1~4.set_title('0x どこ？',fontsize=25) #以下4行'ラズパイ 場所'を入力
plt.suptitle('タイトル sr：100Hz',fontsize=35) #タイトルを入力
は'シングルクォートの中'に好きな文字を入力する

dr = 8
を変更すると、データを削除する間隔を調節できる、800Hzで計測を行っているのでデフォルトの8では、
800 / 8 = 100Hz：0.01sec おき となる

5.実行
一番上から順に実行する
1つめのブロックを実行して少し待つとURLが表示されるのでクリック
適当に進んでいくとこのコードを貼り付けろって言われるので、右側の謎のマークを押してクリップボードにコピー
Colabに戻って Ctrl+V で貼り付ける(右クリック不可)
後は順番に実行するだけ
