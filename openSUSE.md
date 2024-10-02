# Installing <!-- {{ product }} --> on openSUSE

The recommended way to install <!-- {{ product }} --> is to use prebuilt packages from our official release repository.
If the repository is not configured yet,
please [add](#adding-icinga-package-repository) it first
before [installing](#installing-the-package) the package.

All packages we provide are signed with the following [key](https://packages.icinga.com/icinga.key).

## Adding Icinga Package Repository

Here’s how to add the official release repository:

```bash
zypper ar -r https://packages.icinga.com/openSUSE/ICINGA-release.repo
```

## Installing the Package

Use your distribution's package manager to install the `<!-- {{ package }} -->` package as follows:

```bash
zypper install <!-- {{ package }} -->
```

<!-- {% set opensuse = True %} -->
<!-- {% include "02-Installation.md" %} -->
