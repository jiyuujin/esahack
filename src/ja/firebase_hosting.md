# Firebase hosting

## Installation

Flutter for Web によって作成されたWebサイトをデプロイします。

```bash
firebase init hosting

     ######## #### ########  ######## ########     ###     ######  ########
     ##        ##  ##     ## ##       ##     ##  ##   ##  ##       ##
     ######    ##  ########  ######   ########  #########  ######  ######
     ##        ##  ##    ##  ##       ##     ## ##     ##       ## ##
     ##       #### ##     ## ######## ########  ##     ##  ######  ########

```

`build/web` をパブリックディレクトリに設定します。

```bash
? What do you want to use as your public directory? build/web
```

`index.html` を使わないでください。

```bash
? Configure as a single-page app (rewrite all urls to /index.html)? No
```

自動ビルドを開始します。

```bash
? Set up automatic builds and deploys with GitHub? Yes
```

作成したリポジトリの名前を入力する。

```bash
? For which GitHub repository would you like to set up a GitHub workflow? (format: user/repository) jiyuujin/pwa_website
```

許可なくワークフローを作成する。

```bash
? Set up the workflow to run a build script before every deploy? Yes
```

Flutter for Web で `flutter build web` を操作する。

```bash
? What script should be run before every deploy? flutter build web
```

PR がマージされたときに展開する。

```bash
? Set up automatic deployment to your site's live channel when a PR is merged? Yes
```

`master` ブランチを使用する。

```bash
? What is the name of the GitHub branch associated with your site's live channel? master
```

これで完了。

```bash
✔  Firebase initialization complete!
```

![](https://i.imgur.com/S8XsZsr.jpg)
