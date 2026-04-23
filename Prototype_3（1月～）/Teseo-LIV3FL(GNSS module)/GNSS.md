### Teseo-LIV3FL GNSS module
#### 部品

| 部品名 | 個数 | リンク | 備考 |
| --- | --- | --- | --- |
| IC1 Teseo-LIV3FLF | 1 | https://akizukidenshi.com/catalog/g/g130031/ |  |
| R1 200Ω | 1 |  https://www.sengoku.co.jp/mod/sgk_cart/detail.php?code=EEHD-0ECC# | SMD 3216 |
| R2 10Ω | 1 |  https://www.sengoku.co.jp/mod/sgk_cart/detail.php?code=EEHD-0EBH | SMD 3216 |
| C1 0.1μF | 1 | https://akizukidenshi.com/catalog/g/g116143/ | SMD 1608 |
| L1 27nH | 1 | https://www.monotaro.com/g/04259779/ | SMD 1005 サイズ小さい．表面実装できる？あと秋月にはない．|
| D1 LED | 1 | https://akizukidenshi.com/catalog/g/g109639/ | SMD 3216 |
| J1 コネクタ | 1 | https://akizukidenshi.com/catalog/g/g115417/ |  |
| アンテナ | 1 | https://akizukidenshi.com/catalog/g/g130030/ |  |

#### メモ
- 一応アクティブアンテナ向けに設計．回路的にはパッシブアンテナに切り替え可能．ただコネクタの形状が合わないかも．
- [このサイト](https://xsuz.github.io/blog/how_to_get_raw_data_from_teseo-liv3fl/)の回路とほぼ同じ
- 受信回路部分は同軸ケーブル経由でアクティブアンテナ（LNA内蔵）に電源を供給するため，Bias-Teeという回路を採用．[この動画（イチケン）](https://youtu.be/0PgLCQ8AsGs?si=6OudbEyScfQURzJA&t=123)でBias-Teeについて述べられている
- アンテナ周りに結構気を使ったつもり．受信する電波の周波数が1.57542GHzと高く，信号の反射などに気を付けなければならない（普通の回路だと配線長に対して信号の波長が十分に長く気にしなくていいが，配線長に対して信号の波長が短いと信号の反射や減衰などが生じて正しく電気信号が伝わらない．詳しくは「集中定数回路と分布定数回路」「RF回路」「高周波回路」などで検索）．この基板では信号の波長が約19cmなので一応気にしたほうがいい．
- アンテナの配線は特性インピーダンス50Ωで整合．KiCadの計算ツール使った．
