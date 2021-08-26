# Firebase hosting

## Installation

Deploy the website created by Flutter for Web

```bash
firebase init hosting

     ######## #### ########  ######## ########     ###     ######  ########
     ##        ##  ##     ## ##       ##     ##  ##   ##  ##       ##
     ######    ##  ########  ######   ########  #########  ######  ######
     ##        ##  ##    ##  ##       ##     ## ##     ##       ## ##
     ##       #### ##     ## ######## ########  ##     ##  ######  ########

```

Set `build/web` to public directory

```bash
? What do you want to use as your public directory? build/web
```

Maybe not use `index.html`

```bash
? Configure as a single-page app (rewrite all urls to /index.html)? No
```

Start the automatic build

```bash
? Set up automatic builds and deploys with GitHub? Yes
```

Enter the name of the repository you created

```bash
? For which GitHub repository would you like to set up a GitHub workflow? (format: user/repository) jiyuujin/pwa_website
```

Write the workflow without permission

```bash
? Set up the workflow to run a build script before every deploy? Yes
```

Work `flutter build web` in Flutter for Web

```bash
? What script should be run before every deploy? flutter build web
```

Deploy when PR is merged

```bash
? Set up automatic deployment to your site's live channel when a PR is merged? Yes
```

Use `master` branch

```bash
? What is the name of the GitHub branch associated with your site's live channel? master
```

That's all

```bash
✔  Firebase initialization complete!
```

![](https://i.imgur.com/S8XsZsr.jpg)
