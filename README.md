# Python: Asynchronous client for the Open-Meteo API.

[![GitHub Release][releases-shield]][releases]
[![Python Versions][python-versions-shield]][pypi]
![Project Stage][project-stage-shield]
![Project Maintenance][maintenance-shield]
[![License][license-shield]](LICENSE.md)

[![Build Status][build-shield]][build]
[![Code Coverage][codecov-shield]][codecov]
[![Code Quality][code-quality-shield]][code-quality]

[![Sponsor Frenck via GitHub Sponsors][github-sponsors-shield]][github-sponsors]

[![Support Frenck on Patreon][patreon-shield]][patreon]

Asynchronous client for the Open-Meteo API.

## About

Open-Meteo offers free weather forecast APIs for open-source developers and
non-commercial use. No API key is required. You can start using it immediately!

## Installation

```bash
pip install open-meteo
```

## Usage

```python
import asyncio

from open_meteo import OpenMeteo
from open_meteo.models import DailyParameters, HourlyParameters


async def main():
    """Show example on using the Open-Meteo API client."""
    async with OpenMeteo() as ope_meteo:

        # Weather forecast example
        forecast = await open_meteo.forecast(
            latitude=52.27,
            longitude=6.87417,
            current_weather=True,
            daily=list(DailyParameters),
            hourly=list(HourlyParameters),
        )
        print(forecast)

        # Geocoding example
        geocoding = await open_meteo.geocoding(
            name="Enschede",
        )
        print(geocoding)


if __name__ == "__main__":
    asyncio.run(main())
```

## Changelog & Releases

This repository keeps a change log using [GitHub's releases][releases]
functionality. The format of the log is based on
[Keep a Changelog][keepchangelog].

Releases are based on [Semantic Versioning][semver], and use the format
of `MAJOR.MINOR.PATCH`. In a nutshell, the version will be incremented
based on the following:

- `MAJOR`: Incompatible or major changes.
- `MINOR`: Backwards-compatible new features and enhancements.
- `PATCH`: Backwards-compatible bugfixes and package updates.

## Contributing

This is an active open-source project. We are always open to people who want to
use the code or contribute to it.

We've set up a separate document for our
[contribution guidelines](CONTRIBUTING.md).

Thank you for being involved! :heart_eyes:

## Setting up development environment

This Python project is fully managed using the [Poetry][poetry] dependency
manager. But also relies on the use of NodeJS for certain checks during
development.

You need at least:

- Python 3.8+
- [Poetry][poetry-install]
- NodeJS 14+ (including NPM)

To install all packages, including all development requirements:

```bash
npm install
poetry install
```

As this repository uses the [pre-commit][pre-commit] framework, all changes
are linted and tested with each commit. You can run all checks and tests
manually, using the following command:

```bash
poetry run pre-commit run --all-files
```

To run just the Python tests:

```bash
poetry run pytest
```

## Authors & contributors

The original setup of this repository is by [Franck Nijhof][frenck].

For a full list of all authors and contributors,
check [the contributor's page][contributors].

## License

MIT License

Copyright (c) 2021 Franck Nijhof

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

[build-shield]: https://github.com/frenck/python-open-meteo/actions/workflows/tests.yaml/badge.svg
[build]: https://github.com/frenck/python-open-meteo/actions/workflows/tests.yaml
[code-quality-shield]: https://img.shields.io/lgtm/grade/python/g/frenck/python-open-meteo.svg?logo=lgtm&logoWidth=18
[code-quality]: https://lgtm.com/projects/g/frenck/python-open-meteo/context:python
[codecov-shield]: https://codecov.io/gh/frenck/python-open-meteo/branch/master/graph/badge.svg
[codecov]: https://codecov.io/gh/frenck/python-open-meteo
[contributors]: https://github.com/frenck/python-open-meteo/graphs/contributors
[frenck]: https://github.com/frenck
[github-sponsors-shield]: https://frenck.dev/wp-content/uploads/2019/12/github_sponsor.png
[github-sponsors]: https://github.com/sponsors/frenck
[keepchangelog]: http://keepachangelog.com/en/1.0.0/
[license-shield]: https://img.shields.io/github/license/frenck/python-open-meteo.svg
[maintenance-shield]: https://img.shields.io/maintenance/yes/2021.svg
[patreon-shield]: https://frenck.dev/wp-content/uploads/2019/12/patreon.png
[patreon]: https://www.patreon.com/frenck
[poetry-install]: https://python-poetry.org/docs/#installation
[poetry]: https://python-poetry.org
[pre-commit]: https://pre-commit.com/
[project-stage-shield]: https://img.shields.io/badge/Project%20Stage-Concept-red.svg
[pypi]: https://pypi.org/project/open-meteo/
[python-versions-shield]: https://img.shields.io/pypi/pyversions/open-meteo
[releases-shield]: https://img.shields.io/github/release/frenck/python-open-meteo.svg
[releases]: https://github.com/frenck/python-open-meteo/releases
[semver]: http://semver.org/spec/v2.0.0.html