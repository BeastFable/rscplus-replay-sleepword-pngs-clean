# rscplus-replay-sleepword-pngs-clean

This repository contains sleep word images that can be used in your Open RSC server.

## Background

Open RSC servers require sleep word images for sleep words to be robust, otherwise every sleep word you get when sleeping in the game will be `asleep`. Sleep word images should have `.PNG` extension and the file name of these is what the user needs to enter (in most cases) to have their player wake up. Therefore, it is important for sleep word file names and their image content to match.

However, as of this writing, [Open RSC's setup wiki page](https://rsc.vet/wiki/index.php?title=Running_your_own_server) links to a [repository](https://github.com/open-rsc/rsc-captcha-archives) that contains really, really bad sleep words: sleep words that have file names **not** matching the content of the image, leading to player confusion... and overall leading to a bad player experience. 

Luckily, there is a [repository](https://github.com/2003scape/rsc-captcha-archives) that has correct sleep words. It just doesn't present them in a format that is easy to download and instantly plug into your Open RSC server. Well, that is why I created this repository!

## Instructions

1. Clone this repository to your computer, or download the `sleepwords` folder directly.
2. Schedule maintenance for your server, or just shut it down if no one is online.
3. Delete your existing `sleepwords` folder, or rename it to something else.
4. Copy the `sleepwords` folder you downloaded (extracting it first if necessary) to the `<root>/server/conf/server/data` folder, where `<root>` is the root of your Open RSC folder.
5. Start the server. In the console you should see something like: `Loaded 4316 Prerendered Sleepword Images`. This is the approximate number of PNGs in this repository, so it means the new sleep words have been installed successfully!

## Process of obtaining

I obtained these sleep word PNG files via a script. By looping through the [source directory](https://github.com/2003scape/rsc-captcha-archives/tree/master/rscplus-replay-sleepwords/png), skipping any files that had `!INCORRECT!` or `!SUDDENLY-AWOKE!`, extracting sleepwords from each file name, and copying each file to a new location with the name `${sleepword}.png`.

## Limitations

This repository does not include ~300 sleepword files in that `pngs` folder that were too long for Windows to clone down.
