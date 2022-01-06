# quranicaudio-dl

*quranicaudio-dl* is a command-line program to download audio/MP3 files of various Quran recitations from [QuranicAudio][1].

[![License][license-image]][license-link]
[![Release][release-image]][release-link]

## Installation

1. Clone this repo.

   ```shell
   git clone https://github.com/fathyar/quranicaudio-dl.git
   ```

2. Go to the cloned repo directory.

   ```shell
   cd quranicaudio-dl/
   ```

3. Symlink `quranicaudio-dl` to one of your `$PATH` environment variable directories e.g. `~/.local/bin/`.

   ```shell
   ln -s "$(pwd)"/quranicaudio-dl ~/.local/bin/
   ```

## Usage

### Options/Flags

```
-h, --help                Show this help and exit
--version                 Print program version and exit

-r, --recitation <name>   Specify the recitation name
```

### Obtaining the recitation name

As for the recitation name, it is obtained from the audio file URL (unfortunately, for the time being) *manually*. Here is a guide on how to obtain the recitation name.

1. On your browser, go to [QuranicAudio][1] website.
2. Navigate to one of the recitation pages e.g. [this page][2].
3. On the recitation page, hover on one of the surahs. You will see a download link in the form of a "Download" button shown. Right click on it and copy the link address.
4. Paste the link somewhere e.g. a terminal window. Now let's see the link/URL that we've got.
   ```
   https://download.quranicaudio.com/quran/mishaari_raashid_al_3afaasee/001.mp3
   ```
   As seen in the URL above, the string `mishaari_raashid_al_3afaasee` is what we're looking for which is then passed on as an argument to the `-r` or `--recitation` option.

   Another URL example from [another page][3]:
   ```
   https://download.quranicaudio.com/quran/bandar_baleela/complete/001.mp3
   ```
   In the URL above, `bandar_baleela/complete` would be the string we look for.

   In a nutshell, we look for the string between the URL string `https://download.quranicaudio.com/quran/` and the surah number `/nnn.mp3`.
   ```
   https://download.quranicaudio.com/quran/<recitation-name>/nnn.mp3
   https://download.quranicaudio.com/quran/<recitation-name/path>/nnn.mp3
   ```

### Usage examples

Basic usage:

```shell
quranicaudio-dl -r <recitation-name>
# or
quranicaudio-dl --recitation <recitation-name>
```

Example:

```shell
quranicaudio-dl -r mishaari_raashid_al_3afaasee
```

The above example will download audio (mp3) files of all surahs (114 files) from the recitation of `mishaari_raashid_al_3afaasee` and store the files in current directory where the command is executed.

If you want to store the files in a specific directory, you can create the directory first and then `cd` to it before running the command. For example:

```shell
# create a new directory
mkdir 'Mishari Rashid al-Afasy'

# go to the directory
cd 'Mishari Rashid al-Afasy'/

# run the command
quranicaudio-dl -r mishaari_raashid_al_3afaasee
```

## Changelog

See [CHANGELOG.md](/CHANGELOG.md) file.

## License

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program.  If not, see <https://www.gnu.org/licenses/>.

## Author

Copyright © 2021–2022 Fathy AR

[1]: https://quranicaudio.com
[2]: https://quranicaudio.com/quran/5
[3]: https://quranicaudio.com/quran/160
[license-link]: #license
[release-link]: https://github.com/fathyar/quranicaudio-dl/releases
[license-image]: https://img.shields.io/badge/license-GPLv3-maroon.svg
[release-image]: https://img.shields.io/github/v/release/fathyar/quranicaudio-dl
