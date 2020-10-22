.. include:: def-webmo.txt


*************
WebMOの使い方
*************


はじめに
========

WebMO (https://www.webmo.net/) はwebブラウザで分子モデリングを行い、GaussianやGAMESSなどの量子化学計算パッケージへのインターフェースを備えたサーバーサイドのプログラムである。

詳細は、`本家のドキュメント <https://www.webmo.net/support/documentation.html>`_ を参照のこと。

分子構造の作り方
================

#. ブラウザからWebMOのURLを開き、ログインする。WebMOの "Job Manager" のページになる。
#. 新しい分子を作成するには、 :menuselection:`New Job --> Create New Job` を選択する。"Build Molecule" のページに移る。
#. Buildアイコン |webmo-build-icon| を選ぶと、現在選択している元素とヒントが下部のステータスバーに表示される。
#. キャンバスのどこかで左クリックすると、原子が配置される。
#. やり直したい場合は、:menuselection:`Edit --> Undo` を選択する。
#. 原子種を変えたい婆は、Periodic Tableアイコン |webmo-periodictable-icon| をクリックして原子種を変更する。
#. 原子をクリックしてからドラッグすると、新しい原子が配置されるとともに、結合が形成される。
#. 結合次数を変更する場合は、Adjustアイコン |webmo-adjust-icon| をクリックして *adjust* モードにしてから、結合を選択し、右クリックする。
#. 原子の混成軌道(hybridization)を変更する場合も、Adjustアイコン |webmo-adjust-icon| をクリックして *adjust* モードにしてから、原子を選択し、右クリックする。


.. tip::

    水素を自動的に付加したい場合は、:menuselection:`Cleanup --> Add Hydrogens` を選択する。ただし、混成軌道や結合次数を正しく設定していない場合は、失敗する。


.. tip::

    構造を分子力学方を用いた構造最適化する場合は、Comprehensive Cleanup using Mechanicsアイコン |webmo-comprehensive-cleanup-icon| をクリックする。


ジョブの設定と実行
==================

- キャンバス下部にある矢印 |webmo-next-icon| をクリックすると "Configure Gamess Job Options" に移る。
- 計算エンジンの選択が表示されている場合は、 "Gaussian" を選択する。
- 各タブをクリックして計算条件を設定する。計算条件を設定した後、下部にある矢印 |webmo-next-icon| をクリックすると計算が "Job Manager" に登録される。

.. attention::

    ジョブの実行に際し、ローカルルールがある場合はそれに従うこと。


Job Options
-----------

- :guilabel:`Job Name` には任意の名前を記入します。"Job Manager" にはこの名前が表示される。
- :guilabel:`Calculation` は計算目的とする物性を選択する。
- :guilabel:`Theory` では理論的手法を選択する。
- :guilabel:`Basis Set` では基底関数セットを選択する。
- :guilabel:`Charge` は分子の電荷を入力する。
- :guilabel:`Multiplicity` はスピン多重度を設定する。


Advanced
--------

- :guilabel:`Save Checkpoint File` をチェックするとCheckpointファイルを作成する。Checkpointファイルには途中計算結果などが含まれているため、再計算するときに便利。
- :guilabel:`Cartesian Coordinates` をチェックすると原子座標をCartesian座標で入力する。
- 分子軌道を表示したいときは、:guilabel:`Additional Keywords` に "Pop=Full GFInput"を入力する。

Preview
-------

- :guilabel:`Generate` をクリックすると、Gaussianの入力ファイルが表示される。


ジョブの管理 (Job Manager)
==========================

- "Job Manager" には、実行中と完了したジョブがリストアップされる。
- 完了したジョブは、右側の拡大鏡アイコンをクリックすると結果を見ることができる。

.. attention::
  
  http(s)の特性上、サーバー側から更新をpush通知することができず、webページの自動更新には限界がある。 |webmo-refresh-icon| :guilabel:`Refresh` をクリックしてジョブの状況を随時更新すること。


結果の表示 (View Job)
=====================

- 左側"Actions"にある |webmo-output-icon| :guilabel:`Raw output` をクリックすると、計算の全出力(生データ)が表示される。
- 等値面(isosurface)の値は、 |webmo-preferences-icon| をクリックして、"Preferences" ダイアログから変更できる。
