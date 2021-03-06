# RAIDとは

複数のハードディスクを論理的にひとつにまとめて運用する技術をディスクアレイと呼ぶ。  
RAIDはその代表的な実装手段のひとつで、RAID0からRAID6までの7種類に分かれている。  
主な用途はハードディスクの信頼性向上や高速化。  
実際に使われるのは高速化のRAID0,信頼性のRAID1,そしれRAID5の3つ。

## RAID0(ストライピング)

RAID0では一つのデータを2台以上のディスクに分散させて書き込む。高速化が可能。  
一方でいずれか1台でも故障すると全ファイルが失われることになり、信頼性が低い。


## RAID1(ミラーリング)

RAID1では2台以上のディスクに対して常に同じデータを書き込む。常にバックアップがある状態。
使えるディスク領域は半分以下になるが、いずれか1台が故障してもそのまま使えるため信頼性が高い。

## RAID2

分散して書き込む元データと別にメモリなどで使用される誤り訂正符号(ECC)を書き込む。  
製品として実装されるものはほとんどない。

## RAID3,4

RAID3,4では3台以上のディスクを使って、データを分散させて書くと同時に  
パリティと呼ばれる誤り訂正記号を"専用のディスク"に書き込む。

3はストライピング(RAID0のやつ)のセットがbit単位、RAID4はブロック単位で分散させて書き込む。

## RAID5

RAID5では3台以上のディスクを使って、データと同時にパリティ(誤り訂正記号)を書き込む。  
いずれか1台が故障してもそれらのパリティ情報を使ってデータを復元することができる。  
2台にデータを書き込んだらもうひとつのディスクに2台分のパリティ情報を書き込む方法。
