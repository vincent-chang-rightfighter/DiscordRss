# Discord RSS
Send new RSS feed entries to discord via a webhook. 

## This repository has been deprecated,please consider using [New Repo](https://github.com/vincent-chang-rightfighter/DiscordRSS-Improve) 

## Usage
1. Install dependencies - `python3 -m pip install -r requirements.txt`

>安裝依賴 - `python3 -m pip install -r requirements.txt`

2. Create your config.yaml file (see [sample_config.yaml](sample_config.yaml))

>建立你的 config.yaml 檔案 ( 參考 [sample_config.yaml](sample_config.yaml) )

3. Run the script - `python3 main.py` 

>執行程式 `python3 main.py` 

>我寫了一個 while true batch,自動化每5秒執行一次

>`sh run.sh`

To make this script check for new entries periodically, I would recommend using something like cron to schedule the script to run automatically.


## Configuration
A sample config file is provided in [sample_config.yaml](sample_config.yaml).

Embed properties can either have a static value set, or derive information from the RSS feed entry.
Note that as per discord/discord.py limitations, the colour value must be an integer and that the embed must have at least either a title or description.

Values that are to be taken from the RSS feed should be prefixed with `$` followed by `feed` or `entry` to denote the data source. 
Child fields can be accessed by appending a `.` and then the name of the field.

For example, `$feed.image.href` or `$entry.summary`

For the fields that can be extracted, see the [Feedparser documentation](https://feedparser.readthedocs.io/en/latest/reference.html).
