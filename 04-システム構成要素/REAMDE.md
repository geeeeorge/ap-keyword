# システム構成要素
## システムの処理携帯
- 集中処理システム
  - オンライントランザクション処理
    - VDI
      - Virtual Desktop Infrastructure
    - シンクライアント端末
- 分散処理システム
  - 水平機能分散
  - 水平負荷分散
  - 垂直機能分散
## クライアントサーバシステム
- クライアントサーバシステムの構成
  - アーキテクチャ 
    - 2層クライアントサーバシステム
      - クライアント
        - アプリケーションの肥大化
      - データベースサーバ
    - 3層クライアントサーバシステム
      - プレゼンテーション層
      - アプリケーション層
      - データベースアクセス層
- Web3層構造
  - Webサーバ
  - APサーバ
  - DBサーバ
- クライアントサーバ関連技術
  - ストアドプロシージャ
  - RPC
    - Remote Procedure Call
    - CORBA
      - Common Object Request Broker Architecture
      - オブジェクト指向の分散処理システムのための標準的なアーキテクチャ
  - NFS
    - Network File System
    - ファイルシステムの分散処理システムのための標準的なアーキテクチャ
## システムの構成と信頼性設計
- デュアルシステム
  - 並列冗長型システム
- デュプレックスシステム
  - 待機冗長型システム
  - 3つの方式
    - ホットスタンバイ方式
    - ウォームスタンバイ方式
      - スタンバイデータベース
    - コールドスタンバイ方式
- バックアップサイト
  - ホットサイト
  - ウォームサイト
  - コールドサイト
- 高信頼化システム
  - フォールトトレランス
    - フェールソフト
      - 部分回復
      - フォールバック
        - 縮退運転
    - フェールセーフ
      - 危険回避
    - フェールオーバ
      - フェールバック
    - フォールトマスキング
    - フールプルーフ
  - フォールトアボイダンス
## 高信頼性・高性能システム
- クラスタリング
  - HAクラスタ構成
    - High Availability
    - 2つの構成
      - フェールオーバクラスタ構成
        - アクティブ/スタンバイ
      - 負荷分散クラスタ構成
        - アクティブ/アクティブ
        - ロードバランシング
  - リソースを共有するか否か
    - シェアードエブリシング
    - シェアードナッシング
      - DWHはこっち
- グリッドコンピューティング
## ストレージ関連技術
- RAID
  - Redundant Arrays of Independent Disks
- ストレージの接続形態
  - DAS
    - Direct Attached Storage 
  - NAS
    - Network Attached Storage
  - SAN
    - Storage Area Network
    - FC-SAN
      - Fiber Channel Storage Area Network
    - iSCSI
      - Internet Small Computer System Interface
    - FCoE
      - Fibre Channel over Ethernet
## 仮想化技術
- ストレージ仮想化
  - シンプロビジョニング
  - ストレージ自動階層化
- サーバ仮想化
  - ホスト型仮想化
  - ハイパバイザ型仮想化
  - コンテナ型仮想化
  - その他
    - ライブマイグレーション
    - クラスタソフトウェア
## システムの性能特性と評価
- システムの性能指標
  - スループット
  - レスポンスタイム
  - ターンアラウンドタイム
  - MIPS
    - Million Instructions Per Second
  - FLOPS
    - Floating Point Operations Per Second
- システムの性能評価
  - 命令ミックス
    - コマーシャルミックス
    - ギブソンミックス
    - 逆数がMIPS
  - ベンチマーク
    - SPEC
      - Standard Performance Evaluation Corporation
    - TPC
      - Transaction Processing Performance Council
- モニタリング
  - ソフトウェアモニタ
  - ハードウェアモニタ
- キャパシティプランニング
  - キャパシティ管理
  - サーバのスケーリング
    - 水平スケーリング
      - スケールアウト
    - 垂直スケーリング
      - スケールアップ
## 待ち行列理論の適用
## システムの信頼性特性と評価





