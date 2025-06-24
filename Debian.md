<!-- {% if not disable_header %} -->
# Installing <!-- {{ product }} --> on Debian
<!-- {% endif %} -->

The recommended way to install <!-- {{ product }} --> is to use prebuilt packages from our official release repository.
If the repository is not configured yet,
please [add](#adding-icinga-package-repository) it first
before [installing](#installing-the-package) the package.

All packages we provide are signed with the following [key](https://packages.icinga.com/icinga.key).

## Adding Icinga Package Repository

<!-- {% if subscription_product %} -->
!!! info

    A paid subscription is required to download the packages. Get more information on [icinga.com/subscriptions](https://icinga.com/subscriptions/).

    Ensure that your username and password are configured in your package manager to access restricted repositories and packages.
<!-- {% endif %} -->

Add our GPG Key:

```bash
apt update
apt -y install apt-transport-https wget

wget -O icinga-archive-keyring.deb "https://packages.icinga.com/icinga-archive-keyring_latest+debian$(
 . /etc/os-release; echo "$VERSION_ID"
).deb"

apt install ./icinga-archive-keyring.deb
```

Add the Repository:

<!-- {% if subscription_product %} -->
```bash
DIST=$(awk -F"[)(]+" '/VERSION=/ {print $2}' /etc/os-release); \
 echo "deb [signed-by=/usr/share/keyrings/icinga-archive-keyring.gpg] https://packages.icinga.com<!-- {{ package_repo_url }} -->/debian ${DIST} main" > \
 /etc/apt/sources.list.d/${DIST}-icinga-<!-- {{ repo_file_identifier }} -->.list
 echo "deb-src [signed-by=/usr/share/keyrings/icinga-archive-keyring.gpg] https://packages.icinga.com/<!-- {{ package_repo_url }} -->/debian ${DIST} main" >> \
 /etc/apt/sources.list.d/${DIST}-icinga-<!-- {{ repo_file_identifier }} -->.list

apt update
```
<!-- {% else %} -->
```bash
DIST=$(awk -F"[)(]+" '/VERSION=/ {print $2}' /etc/os-release); \
 echo "deb [signed-by=/usr/share/keyrings/icinga-archive-keyring.gpg] https://packages.icinga.com/debian icinga-${DIST} main" > \
 /etc/apt/sources.list.d/${DIST}-icinga.list
 echo "deb-src [signed-by=/usr/share/keyrings/icinga-archive-keyring.gpg] https://packages.icinga.com/debian icinga-${DIST} main" >> \
 /etc/apt/sources.list.d/${DIST}-icinga.list

apt update
```
<!-- {% endif %} -->

## Installing the Package

Use your distribution's package manager to install the `<!-- {{ package }} -->` package as follows:

```bash
apt install <!-- {{ package }} -->
```

<!-- {% if not raspberry_pi_os %} -->
<!-- {% set debian = True %} -->
<!-- {% endif %} -->
<!-- {% include "02-Installation.md" %} -->
