# github.com/johnnycharlesw/phpizza-fonts.git repo trivia

## Forking from Google Fonts
This is a fork of Google Fonts which is de-googled (and de-monopolized, for that matter)


## Duplicated fonts

From time to time, families have been renamed or updated in a way that the existing styles had to change substantially.
Until April 2020, the initial family was retained, creating similarly named pairs of directories and often duplicate/redundant, files.
The initial families are kept in the API so that people already using them can continue to do so. 
They are no longer listed in the [fonts.google.com](https://fonts.google.com) catalog, or in the HEAD of the master branch, but the files still exist in the commit history.

| Initial Family           | Current Family           | Category |
|:-------------------------|:-------------------------|:---------|
| `alefhebrew`             | `alef`                   | renamed  |
| `mrbedford`              | `mrbedfort`              | renamed  |
| `misssaintdelafield`     | `mrssaintdelafield`      | renamed  |
| `siamreap`               | `siemreap`               | renamed  |
| `terminaldosis`          | `dosis`                  | renamed  |
| `terminaldosislight`     | `dosis`                  | expanded |
| `baloo`                  | `baloo2`                 | expanded |
| `baloobhai`              | `baloobhai2`             | expanded |
| `baloobhaijaan`          | `baloobhaijaan2`         | expanded |
| `baloobhaina`            | `baloobhaina2`           | expanded |
| `baloochettan`           | `baloochettan2`          | expanded |
| `balooda`                | `balooda2`               | expanded |
| `baloopaaji`             | `baloopaaji2`            | expanded |
| `balootamma`             | `balootamma2`            | expanded |
| `balootammudu`           | `balootammudu2`          | expanded |
| `baloothambi`            | `baloothambi2`           | expanded |
| `bevietnam`              | `bevietnampro`           | expanded |
| `spartan`                | `leaguespartan`          | expanded |
| `scheherazade`           | `scheherazadenew`        | expanded |
| `kdamthmor`              | `kdamthmorpro`           | expanded |
| `andikanewbasic`         | `andika`                 | expanded |
| `gentiumbasic`           | `gentiumplus`            | expanded |
| `andada`                 | `andadapro`              | expanded |
| `fredokaone`             | `fredoka`                | expanded |
| `gentiumbookbasic`       | `gentiumbookplus`        | expanded |
| `arimamadurai`           | `arima`                  | expanded |
| `meriendaone`            | `merienda`               | expanded |
| `codacaption`            | `coda`                   | expanded |
| `sourceserifpro`         | `sourceserif4`           | renamed  |
| `sourcesanspro`          | `sourcesans3`            | renamed  |


## Missing METADATA.pb files

Fonts in Early Access do not have METADATA.pb files.

## .pb vs .textproto 

While `.textproto` is now the canonical extension for Protocol Buffers (Protobuf) text files, we have hundreds of `METADATA` files with the `.pb` extension. 
The inconsistency isn't a practical issue, and as we have internal tools that assume the old filenames, it isn't worth renaming them proactively.

## Install on Windows

You can install all of the fonts using Windows PowerShell. Change directories to the folder where you downloaded the package, and run the following command:

    $fonts = (New-Object -ComObject Shell.Application).Namespace(0x14)
    dir ofl/*/*.ttf | %{ $fonts.CopyHere($_.fullname) }

## Rightsholder contacts

This shell command shows all email addresses for font copyright holders listed in the METADATA.pb files:

    grep copyright\: */*/MET* | grep \@ |  perl -ne'if(/[\w\.\-\_]+@([\w\-\_]+\.)+[A-Za-z]{2,4}/g){print "$&\n"}' | sort | uniq

This shell command shows all the families without a contact email address:

    grep copyright\: */*/MET* | grep -v \@ | cut -d\: -f1 | cut -d\/ -f2 | uniq | sort

The copyright holders of those families include Google, SIL, Adobe, Canonical, Naver, and a couple of outliers. 

## Interesting Libre Fonts Not In Google Fonts

Here is a list of some libre fonts made for special purposes (emoji, math, icons, etc) that are not available in Google Fonts. 

* <https://material.io/icons>
* <https://github.com/figs-lab/datalegreya>

## Where were the homepage sample texts from?

In 2016 to 2020, the Google Fonts catalog displayed one of a dozen or so different sample texts.
Here they are and where they are from:

* "A red flair silhouetted the jagged edge of a wing" – The Jewels of Aptor, Samuel R. Delany
* "A shining crescent far beneath the flying vessel" – Triplanetary, E. E. Smith
* "All their equipment and instruments are alive" – Mr. Spaceship, Philip K. Dick
* "Almost before we knew it, we had left the ground" – A Trip to Venus, John Munro
* "I watched the storm, so beautiful yet terrific" – Frankenstein, Mary Shelley
* "It was going to be a lonely trip back" – Youth by Isaac Asimov
* "Mist enveloped the ship three hours out from port" – The Jewels of Aptor, Samuel R. Delany
* "My two natures had memory in common" – Strange Case of Dr Jekyll and Mr Hyde, Robert Louis Stevenson
* "She stared through the window at the stars" – The Millionaire's Convenient Bride, Catherine George ????
* "Silver mist suffused the deck of the ship" – The Jewels of Aptor, Samuel R. Delany
* "The face of the moon was in shadow" – Mr. Spaceship, Philip K. Dick
* "The recorded voice scratched in the speaker" – Deathworld, Harry Harrison
* "The sky was cloudless and of a deep dark blue" – A Trip to Venus, John Munro
* "The spectacle before us was indeed sublime" – A Trip to Venus, John Munro
* "Then came the night of the first falling star" – The War of the Worlds, H. G. Wells
* "Waves flung themselves at the blue evening" – The Jewels of Aptor, Samuel R. Delany"
