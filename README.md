# CAR Monitor

A small terminal client for the GWES Central Alert Repository (CAR) API v2.

## Usage

```bash
car
car --page 2
car --limit 5
car --type RWT
car --type SVR --page 2
car --watch
car --help
```

The API returns ten alerts per page. `--watch` polls the selected page every 60 seconds.

## Build locally

Install the build tools and runtime dependencies:

```bash
sudo pacman -S --needed base-devel python python-requests
```

Then, from this directory:

```bash
makepkg -si
```

## Preparing an AUR submission

1. Replace the maintainer placeholder in `PKGBUILD`.
2. Review the script and package metadata.
3. Generate `.SRCINFO` using `makepkg --printsrcinfo > .SRCINFO`.
4. Test the package with `makepkg -si`.
5. Create an AUR account and configure SSH access.
6. Create the `car-monitor` package repository on the AUR, then push `PKGBUILD`, `.SRCINFO`, `car`, `README.md`, and `LICENSE`.

The AUR repository name may already be taken; check before creating it. This project is not affiliated with or endorsed by GWES/CAR.
