# Installing <!-- {{ product }} --> on SLES

The recommended way to install <!-- {{ product }} --> is to use prebuilt packages from our official release repository.
If the repository is not configured yet,
please [add](#adding-icinga-package-repository) it first
before [installing](#installing-the-package) the package.

All packages we provide are signed with the following [key](https://packages.icinga.com/icinga.key).

## Adding Icinga Package Repository

!!! info

    A paid subscription is required to download the packages. Get more information on [icinga.com/subscriptions](https://icinga.com/subscriptions/).

    Ensure that your username and password are configured in your package manager to access restricted repositories and packages.

Here’s how to add the official release repository:

```bash
zypper ar -r https://packages.icinga.com/subscription/sles/$releasever/release/ icinga-stable-release
```

## Installing the Package

Use your distribution's package manager to install the `<!-- {{ package }} -->` package as follows:

```bash
zypper install <!-- {{ package }} -->
```

<!-- {% set sles = True %} -->
<!-- {% include "02-Installation.md" %} -->
