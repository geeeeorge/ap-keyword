# AP ネットワーク
## 通信プロトコルの標準化
- OSI基本参照モデル
  - アプリケーション層
  - プレゼンテーション層
  - セッション層
  - トランスポート層
    - TCP, UDP
    - ポート番号
  - ネットワーク層
    - IP
  - データリンク層
  - 物理層
- プロトコルとサービス
  - 同じ層同士の通信
    - プロトコル
  - 階層間の通信
    - サービス
- プロトコルスイート
  - TCP/IPプロトコルスイート
- TCP/IPの通信
  - パケットとヘッダ
  - MACアドレス
    - 6byte
      - 前24bit
        - ベンダーID(OUI)
      - 後24bit
        - 固有製造番号
  - IPアドレス
  - ポート番号
    - 0-65535
    - 0-1023
      - 予約済み
      - well-known port

## ネットワーク接続装置と関連技術
### 物理層の接続
- リピータ
  - マルチポートリピータ(ハブ)

### データリンク層の接続
- ブリッジ
  - MACアドレステーブル
    - ブロードキャストフレーム
      - 受信ポート以外の全ポートに転送する
      - ブロードキャストストリーム
        - 機器をループ上につなぐと起こる
      - 対策
        - スパニングツリープロトコル
  - コリジョンドメイン
- スイッチングハブ
  - L2スイッチ

### ネットワーク層の接続
- ルータ
  - ブロードキャストドメイン
  - ルーティングテーブルの作成方法
    - スタティックルーティング
      - 手作業
    - ダイナミックルーティング
      - 自律的
      - RIP
        - Routing Information Protocol
        - ディスタンスベクタ型
        - ホップ数
          - 最大ホップ数は15
      - OSPF
        - Open Shortest Path First
        - リンクステート型
        - コスト
  - 冗長構成
    - VRRP
      - Virtual Router Redundancy Protocol
- L3スイッチ
  - 高速に処理できるのでファイルサーバへのアクセスに適す

### トランスポート層以上の接続
- ゲートウェイ
  - アプリケーションヘッダの不正な情報を検知
- L4スイッチ
  - TCP, UDPポート番号を見て処理を振り分ける
- L7スイッチ
- ネットワーク仮想化
  - SDN
    - Software Defined Networking
    - ネットワーク機器の制御をソフトウェアで行う
  - NFV
    - Network Function Virtualization
    - ネットワーク機器の機能をソフトウェアで行う

### VLAN

## データリンク層の制御とプロトコル
### メディアアクセス制御
- メディアアクセス制御
  - MAC
    - Media Access Control
- メディアアクセス制御の種類
  - CSMA/CD
    - Carrier Sense Multiple Access with Collision Detection
    - 送信前に空き状態を確認する
    - 衝突検出
      - 衝突した場合は再送信する
    - 30%を超えると実用的でない
  - トークンパッシング方式
    - フリートークンが巡回
    - 2種類の方式
      - トークンバス方式
      - トークンリング方式
  - TDMA方式
    - Time Division Multiple Access
    - 時分割多重アクセス
    - タイムスロットを割り当てる

### データリンク層の主なプロトコル
- ARP
  - Address Resolution Protocol
  - IPアドレスからMACアドレスを取得する
- RARP
  - Reverse Address Resolution Protocol
  - MACアドレスからIPアドレスを取得する
- PPP
  - Point-to-Point Protocol
  - NCP
  - LCP
- PPPoE
  - Point-to-Point Protocol over Ethernet

### IEEE 802.3規格
- CSMA/CD方式を使うLANについての標準
- データリンク層
  - LLC副層
    - Logical Link Control
  - MAC副層
    - Media Access Control
- 物理層

## ネットワーク層のプロトコルと技術
### IP
- IP
  - Internet Protocol
  - パケット通信技術
  - コネクションレス型
- TCP
  - コネクション型
- UDP
  - コネクションレス型
- IPヘッダ(IPv4)
  - TTL
    - Time To Live
    - ICMPタイプ11
  - プロトコル番号
    - 0-255
    - ICMP
      - 1
    - TCP
      - 6
    - UDP
      - 17
  - チェックサム

### IPアドレス
- ISP
  - Internet Service Provider
  - ここに申請し，IPアドレス取得
  - ダークネット
    - 使われていないIPアドレス空間
- IPアドレスの構成
  - ネットワークアドレス部
  - ホストアドレス部
