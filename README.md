# TelegramSchoolBot [![MIT License](https://img.shields.io/github/license/paolobarbolini/TelegramSchoolBot.svg?maxAge=2592000)](LICENSE) [![Build Status](https://travis-ci.org/paolobarbolini/TelegramSchoolBot.svg?branch=master)](https://travis-ci.org/paolobarbolini/TelegramSchoolBot)
_Interact with your school website with telegram!_

This bot was created to simplify the interaction with my school's website by using telegram.

It allows us to check the school hours of a class, a teacher or a classroom and to optionally receive notifications when new announcements are posted on their website.

## Compatibility
This bot has only been tested on my school's website which is using the [Yoomla CMS](https://www.joomla.org/) with the [JSN Epic](https://www.joomlashine.com/joomla-templates/jsn-epic-joomla-template-details.html) template.
The bot searches for and article on the left side of the screen which contains a link pointing to a page created with [Orario Facile 8](https://www.orariofacile.com/).
The path to the page created with ``Orario Facile`` must start with ``/web_orario`` or ``/weborario``.

It is licensed under the [MIT License](LICENSE), which basically allows you to do whatever you want with it as long as you preserve the copyright and license notices.


## Required dependencies
This bot requires the following dependencies to work:

* Make (apt: `build-essential`)
* Python 3 (apt: `python3`)
* PIP (apt: `python3-pip`)
* Virtualenv (apt: `python-virtualenv` pip: `virtualenv`)
* wkhtmltopdf (apt: `wkhtmltopdf`)
* Xvfb (apt: `xvfb`)

You can easily install them with the following commands:

```
$ sudo apt install build-essential python3 python3-pip python-virtualenv wkhtmltopdf xvfb
```

## Setup
All of the configurations are stored in the `config.json` file, to create it run:

```
$ make init
```

Edit the `config.json`:

```json
{
  "telegram_token": "BOT-API-KEY",
  "school_website": "URL-OF-YOUR-SCHOOL-WEBSITE",
  "owner": "@YOUR-TELEGRAM-USERNAME",
  "database_url": "THE_DATABASE_URL"
}
```

The parameters are:

* `telegram_token` is the api key of your telegram bot, you can [generate one here](https://t.me/BotFather).
* `school_website` is the url of the homepage of your school website.
* `owner` is the username on telegram you wish to be contacted.
* `database_url` is the database connection url (for example `sqlite:///database.db` for a sqlite database)

To create the database tables run:

```
$ make initdb
```

## Running the bot
To start the bot run the following command:

```
$ make run
```

The first time it will take a few minutes to start because it has to build the virtualenv and install the dependencies.

## Contributing
I highly appreciate your contributions in the matter of fixing bugs and optimizing the bot source code, but i won't accept your pull request if it adds features that i don't want to get added to it or if it breaks compatibility with my school website.

If you want to talk to me about a feature you would like to add please open an issue and i will answer to you as soon as possible.
