# .ply（GaussianSplatting）をUnityで表示させる方法
## まえがき
Unityは.plyファイルには非対応の為、拡張機能を介してアセットを生成させてから表示させる必要がある。
>参考：https://docs.unity3d.com/ja/560/Manual/HOWTO-importObject.html

私の環境で実行できた手順を記す。

## 動作環境
以下の環境で行った。
- **Unity 2022.3.7f1**
  >[https://unity.com/ja/releases/editor/whats-new/2022.3.7](https://unity.com/ja/releases/editor/whats-new/2022.3.7)\
  >上記サイトにアクセス、「INSTALL」をクリックしてUnityHUBを起動し、UnityHUBよりUnity2022.3.7f1をインストール。\
  >[Unity Hub](https://unity.com/download)の事前インストールが必要となる。
- **GitHubリポジトリ**
  >[https://github.com/aras-p/UnityGaussianSplatting](https://github.com/aras-p/UnityGaussianSplatting)\
  >後述。
- **.plyファイル**

## 導入
1. GitHubDeskTopで [https://github.com/aras-p/UnityGaussianSplatting.git](https://github.com/aras-p/UnityGaussianSplatting.git) を任意のディレクトリにクローン。\
   または、コマンドプロンプトを起動して任意のディレクトリに移動後、以下のコマンドを実行してクローンする。
   ```
   git clone https://github.com/aras-p/UnityGaussianSplatting.git
   ```
2. クローン出来たら、`.\UnityGaussianSplatting\projects\GaussianExample\Assets\GSTestScene.unity`を開く。\
   ※以下のようなエラーウィンドウが出た場合、最も右の「Continue」で続行する。\
   ![image](https://github.com/user-attachments/assets/41e61121-61ca-48c7-ab18-aa47a2bf6422)
3. シーンをUnityで起動出来たら、Unityウィンドウ上部リボンメニューから、「Tools」→「Gaussian Splats」→「Create GaussianSplatsAsset」を選択。\
   ![image](https://github.com/user-attachments/assets/e95f351b-8c87-43b6-b43d-dd16440966b5)
4. 「Gaussian Splat Creater」ウィンドウが表示されるので、「Input PLY/SPZ File」に使用したい.plyファイルをインポートし、ウィンドウ最下部の「Create Asset」を押してアセット化を実行する。\
   ![image](https://github.com/user-attachments/assets/77f7bae7-b078-47f8-8744-bc7e02916285)
5. 処理に成功すると、plyファイル名のアセットが作成されている。「Project」→「Assets」→「GaussianAssets」内に格納されているので作成されているかを確認する。\
   ![image](https://github.com/user-attachments/assets/48bc039a-c517-410b-9269-88ea83112a31)
6. 「Hierarchy」内の「GSTestScene」→「GaussianSplats」を選択してインスペクター（Inspector）を開く。
7. インスペクター内に「Gaussian Splats Renderer」スクリプトが入っていることを確認し、「Data Asset」の「Asset」に5.で作成したアセットをドラッグ＆ドロップする。（5.の画像一番左（例：example.asset））\
   ![image](https://github.com/user-attachments/assets/92728a78-dfec-497d-aa78-04dac3f8f0f9)
8. シーンに反映されれば完了。

