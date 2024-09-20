<!-- {% if not disable_header %} -->
# Installing <!-- {{ product }} --> on Debian
<!-- {% endif %} -->

The recommended way to install <!-- {{ product }} --> is to use prebuilt packages from our official release repository.
If the repository is not configured yet,
please [add](#adding-icinga-package-repository) it first
before [installing](#installing-the-package) the package.

All packages we provide are signed with the following [key](https://packages.icinga.com/icinga.key).

## Adding Icinga Package Repository

Here’s how to add the official release repository:

```bash
apt update
apt -y install apt-transport-https wget gnupg

install -d -o root -g root -m 0755 /etc/apt/keyrings

wget -O - https://packages.icinga.com/icinga.key | gpg --dearmor -o /etc/apt/keyrings/icinga.gpg

DIST=$(awk -F"[)(]+" '/VERSION=/ {print $2}' /etc/os-release); \
 echo "deb [signed-by=/etc/apt/keyrings/icinga.gpg] https://packages.icinga.com/debian icinga-${DIST} main" > \
 /etc/apt/sources.list.d/${DIST}-icinga.list
 echo "deb-src [signed-by=/etc/apt/keyrings/icinga.gpg] https://packages.icinga.com/debian icinga-${DIST} main" >> \
 /etc/apt/sources.list.d/${DIST}-icinga.list

apt update
```

## Installing the Package

Use your distribution's package manager to install the `<!-- {{ package }} -->` package as follows:

```bash
apt install <!-- {{ package }} -->
```
<!-- {% include "02-Installation.md" %} -->
