# CAR Monitor 📡

A small command-line client for viewing recent Emergency Alert System (EAS) alerts from the [GWES Central Alert Repository (CAR) API v2](https://alerts.globaleas.org/).

CAR Monitor is written in Python. It should work on most Linux distributions that provide Python 3 and the `requests` library. **You do not need Git, `yay`, or an AUR account to use it.**

> CAR Monitor is an independent community project and is not affiliated with or endorsed by GWES or the CAR service. Alert data and API availability are controlled by the service.

## Features

- View recent alerts from the CAR API
- Choose an alert page
- Limit how many alerts are displayed
- Filter by alert type (for example, `RWT`, `SVR`, `TOR`, or `CEM`)
- Watch a page for newly appearing alerts, polling every 60 seconds

## Requirements

- Python 3
- Python's `requests` library
- Internet access to reach the CAR API

The API returns up to ten alerts per page. The program needs the API to be online.

## Quick start (no Git required)

1. [Download the `car` script directly](https://raw.githubusercontent.com/finnboylol/car-monitor/main/car).
2. Save the downloaded file as `car`.
3. Install Python 3 and the `requests` library using your distribution's package manager (see below).
4. Open a terminal in the folder where you saved the file and run:

   ```sh
   python3 car
   ```

You can also get the repository files by opening the [GitHub repository](https://github.com/finnboylol/car-monitor) and choosing **Code → Download ZIP**. Extract the ZIP, open a terminal in the extracted folder, and run `python3 car`.

Git is optional. If you already have it, you can instead run:

```sh
git clone https://github.com/finnboylol/car-monitor.git
cd car-monitor
python3 car
```

## Install dependencies

Use the commands for your distribution. Package names can differ between releases.

### Debian, Ubuntu, and Linux Mint

```sh
sudo apt update
sudo apt install python3 python3-requests
```

### Arch Linux, EndeavourOS, and Manjaro

```sh
sudo pacman -S python python-requests
```

### Fedora

```sh
sudo dnf install python3 python3-requests
```

### openSUSE

```sh
sudo zypper install python3 python3-requests
```

### Gentoo

```sh
sudo emerge --ask dev-lang/python dev-python/requests
```

### Alpine Linux

```sh
sudo apk add python3 py3-requests
```

For other distributions, install Python 3 and the `requests` library through the distribution's official package manager or documentation. You don't need to install every package manager listed above.

## Usage

Run the program:

```sh
python3 car
```

Show all supported options:

```sh
python3 car --help
```

Examples:

```sh
python3 car --page 2
python3 car --limit 5
python3 car --type RWT
python3 car --type SVR --page 2
python3 car --watch
```

The `--watch` option checks the selected page every 60 seconds. Press **Ctrl+C** to stop monitoring.

## Optional: run it as `car`

You can make the downloaded script executable and run it from its current folder:

```sh
chmod +x car
./car
```

On systems with GNU `install`, you can install it system-wide with:

```sh
sudo install -Dm755 car /usr/local/bin/car
```

Then run:

```sh
car
```

System-wide installation requires administrator permissions. Alternatively, keep running it with `python3 car`; no system-wide installation is needed.

## Arch Linux AUR (optional)

If the package is published on the AUR, Arch Linux users with an AUR helper such as `yay` may be able to install it with:

```sh
yay -S car-monitor
```

The AUR is Arch-specific. Users of other distributions should use the general instructions above. This command will not work until the package has actually been published to the AUR.

## Troubleshooting

- **`ModuleNotFoundError: No module named 'requests'`** — install the `requests` package for your Python 3 installation.
- **`Permission denied`** — try `chmod +x car` or run `python3 car`.
- **`car: command not found`** — run `python3 car` from the folder containing the script, or check that the installed script is in your `PATH`.
- **Connection or API errors** — check your internet connection and whether the CAR API is reachable.

## Licence

This project is distributed under the [MIT License](LICENSE).

## Links

- [Source repository](https://github.com/finnboylol/car-monitor)
- [Download the script](https://raw.githubusercontent.com/finnboylol/car-monitor/main/car)
- [Global EAS CAR API](https://alerts.globaleas.org/)