- IPアドレスクラス
  - Aクラス
    -  先頭bit 0
      - ネットワークアドレス部 8bit
  - Bクラス
    - 先頭bit 10
      - ネットワークアドレス部 16bit
  - Cクラス
    - 先頭bit 110
      - ネットワークアドレス部 24bit
  - Dクラス
    - 先頭bit 1110
      - マルチキャストアドレス
- 特殊なIPアドレス
  - ネットワークアドレス
    - 全てのホストアドレスが0
  - ブロードキャストアドレス
    - 全てのホストアドレスが1
  - ループバックアドレス
    - 127.0.0.1
    - localhost
  - グローバルIPアドレス
  - プライベートIPアドレス
    - クラスA
      - 10.0.0.0~10.255.255.255
    - クラスB
      - 172.16.0.0~172.31.255.255
    - クラスC
      - 192.168.0.0~192.168.255.255

### サブネットマスク
- サブネットマスク
  - ネットワークアドレス部とホストアドレス部を区別するためのマスク
  - ネットワークアドレス部を1，ホストアドレス部を0とする
  - サブネットアドレス
    - サブネットに分割
  - プレフィックス表記
- CIDR
  - Classless Inter-Domain Routing
- スーパーネット化
  - 連続するネットワークを1つのネットワークにまとめる
### IPv6とアドレス変換技術
- IPv6
  - 変更内容
    - 128bit
    - IPsec
    - エニーキャスト
      - 複数のうち最も近いものに送信
  - プレフィックス
  - アドレスの種類
    - ユニキャストアドレス
    - エニーキャストアドレス
    - マルチキャストアドレス
      - FF00::/8
  - IPヘッダ
    - 次ヘッダ
      - プロトコル番号
    - ホップ・リミット
      - TTL
- アドレス変換技術
  - NAT
    - Network Address Translation
    - プライベートアドレスをグローバルアドレスに変換する
  - NAPT(IPマスカレード)
    - Network Address Port Translation
    - プライベートアドレスとポート番号をグローバルアドレスと別の番号に変換する
    - セキュリティ上の副次効果もある
### ネットワーク層のプロトコル
- ICMP
  - Internet Control Message Protocol
  - ICMPメッセージのタイプ
    - 0
      - エコー応答
    - 3
      - 到達不能
    - 5
      - 経路変更要求
    - 8
      - エコー要求
    - 11
      - タイムアウト
  - 便利コマンド
    - ping

## トランスポート層のプロトコル
### TCP
- Transmission Control Protocol
  - コネクション型
  - TCPヘッダ
    - シーケンス番号
      - 分割前どの部分だったか
    - ACK番号
      - 期待する次のシーケンス番号

### UDP
- User Datagram Protocol
  - コネクションレス型

## アプリケーション層のプロトコル
### メール関連
- メールプロトコル
  - SMTP
    - 送信
  - POP3
    - 受信
- メール受信プロトコル
  - APOP
    - パスワードを暗号化して送信する
  - IMAP4
    - メールサーバー上のメールボックスをクライアントにマウントする
  - IMAPS
    - IMAP4のSSL/TLS版
- メール関連のプロトコル
  - SMTP-AUTH
    - SMTPで認証を行う
    - サブミッションポート
      - 587
  - POP before SMTP
    - POP3でメールを受信してからSMTPで送信する
    - メールサーバーの負荷を減らす
  - SMTP over TLS
    - SMTPでSSL/TLSを利用する
  - S/MIME
    - MIMEの拡張
      - 日本語(16bit)，画像データをSMTPで扱えるように拡張したもの
    - メールの暗号化とデジタル署名を行う
  - PGP
    - S/MIMEとの違い
      - 相互認証方式
    - メールの暗号化とデジタル署名を行う

### Web関連
- HTTP
  - HyperText Transfer Protocol
  - HTTPメソッド
    - クエストリング
      - URLの末尾に付加される
    - CONNECT
      - プロキシサーバーとの接続を確立する
  - プル配信
    - クライアントがサーバーに要求する
- WebDAV
  - Web Distributed Authoring and Versioning
- HTTPS
  - HTTP over SSL/TLS
  - HSTS
    - HTTP Strict Transport Security
    - ブラウザで設定
    - HTTPでアクセスした場合，HTTPSにするよう求める
      - 中間者攻撃を防ぐ
- WebSocket
  - 双方向通信

### アドレス管理及び名前解決技術
- DHCP
  - Dynamic Host Configuration Protocol
  - UDP67, 68を使用
  - ネットワーク上のホストにIPアドレスを割り当てる
  - メッセージ順序
    - DHCPDISCOVER
      - ブロードキャスト
    - DHCPOFFER
    - DHCPREQUEST
      - ブロードキャスト
        - どのDHCPサーバからのOFFERを受け取るか他のDHCPサーバにわからせるため
    - DHCPACK
