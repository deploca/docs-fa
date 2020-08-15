# پکیج ها در دیپلوکا


### ساختار فایلهای پکیج

    deploca-package.yml    # The package configuration file.
    ui-app/
        Dockerfile         # The docker image build statements
        ...                # Other files.
    backend-app/
        Dockerfile         # The docker image build statements
        ...                # Other files.


### نمونه فایل deploca-package.yml

``` {.yaml linenums="1"}
version: '1.0'

services:
    database:
        image: postgres:12.2-alpine
    backend-app:
        source: backend-app
        external: yes
    ui-app:
        source: ui-app
        external: yes
        root_url: yes
```
