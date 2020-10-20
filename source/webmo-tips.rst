.. |webmo-build-icon| image:: ./img/webmo-build-icon.png
.. |webmo-periodictable-icon| image:: ./img/webmo-periodictable-icon.png
.. |webmo-adjust-icon| image:: ./img/webmo-adjust-icon.png
.. |webmo-comprehensive-cleanup-icon| image:: ./img/webmo-comprehensive-cleanup-icon.png
.. |webmo-next-icon| image:: ./img/webmo-next.gif


*****************
WebMOに関するTips
*****************

分子構造の作り方
================

- ブラウザからWebMOのURLを開き、ログインします。WebMOの "Job Manager" のページになります。
- 新しい分子を作成するには、 :menuselection:`New Job --> Create New Job` を選択します。すると、 "Build Molecule" のページに移ります。
- Buildアイコン |webmo-build-icon| を選ぶと、現在選択している元素とヒントが下部のステータスバーに表示されます。
- キャンバスのどこかで左クリックすると、原子が配置されます。
- やり直したい場合は、:menuselection:`Edit --> Undo` を選択します。
- 原子種を変えたい婆は、Periodic Tableアイコン |webmo-periodictable-icon| をクリックして原子種を変更します。
- 原子をクリックしてからドラッグすると、新しい原子が配置されるとともに、結合が形成されます。
- 結合次数を変更する場合は、Adjustアイコン |webmo-adjust-icon| をクリックして *adjust* モードにしてから、結合を選択し、右クリックします。
- 原子の混成軌道(hybridization)を変更する場合も、Adjustアイコン |webmo-adjust-icon| をクリックして *adjust* モードにしてから、原子を選択し、右クリックします。


.. tip::

    水素を自動的に付加したい場合は、:menuselection:`Cleanup --> Add Hydrogens` を選択します。ただし、混成軌道や結合次数を正しく設定していない場合は、失敗します。


.. tip::

    構造を分子力学方を用いた構造最適化する場合は、Comprehensive Cleanup using Mechanicsアイコン |webmo-comprehensive-cleanup-icon| をクリックします。


ジョブの設定と実行
==================

- キャンバス下部にある矢印 |webmo-next-icon| をクリックすると "Configure Gamess Job Options" に移ります。
- 計算エンジンの選択が表示されている場合は、 "Gaussian" を選択します。
- 各タブをクリックして計算条件を設定します。計算条件を設定した後、下部にある矢印 |webmo-next-icon| をクリックすると計算が "Job Manager" に登録されます。

.. attention::

    ジョブの実行に際し、ローカルルールがある場合はそれに従ってください。


Job Options
-----------

- :guilabel:`Job Name` には任意の名前を記入します。"Job Manager" にはこの名前が表示されます。
- :guilabel:`Calculation` は計算目的とする物性を選択します。
- :guilabel:`Theory` は理論的手法です。
- :guilabel:`Basis Set` では基底関数セットを選択します。
- :guilabel:`Charge` は分子の電荷です。
- :guilabel:`Multiplicity` はスピン多重度を設定します。


Advanced
--------

- :guilabel:`Save Checkpoint File` をチェックするとCheckpointファイルを作成します。Checkpointファイルには途中計算結果などが含まれているため、再計算するときに便利です。
- :guilabel:`Cartesian Coordinates` をチェックすると原子座標をCartesian座標で入力します。


Preview
-------

- :guilabel:`Generate` をクリックすると、Gaussianの入力ファイルが表示されます。


ジョブの管理
============

- "Job Manager" には、実行中と完了したジョブがリストアップされます。
- 完了したジョブは、右側の拡大鏡アイコンをクリックすると結果を見ることができます。

.. attention::
  
  http(s)の特性上、サーバー側から更新をpush通知することができず、webページの自動更新には限界があります。:guilabel:`Refresh` をクリックしてジョブの状況を随時更新してください。