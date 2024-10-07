# Installing <!-- {{ product }} --> on Amazon Linux

The recommended way to install <!-- {{ product }} --> is to use prebuilt packages from our official release repository.
If the repository is not configured yet,
please [add](#adding-icinga-package-repository) it first
before [installing](#installing-the-package) the package.

All packages we provide are signed with the following [key](https://packages.icinga.com/icinga.key).

## Adding Icinga Package Repository

!!! info

    A paid repository subscription is required for Amazon Linux 2 repositories. Get more information on
    [icinga.com/subscription](https://icinga.com/subscription).

    Don't forget to fill in the username and password section with appropriate credentials in the local .repo file.

Here’s how to add the official release repository:

```bash
curl https://packages.icinga.com/subscription/amazon/ICINGA-release.repo -o /etc/yum.repos.d/ICINGA-release.repo
```

## Installing the Package

Use your distribution's package manager to install the `<!-- {{ package }} -->` package as follows:

=== "Amazon Linux 2023"

    ```bash
    dnf install <!-- {{ package }} -->
    ```

=== "Amazon Linux 2"

    ```bash
    yum install <!-- {{ package }} -->
    ```

<!-- {% set amazon_linux = True %} -->
<!-- {% include "02-Installation.md" %} -->
