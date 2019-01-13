# symfony-crud
symfonyでのCRUDアプリ習作  

下記を使わせていただきました。  
https://php-archive.net/php/symfony-4-crud/

# 環境

- CentOS Linux release 7.4.1708 (Core)
- PHP 7.1.21
- symfony/skeleton (v4.2.2.1)

# 注意点

## doctorineインストール

上のコマンドだとエラーになったので、下のコマンドを実行する

```bash
# composer require doctrine maker

  [UnexpectedValueException]
  Could not parse version constraint maker: Invalid version string "maker"
```

```bash
# composer require symfony/orm-pack
# composer require symfony/maker-bundle --dev
```

また、makeコマンドでエラーになったのでmakerを一度削除し再インストールしました。

```bash
# php bin/console make:entity Post
2019-01-13T05:14:18+00:00 [error] Error thrown while running command "'make:entity' Post". Message: "There are no commands defined in the "make" namespace."
```

```bash
# composer remove maker
# composer require maker --dev
```

## .htaccess設定

/public直下に、.htaccessを追加する。（httpd.conf等webサーバへ設定行う場合は不要）  
[https://gist.github.com/Guibzs/a3e0b3ea4eb00c246cda66994defd8a4:title]
