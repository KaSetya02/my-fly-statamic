# Requirements
- PHP >= 7.4.x (8.0+ recommended)
- BCMath PHP Extension
- Ctype PHP Extension
- Exif PHP Extension
- JSON PHP Extension
- Mbstring PHP Extension
- OpenSSL PHP Extension
- PDO PHP Extension
- Tokenizer PHP Extension
- XML PHP Extension
- GD Library or ImageMagick
- Composer

# Statamic CLI Tool

![Statamic 3.0+](https://img.shields.io/badge/Statamic-3.0+-FF269E?style=for-the-badge&link=https://statamic.com)

🌴 Install and manage your **Statamic v3** projects from the command line.

- [Installing the CLI tool](#installing-the-cli-tool)
- [Using the CLI tool](#using-the-cli-tool)
    - [Installing Statamic](#installing-statamic)
    - [Checking Statamic versions](#checking-statamic-versions)
    - [Updating Statamic](#updating-statamic)

## Installing the CLI tool

```
composer global require statamic/cli
```

Make sure to place Composer's system-wide vendor bin directory in your `$PATH` so the `statamic` executable can be located by your system. [Here's how](https://statamic.dev/troubleshooting/command-not-found-statamic).

Once installed, you should be able to run `statamic {command name}` from within any directory.

### GitHub authentication

When you install starter kits, the CLI might present you with a warning that the GitHub API limit is reached. [Generate a Personal acces token](https://github.com/settings/tokens/new) and paste it in your terminal with this command so Composer will save it for future use:

```bash
composer config --global --auth github-oauth.github.com [your_token_here]
```

Read more on this in the [Composer Docs](https://getcomposer.org/doc/articles/authentication-for-private-packages.md).

## Updating the CLI tool

```
composer global update statamic/cli
```

Run this command to update the CLI tool to the most recent published version.

## Using the CLI tool

### Installing Statamic

You may create a new Statamic site with the `new` command:

```
statamic new my-site
```

This will present you with a list of supported starter kits to select from.  Upon selection, the latest version will be downloaded and installed into the `my-site` directory.

You may also pass an explicit starter kit repo if you wish to skip the selection prompt:

```
statamic new my-site statamic/starter-kit-cool-writings
```
### Installing new Starter-kit
```
php please starter-kit:install studio1902/statamic-peak
```

### Checking Statamic versions

From within an existing Statamic project root directory, you may run the following command to quickly find out which version is being used.

```
statamic version
```

### Updating Statamic

From within an existing Statamic project root directory, you may use the following command to update to the latest version.

```
statamic update
```

This is just syntactic sugar for the `composer update statamic/cms --with-dependencies` command.

## Install Statamic into your Laravel app

1. Run php artisan config:clear to make sure your config isn't cached
2. Add the statamic:install command to post-autoload-dump in composer.json.
``
"scripts": {
    "post-autoload-dump": [
        "Illuminate\\Foundation\\ComposerScripts::postAutoloadDump",
        "@php artisan package:discover --ansi",
        "@php artisan statamic:install --ansi", 
        "@php artisan statamic:search:update --all --ansi",
        "@php artisan statamic:static:clear --ansi"
    ],
}
``
3. Install statamic/cms with Composer.

-------------------------------------------------------------------------------------------------------------------------------------------

## Installation project my-statamic instructions

1. run `composer install`
2. run `php please make:user`
3. run `npm i` && `npm run dev`

## Environment file contents

### Development

```env
Dump your .env values here with sensitive data removed.
```

### Production

```env
Dump your .env values here with sensitive data removed. The following is a production example that uses full static caching:
APP_NAME="my-statamic"
APP_ENV=production
APP_KEY="base64:AWbdOVxkEYR+1keG1QprqOeKQdjMzpsWQhukML7RuAQ="
APP_DEBUG=false
APP_URL=

DEBUGBAR_ENABLED=false

LOG_CHANNEL=stack

BROADCAST_DRIVER=log
CACHE_DRIVER=file
QUEUE_CONNECTION=redis
SESSION_DRIVER=file
SESSION_LIFETIME=120

REDIS_HOST=127.0.0.1
REDIS_DATABASE=
REDIS_PASSWORD=null
REDIS_PORT=6379

MAIL_MAILER=smtp
MAIL_HOST=smtp.postmarkapp.com
MAIL_PORT=587
MAIL_ENCRYPTION=tls
MAIL_USERNAME=
MAIL_PASSWORD=
MAIL_FROM_ADDRESS=
MAIL_FROM_NAME="${APP_NAME}"

IMAGE_MANIPULATION_DRIVER=imagick

STATAMIC_LICENSE_KEY=
STATAMIC_THEME=business

STATAMIC_API_ENABLED=false
STATAMIC_REVISIONS_ENABLED=false

STATAMIC_GIT_ENABLED=true
STATAMIC_GIT_PUSH=true
STATAMIC_GIT_DISPATCH_DELAY=5

STATAMIC_STATIC_CACHING_STRATEGY=full
SAVE_CACHED_IMAGES=false
STATAMIC_STACHE_WATCHER=false
STATAMIC_CACHE_TAGS_ENABLED=true

#STATAMIC_CUSTOM_CMS_NAME=
STATAMIC_CUSTOM_LOGO_OUTSIDE_URL="/visuals/client-logo.svg"
#STATAMIC_CUSTOM_LOGO_NAV_URL=
#STATAMIC_CUSTOM_FAVICON_URL=
#STATAMIC_CUSTOM_CSS_URL=
```
# fly.io
## Intalasi fly.io OS Windows
```
powershell -Command "iwr https://fly.io/install.ps1 -useb | iex"
```
## Sign Up
```
flyctl auth signup
```
## Sign In
```
flyctl auth login
```
## Clone our my-fly-statamic app
```
git clone https://github.com/fly-apps/my-fly-statamic.git
```
# Go to the directory
```
cd my-fly-statamic
```
# Deploy to the world
```
fly launch --now
```
