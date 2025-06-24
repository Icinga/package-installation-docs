# Installing <!-- {{ product }} --> on Fedora

The recommended way to install <!-- {{ product }} --> is to use prebuilt packages from our official release repository.
If the repository is not configured yet,
please [add](#adding-icinga-package-repository) it first
before [installing](#installing-the-package) the package.

All packages we provide are signed with the following [key](https://packages.icinga.com/icinga.key).

## Adding Icinga Package Repository

Here’s how to add the official release repository:

```bash
rpm --import https://packages.icinga.com/icinga.key
curl https://packages.icinga.com<!-- {{ package_repo_url }} -->/fedora/ICINGA-release.repo -o /etc/yum.repos.d/ICINGA-<!-- {{ repo_file_identifier }} -->.repo
```

## Installing the Package

Use your distribution's package manager to install the `<!-- {{ package }} -->` package as follows:

```bash
dnf install <!-- {{ package }} -->
```

<!-- {% set fedora = True %} -->
<!-- {% include "02-Installation.md" %} -->
