# Installing <!-- {{ product }} --> on Amazon Linux

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
curl https://packages.icinga.com<!-- {{ package_repo_url }} -->/amazon/ICINGA-release.repo -o /etc/yum.repos.d/ICINGA-<!-- {{ repo_file_identifier }} -->.repo
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
