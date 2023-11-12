# CakePHP 5.x Boostrap 導入

## CakePHP インストール手順

参考: https://github.com/FriendsOfCake/bootstrap-ui

プラグインをCakePHP内に組み込むやり方ではなく、`npm`で`boostrap`を入れて
それをViewに反映させる方法

1. composerに追加
    ```
   composer require friendsofcake/bootstrap-ui
   ```
2. Pluginをロード
    ```
   bin/cake plugin load BootstrapUI
   ```
3. npmでboostrapをインストール
    ```
    npm install @popperjs/core@2 bootstrap@5 bootstrap-icons@1
    ```
4. 必要なファイルをコピー
    ```
   cp node_modules/@popperjs/core/dist/umd/popper.js webroot/js
   cp node_modules/@popperjs/core/dist/umd/popper.min.js webroot/js
   cp node_modules/bootstrap/dist/css/bootstrap.css webroot/css/
   cp node_modules/bootstrap/dist/css/bootstrap.min.css webroot/css/
   cp node_modules/bootstrap/dist/js/bootstrap.js webroot/js/
   cp node_modules/bootstrap/dist/js/bootstrap.min.js webroot/js/
   cp node_modules/bootstrap-icons/font/bootstrap-icons.css webroot/font/
   cp node_modules/bootstrap-icons/font/fonts/bootstrap-icons.woff webroot/font/fonts/
   cp node_modules/bootstrap-icons/font/fonts/bootstrap-icons.woff2 webroot/font/fonts/
   cp vendor/friendsofcake/bootstrap-ui/webroot/font/bootstrap-icon-sizes.css webroot/font/
   ```
5. layoutに追加
    ```
   <?php
       echo $this->Html->css('bootstrap.min');
       echo $this->Html->css(['/font/bootstrap-icons', '/font/bootstrap-icon-sizes']);
       echo $this->Html->script(['popper.min', 'bootstrap.min']);
   ?>
   ```
___

