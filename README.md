# .ply（GaussianSplatting）をUnityで表示させる方法
## 
Unity自体は.plyファイルには非対応の為、拡張機能を介してアセットを生成させてから表示させる必要がある。
>参考：https://docs.unity3d.com/ja/560/Manual/HOWTO-importObject.html

## 動作環境
以下の環境で行った。
- **Unity 2022.3.7f1**
  >[https://unity.com/ja/releases/editor/whats-new/2022.3.7](https://unity.com/ja/releases/editor/whats-new/2022.3.7)\
  >UnityHUBを事前インストールの上、「INSTALL」をクリックしてUnityHUBを起動し、UnityHUBよりUnity2022.3.7f1をインストール。
- **GitHubリポジトリ**
  >[https://github.com/aras-p/UnityGaussianSplatting](https://github.com/aras-p/UnityGaussianSplatting)\
  >後述。
- **.plyファイル**

## 導入
1. GitHubDeskTopで[https://github.com/aras-p/UnityGaussianSplatting.git](https://github.com/aras-p/UnityGaussianSplatting.git)を任意のディレクトリにクローン。\
   または、コマンドプロンプトを起動して任意のディレクトリに移動後、以下のコマンドを実行してクローンする。
   ```
   git clone https://github.com/aras-p/UnityGaussianSplatting.git
   ```
2. クローン出来たら、
