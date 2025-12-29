# Quick Start

## Usage Combinations

||Serverless usage|Self-hosting|
|-|-|-|
| **Configuration** |Via settings in database file|Via settings in database file|
| **Database** |Your own database file that you bind via the browser File API|Your own database file that you bind via the browser File API or database file stored on a server|

## Serverless usage (simplest choice)

Download the database template (read more about how to edit the file under [Create the dataset](./create-dataset)

[https://github.com/plans-coding/immer-in-bewegung/raw/refs/heads/main/personal/bewegung.db](https://github.com/plans-coding/immer-in-bewegung/raw/refs/heads/main/personal/bewegung.db)

To bind your own SQLite file to the online application, go to

<CodeBlock>https://online.bewegung.app/?p=source</CodeBlock>

Afterwards just start browsing your trips at

<CodeBlock>https://online.bewegung.app/</CodeBlock>

## Host on your own server

If you want your app available from many devices without need to bind it specifillay on each device, you can develop your instance to your own server instead.

### Step 1 − Download files
Go to the directory where you want to place your files, e.g.
```
cd /var/www/iib
```
Download the [latest release](https://github.com/plans-coding/immer-in-bewegung/releases/) to your home directory

<CodeBlock>wget https://github.com/plans-coding/immer-in-bewegung/archive/refs/tags/<LatestVersion />.tar.gz</CodeBlock>

### Step 2 − Edit settings

Specify your settings and the path to the database file in `personal/settings.json`. Read more at [Settings](./settings).
