# 26th_PCB_AirData
メイン兼エアデータセンサー部（今後、エアデータと言います）のリポジトリです。
## 基板作成時の注意点
PCBエディターで基板上の配線をするときに気をつけてほしい点・できるだけ避けるべき点が書いてあります．これが全てではないのですが，最低限これらは守ってほしいです🙏  
( ｀・∀・´)ﾉﾖﾛｼｸ
### KiCadの初期設定
これから表面実装化に向けた，小さく密度の高い基板を作ろうとするとKiCadの初期設定状態では不便が生じます．それは例えば配線のクリアランス（配線同士の最低間隔）やビア半径の初期設定値が大きすぎるためです．  
以下の画像下部のGNDビアはその上のコンデンサと同じぐらいの大きさになっていて，もはや邪魔です．  
<img width="500" height="778" alt="image" src="https://github.com/user-attachments/assets/9dc073f4-7d39-4f44-b29c-0b9c6b46b7a5" />  
そこで，以下の画像左上「ビア：ネットクラスのサイズを使用」から任意の半径でビアの大きさを指定できるのですが，[JLCPCBの製造能力](https://jlcpcb.com/jp/capabilities/pcb-capabilities)には限界があるわけでその限界を突破しないギリギリで設計する必要があります．その限界を突破していないか確認してくれる機能を活用するためにKiCad初期設定を変更します．  
<img width="1919" height="990" alt="image" src="https://github.com/user-attachments/assets/cacfa8a9-fa94-4381-ad05-0062fc997e36" />
1. ファイル ＞ 基板の設定
<img width="1919" height="1017" alt="image" src="https://github.com/user-attachments/assets/38d11a01-088e-4200-a178-2f459dd85d28" />  

2. デザインルール ＞ 制約
<img width="1918" height="1018" alt="image" src="https://github.com/user-attachments/assets/01847bb4-8a08-4854-8415-595e29ed0c79" />

3. 以下のようにパラメーターを変更
<img width="444" height="695" alt="image" src="https://github.com/user-attachments/assets/db7b8c8f-52e0-461f-bd9d-095a752814f5" />

### USBの配線について
USBは差動伝送で通信しています．そのため，2本の配線のどちらかにだけノイズが乗ることや配線長に差があること，配線が長すぎることは避けるべきです．また，差動インピーダンスを考慮する必要があり，普段の配線よりも気を遣う点が多いです．以下の点に気をつけて配線をお願いします．  
- 差動インピーダンスを90Ωに近づける（[JLCPCB公式計算ツール](https://jlcpcb.com/jp/pcb-impedance-calculator)）
- KiCad「差動ペアを配線」機能を使用する
- 同一レイヤー上で配線する
- できるだけ配線を曲げず，一直線に配線する
- 電源線（5V，3.3Vなど）を近くに置かない
- 
