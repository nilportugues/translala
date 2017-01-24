Translala
==================

You new toolbox to manage translations of your projects.
It provide command to translate your missing translation, detect commons translations, report translation stats and detect dead translation.
(First version work with yml file only)

## Install
Grab the translala.phar and move it to your bin.

``` bash
$ git clone git@github.com:Translala/translala.git && cp translala/build/translala.phar /usr/local/bin/translala
```

## Configure your project
Here is what a complete `.translation.yml` file look like. You can add many path for each of your translation path.
The translala report are dumped in your export path.

``` yml
master_language: fr
languages:
    - en
    - fr
    - da
paths:
    - ./app/Resources/translations/
export_path: /tmp

api:
    google: my_very_secret_api_key

project_path: ./
```

## Stats command
`translala translala:project:stats --config ./app/Resources/translations/.translation.yml`
The stats command report project stats about translations achievements.
![](http://www.updemia.com/static/e/a/xl/5887cc5f5c697.png)

## Common command
`translala translala:project:common --config ./app/Resources/translations/.translation.yml`
Do you have a different translation key for each "save" buttons of your form? With many locales, it can have a significant cost.
![](http://www.updemia.com/static/e/a/xl/5887cc9c35428.png)

## Dead command
`translala translala:project:dead --config ./app/Resources/translations/.translation.yml`
This search each translations keys in your project to help you find dead key.
![](https://i.imgflip.com/11z8lt.jpg)


## Translation command
`translala translala:project:translate --config ./app/Resources/translations/.translation.yml`
Using php-translation it translate missing or empty keys for each locale in each file.

## Contribution
Feel free to remove array manipulation, fix typo and create new file parser with a PR ;)