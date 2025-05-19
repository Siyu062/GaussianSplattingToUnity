# .ply（GaussianSplatting）をUnityで表示させる方法
## まえがき
Unityは.plyファイルには非対応の為、拡張機能を介してアセットに変換させてから表示させる必要がある。
>参考：https://docs.unity3d.com/ja/560/Manual/HOWTO-importObject.html

私の環境で実行できた手順を記す。

## 用意物
- **Unity 2022.3.7f1**
  >[https://unity.com/ja/releases/editor/whats-new/2022.3.7](https://unity.com/ja/releases/editor/whats-new/2022.3.7)\
  >上記サイトにアクセス、「INSTALL」をクリックしてUnity Hubを起動し、Unity HubよりUnity2022.3.7f1をインストール。\
  >Unity 2022.3.7f1のインストールには[Unity Hubの事前インストール](https://unity.com/download)が必要。
- **GitHubクローン**
  >[https://github.com/aras-p/UnityGaussianSplatting](https://github.com/aras-p/UnityGaussianSplatting)\
  >今回使用するUnity拡張機能。GitHubで公開されている。
- **.plyファイル**
  >Unityに取り込みたい.plyファイルを用意する。\
  >使用する.plyファイルにはガウス分布が含まれている必要がある。ガウス分布が含まれていない場合には実行できない。

## 導入
1. [GitHub DeskTop](https://docs.github.com/ja/desktop/installing-and-authenticating-to-github-desktop/installing-github-desktop)で [https://github.com/aras-p/UnityGaussianSplatting.git](https://github.com/aras-p/UnityGaussianSplatting.git) を任意のディレクトリにクローン。\
   または、コマンドプロンプトを起動して任意のディレクトリに移動後、以下のコマンドを実行してクローンする。
   ```
   git clone https://github.com/aras-p/UnityGaussianSplatting.git
   ```
2. クローン出来たら、`.\UnityGaussianSplatting\projects\GaussianExample\Assets\GSTestScene.unity`を開く。\
   ※以下のようなエラーウィンドウが出た場合、「Continue」を選択して続行する。\
   ![image](https://github.com/user-attachments/assets/41e61121-61ca-48c7-ab18-aa47a2bf6422)
3. シーンをUnityで起動出来たら、Unityウィンドウ上部リボンメニューから、「Tools」→「Gaussian Splats」→「Create GaussianSplatAsset」を選択。\
   ![image](https://github.com/user-attachments/assets/e95f351b-8c87-43b6-b43d-dd16440966b5)
4. 「Gaussian Splat Creater」ウィンドウが表示されるので、「Input PLY/SPZ File」に使用したい.plyファイルをインポートし、ウィンドウ最下部の「Create Asset」を押してアセット化を実行する。\
   ![image](https://github.com/user-attachments/assets/77f7bae7-b078-47f8-8744-bc7e02916285)
5. 処理に成功すると、.plyファイル名でアセットが作成される（例：`example.ply`→`example.asset`）。「Project」→「Assets」→「GaussianAssets」内に格納されるので、アセットが作成されているかを確認する。\
   ![image](https://github.com/user-attachments/assets/48bc039a-c517-410b-9269-88ea83112a31)
6. 「Hierarchy」内の「GSTestScene」→「GaussianSplats」を選択してインスペクター（Inspector）を開く。
7. インスペクター内に「Gaussian Splats Renderer」スクリプトが入っていて、チェックマークが入っていることを確認し、「Data Asset」の「Asset」に5.で作成したアセットをドラッグ＆ドロップする。（5.の画像一番左（例：`example.asset`））\
   ![image](https://github.com/user-attachments/assets/92728a78-dfec-497d-aa78-04dac3f8f0f9)
8. シーンに反映されれば完了。

## 参考文献
- Gaussian-Splatting をUnityで動かしてみた｜aster\
  [https://zenn.dev/aster_ideatech/articles/523b4909d4e48f](https://zenn.dev/aster_ideatech/articles/523b4909d4e48f)
- 3D アプリケーションからモデルをインポートする方法 - Unity マニュアル\
  [https://docs.unity3d.com/ja/560/Manual/HOWTO-importObject.html](https://docs.unity3d.com/ja/560/Manual/HOWTO-importObject.html)
- aras-p_UnityGaussianSplatting_ Toy Gaussian Splatting visualization in Unity\
  [https://github.com/aras-p/UnityGaussianSplatting](https://github.com/aras-p/UnityGaussianSplatting)
