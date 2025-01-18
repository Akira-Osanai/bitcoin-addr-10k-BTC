# Bitcoin Market Analysis Tool

ビットコイン市場の分析に役立つ様々な指標を収集・可視化するツールです。

## 機能

- 1年分のヒストリカルデータを収集
- 複数の指標を組み合わせた分析が可能
- 自動的なデータ更新（既存データの確認と不足分のみ取得）
- グラフによる視覚化

## 収集する指標

1. **大口保有者データ**
   - 10,000BTC以上を保有するアドレス数
   - データソース: bitcoin-data.com

2. **BTCUSDの価格データ**
   - ビットコインの米ドル建て価格
   - データソース: Yahoo Finance

3. **ファンディングレート**
   - Binanceの先物市場におけるファンディングレート
   - トレーダーの方向性バイアスを示す指標

4. **Fear & Greed Index**
   - 市場の感情指標
   - 0（極度の恐怖）から100（極度の強気）

5. **オープンインタレスト（OI）**
   - Binanceの先物市場における未決済の契約数
   - 市場参加者のポジション状況を示す

6. **取引量**
   - 24時間の取引量
   - 価格変動の信頼性を判断する指標

7. **アクティブアドレス数**
   - ネットワーク上のユニークなアクティブアドレス数
   - ネットワークの利用状況を示す

8. **ハッシュレート**
   - ネットワークの計算能力
   - マイニング難易度とセキュリティの指標

## セットアップ

1. リポジトリのクローン:
```bash
git clone https://github.com/Akira-Osanai/bitcoin-addr-10k-BTC.git
cd bitcoin-addr-10k-BTC
```

2. 仮想環境の作成と有効化:
```bash
python -m venv venv
source venv/bin/activate  # Linuxの場合
venv\Scripts\activate     # Windowsの場合
```

3. 依存パッケージのインストール:
```bash
pip install -r requirements.txt
```

## 使用方法

1. スクリプトの実行:
```bash
python crypto_analysis.py
```

2. 出力:
- 各指標のデータは`market_data`ディレクトリにCSVファイルとして保存
- グラフは`crypto_analysis.png`として保存

## データの更新

- スクリプトは既存のデータを確認し、不足している期間のデータのみを取得
- 毎日実行することで、最新のデータを維持可能

## 注意事項

- APIの利用制限に配慮して、適切な間隔でデータを取得
- CSVファイルはGitの管理対象外（`.gitignore`に設定済み）