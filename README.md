# python-app - Python App GitHub Template

[![Linux](https://svgshare.com/i/Zhy.svg)](https://docs.microsoft.com/en-us/windows/wsl/tutorials/gui-apps)
[![Windows](https://svgshare.com/i/ZhY.svg)](https://svgshare.com/i/ZhY.svg)
[![GitHub license](https://img.shields.io/github/license/ThomasByr/python-app)](https://github.com/ThomasByr/python-app/blob/master/LICENSE)
[![GitHub commits](https://badgen.net/github/commits/ThomasByr/python-app)](https://GitHub.com/ThomasByr/python-app/commit/)
[![GitHub latest commit](https://badgen.net/github/last-commit/ThomasByr/python-app)](https://gitHub.com/ThomasByr/python-app/commit/)
[![Maintenance](https://img.shields.io/badge/maintained%3F-yes-green.svg)](https://GitHub.com/ThomasByr/python-app/graphs/commit-activity)

[![Python Package](https://github.com/ThomasByr/python-app/actions/workflows/python-package.yml/badge.svg)](https://github.com/ThomasByr/python-app/actions/workflows/python-package.yml)
[![GitHub release](https://img.shields.io/github/release/ThomasByr/python-app)](https://github.com/ThomasByr/python-app/releases/)
[![Author](https://img.shields.io/badge/author-@ThomasByr-blue)](https://github.com/ThomasByr)

1. [✏️ Setup](#️-setup)
2. [👩‍🏫 Usage](#-usage)
3. [🧑‍🏫 Contributing](#-contributing)
4. [⚖️ License](#️-license)
5. [🔄 Changelog](#-changelog)
6. [🐛 Bugs and TODO](#-bugs-and-todo)
7. [🎨 Logo and Icons](#-logo-and-icons)

Like this template ? We have other templates ready for you ⭐ !

- [python-app](https://github.com/ThomasByr/python-app) - Python App GitHub Template
- [c-cpp-app](https://github.com/ThomasByr/c-cpp-app) - C/C++ App GitHub Template

## ✏️ Setup

This repository is a template for a python app. It is meant to be used as a starting point for any python app. As such, this document is not meant to be _entirely_ read as is, but rather to be used as a base for your own documentation. Nevertheless, you can still find usefull information here since it is a great way to see how the template is used. You will still need to do some (minor) work when using this template - like changing the name of the app, the name of the author, etc. - but it should be fairly easy to do.

> <picture>
>   <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/Mqxx/GitHub-Markdown/main/blockquotes/badge/light-theme/info.svg">
>   <img alt="Info" src="https://raw.githubusercontent.com/Mqxx/GitHub-Markdown/main/blockquotes/badge/dark-theme/info.svg">
> </picture><br>
>
> Please note we do not officially support Windows or MacOS, but we do provide some instructions for those who want to use it on these platforms.

You do not explicitly need a conda environment for the bot to run. But it is always recommended nontheless, especially because the next LTS of Ubuntu won't let users pip-install anything without a virtual environment. At the time of writing, this app `python >= 3.11` to run.

First, [🔗 generate](https://github.com/ThomasByr/python-app/generate) a new repository from this template. Then, clone it and `cd` into it :

```bash
# Clones the repository
git clone <your-repository-url>
cd <your-repository-name>
```

You can create and activate a conda environment with the following commands (make sure to give it a name in [environment.yml](environment.yml)) :

```bash
# Creates environment and install dependencies
conda env create -f environment.yml -y
conda activate <name>
```

Finally, run the app in the background with `nohup` and `tee` :

```bash
# Runs the app in the background
nohup python main.py 2>&1 | tee -a .log &
```

or in the foreground :

```bash
# Runs the app (lets you Ctrl+C to stop it)
python main.py
```

## 👩‍🏫 Usage

In this section, we generally present the app, put a nice screenshot of the GUI - if any, or the CLI, and explain how to use it. Here is an example of a CLI app :

```py
import argparse


def get_parser() -> argparse.ArgumentParser:
  """Returns the parser for the CLI app."""
  parser = argparse.ArgumentParser(description='This is a CLI app.')
  parser.add_argument(
    '-v',
    '--verbose',
    action='store_true',
    help='Increase output verbosity',
  )
  return parser


if __name__ == '__main__':
  parser = get_parser()
  args = parser.parse_args()

  if args.verbose:
    print('Verbosity turned on')

```

For a GUI app, you can use [CustomTkinter](https://github.com/TomSchimansky/CustomTkinter).

We also provide premade config files for linting, testing and formating purposes. Please make sure you have the required dependencies installed before running the commands below. Of course you can tweak these files to match your needs, but they should be good enough for most use cases.

```bash
# Linting
python -m pylint src

# Testing
python -m pytest

# Formating
yapf -ir .
```

Last is our [scripts folder](scripts/) which contains

- a bash script that acts as `dos2unix` for _malicious_ Windows users
- a python file to automatically build the "changelog" section of this README

In the root directory, when needed, type :

```bash
bash scripts/crlf-lf.bash
```

```bash
python scripts/changelog.py
```

## 🧑‍🏫 Contributing

If you ever want to contribute, either request the contributor status, or, more manually, fork the repo and make a pull request !

We are using [yapf](https://github.com/google/yapf) to format the code, so make sure you have it installed and run :

```ps1
yapf -ir .
```

> The standard procedure is :
>
> ```txt
> fork -> git branch -> push -> pull request
> ```
>
> Note that we won't accept any PR :
>
> - that does not follow our Contributing Guidelines
> - that is not sufficiently commented or isn't well formated
> - without any proper test suite
> - with a failing or incomplete test suite

Happy coding ! 🙂

## ⚖️ License

> <picture>
>   <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/Mqxx/GitHub-Markdown/main/blockquotes/badge/light-theme/warning.svg">
>   <img alt="Warning" src="https://raw.githubusercontent.com/Mqxx/GitHub-Markdown/main/blockquotes/badge/dark-theme/warning.svg">
> </picture><br>
>
> This repository is a template. Working source code is licensed under AGPL, the rest is unlicensed. If you whish not to use source code, please use the license of your choice. The following license only applies to the template itself and is not legal advice. <FONT COLOR="#ff0000"><u>The license of this repo does not apply to the resources used in it.</u></FONT> Please check the license of each resource before using them.

This project is licensed under the AGPL-3.0 new or revised license. Please read the [LICENSE](LICENSE.md) file. Additionally :

- Redistributions of source code must retain the above copyright notice, this list of conditions and the following disclaimer.

- Redistributions in binary form must reproduce the above copyright notice, this list of conditions and the following disclaimer in the documentation and/or other materials provided with the distribution.

- Neither the name of the python-app authors nor the names of its contributors may be used to endorse or promote products derived from this software without specific prior written permission.

```LICENSE
python-app - Python App GitHub Template
Copyright (C) 2023 Thomas BOUYER

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU Affero General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the
GNU Affero General Public License for more details.

You should have received a copy of the GNU Affero General Public License
along with this program. If not, see <http://www.gnu.org/licenses/>.
```

## 🔄 Changelog

Please read the [changelog](changelog.md) file for the full history !

<details>
  <summary>  Title for major version (click here to expand) </summary>

**v0.1** title for minor version

- list
- of
- changes

</details>

## 🐛 Bugs and TODO

**TODO** (first implementation version)

- [x] TODO 1
- [ ] TODO 2

**Known Bugs** (latest fix)

- ~~BUG 1~~ (fixed in v0.1)
- BUG 2

## 🎨 Logo and Icons

Unless otherwise stated, all icons and logos are made by the author.
Copyright (C) 2023 Thomas BOUYER, all rights reserved.

Tools used :

- [Microsoft Designer](https://designer.microsoft.com/)
- [Clip Studio Paint](https://www.clipstudio.net/en)
- [Canva](https://www.canva.com/)