- DNS
  - Domain Name System
  - UDP53を使用
  - 可用性
    - プライマリサーバ
    - セカンダリサーバ
  - DNSレコード
  - DNSラウンドロビン
    - 複数のサーバーに分散して負荷を分散させる
  - コンテンツサーバとキャッシュサーバ

### その他のアプリケーション層プロトコル
- SOAP
  - XMLを利用
- SNMP
  - Simple Network Management Protocol
  - UDPを使用
  - ネットワーク機器の管理
  - PDU
    - Protocol Data Unit
- FTP
  - File Transfer Protocol
  - TCP20, 21を使用
- SSH
    - Secure Shell
    - TelnetのSecure版
    - TCP22を使用
- Telnet
  - テキストベースでのリモートログイン 
  - TCP23を使用
- NTP
  - Network Time Protocol
  - UDP123を使用
- LDAP
  - Lightweight Directory Access Protocol
  - TCP389を使用

### インターネット上の電話サービス
- VoIP
  - Voice over IP
  - デジタル信号をIPパケットに変換して送信する
  - RTP
    - Real-time Transport Protocol
    - UDPを使用
- SIP
  - Session Initiation Protocol
  - VoIPのセッションを開始するためのプロトコル
  - UDP5060を使用
- RSVP
  - Resource Reservation Protocol
  - 帯域管理

## 伝送技術
### 誤り制御
- パリティチェック
  - 偶数，奇数
  - 1bitまで
- CRC
  - Cyclic Redundancy Check
  - バースト誤りも検出可能
  - HDLCで使用
- ハミング符号
  - 2bit誤りを検出，1bitまで修正可能
- 水平垂直パリティチェック
  - 1bit修正可能

### 同期制御
- キャラクタ同期方式
- フラグ同期方式
  - 01111110
    - フラグシーケンス
    - DATAに出てきた場合
      - ゼロインサーション
  - HDLCで使用
- 調歩同期方式
  - 非同期方式

### 伝送制御
- HDLC手順
  - High-Level Data Link Control
  - フレームチェックシーケンス(FCS)
    - CRC方式での生成多項式で割った余り
- 無手順
  - 調歩同期方式を使用
- ベーシック手順
  - キャラクタ(文字)としてデータを伝達
  - キャラクタ同期方式

## 交換方式
### パケット交換方式
- 対となる方式
  - 回線交換方式
- メリット
  - 耐障害性
  - パケット多重
  - 異機種間接続性
- デメリット
  - 遅延

### ATM交換方式
- Asynchronous Transfer Mode
- セルの長さ
  - ヘッダ部
    - 5byte
  - ペイロード
    - 48byte
- ATMの階層構造
  - AAL
    - ATM Adaptation Layer
  - ATMもAALもデータリンク層

### フレームリレー
- DLCI
  - Data Link Connection Identifier
  - フレームリレーの接続を識別するための識別子
  - ワイヤスピード
    - 超えると輻輳状態
    - CIR
      - Committed Information Rate
      - 最低限保証する速度

## 無線LAN
### 無線LANの規格
- IEEE 802.11
  - b
    - 11Mbps
    - 2.4GHz
  - a
    - 54Mbps
    - 5GHz
  - g
    - 54Mbps
    - 2.4GHz
  - n
    - 600Mbps
    - 2.4, 5GHz
    - チャネルボンディング
    - MIMO
  - ac
    - 7Gbps
    - 5GHz
  - ax
    - 9.6Gbps
    - 2.4, 5GHz
- OFDM
  - Orthogonal Frequency Division Multiplexing
  - パケットを並列に送受信可能

### 無線LANのアクセス手順
- ビーコン信号の受信と接続
  - SSID
    - 最大32文字
  - ステルス機能
- SSIDの確認
  - MACアドレスフィルタリング
    - MACアドレスを指定して接続を制限する
- 暗号方式の確認
  - WPE, WPA, WPA2

### 無線LANのアクセス制御方式
- CSMA/CA方式
  - Carrier Sense Multiple Access with Collision Avoidance
  - バックオフ制御時間
    - バックオフ制御時間をランダムに設定することで衝突を防ぐ
- 隠れ端末問題
  - RTS/CTS方式
    - Request to Send/Clear to Send
    - データを送信する前に，送信先に送信準備ができているか確認する

### 無線LANのチャネル割り当て
