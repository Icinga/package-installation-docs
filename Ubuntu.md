# Installing <!-- {{ product }} --> on Ubuntu

The recommended way to install <!-- {{ product }} --> is to use prebuilt packages from our official release repository.
If the repository is not configured yet,
please [add](#adding-icinga-package-repository) it first
before [installing](#installing-the-package) the package.

All packages we provide are signed with the following [key](https://packages.icinga.com/icinga.key).

## Adding Icinga Package Repository

<!-- {% if subscription_product %} -->
!!! info

    A paid subscription is required to download the packages. Get more information on [icinga.com/pricing](https://icinga.com/pricing/).

    Ensure that your username and password are configured in your package manager to access restricted repositories and packages.
<!-- {% endif %} -->

Add our GPG Key:

```bash
apt update
apt -y install apt-transport-https wget

wget -O icinga-archive-keyring.deb "https://packages.icinga.com/icinga-archive-keyring_latest+ubuntu$(
 . /etc/os-release; echo "$VERSION_ID"
).deb"

apt install ./icinga-archive-keyring.deb
```

Add the Repository:

<!-- {% if subscription_product %} -->
```bash
cat >/etc/apt/sources.list.d/icinga-<!-- {{ repo_file_identifier }} -->.sources <<EOF
Types: deb deb-src
URIs: https://packages.icinga.com<!-- {{ package_repo_url }} -->/ubuntu/
Suites: $(. /etc/os-release; echo "$VERSION_CODENAME")
Components: main
Signed-By: /usr/share/keyrings/icinga-archive-keyring.gpg
EOF

apt update
```
<!-- {% else %} -->
```bash
cat >/etc/apt/sources.list.d/icinga.sources <<EOF
Types: deb deb-src
URIs: https://packages.icinga.com/ubuntu/
Suites: icinga-$(. /etc/os-release; echo "$VERSION_CODENAME")
Components: main
Signed-By: /usr/share/keyrings/icinga-archive-keyring.gpg
EOF

apt update
```
<!-- {% endif %} -->

## Installing the Package

Use your distribution's package manager to install the `<!-- {{ package }} -->` package as follows:

```bash
apt install <!-- {{ package }} -->
```

<!-- {% set ubuntu = True %} -->
<!-- {% include "02-Installation.md" %} -->
