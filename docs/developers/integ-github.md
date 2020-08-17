# اتصال به گیت هاب

درصورتی که کدهای خود را در گیت هاب نگهداری میکنید، میتوانید repository خود را به دیپلوکا متصل نمایید.

## استفاده از Github Actions
اکشن زیر بعد از هر `commit` در برنچ `master` اجرا شده و بعد از build کردن همه سرویسها و ایجاد `package`، آنرا به برنچ `development` در پروژه `my-app` در دیپلوکا ارسال میکند.

``` {.yaml linenums="1"}
push:
  branches:
    - master

jobs:
  build_and_deploy:
    runs-on: ubuntu-latest
    name: Build projects and deploy them to deploca.com
    steps:
      - name: Checkout Action
        uses: actions/checkout@v2
      - name: Setup .NET Core
        uses: actions/setup-dotnet@v1.5.0
        with:
          dotnet-version: 3.1.x
      - name: Build all projects
        run: |
          chmod +x build.sh
          ./build.sh
      - name: Upload action
        uses: deploca/deploca-upload-action@0.1.0
        with:
          path: _publish
          target: my-app/development
          token: ${{ secrets.DEPLOCA_API_TOKEN }}
```

!!! warning "نکته مهم"
    حتما توکن ها را بصورت secret در github تعریف کنید. به دلیل اینکه توکن ها مانند رمز عبور شما میباشند. درصورتی که مقدار توکن شما در دسترس دیگران قرار بگیرد، آنها میتوانند با سطح دسترسی شما پروژه های شما را ویرایش نمایند. برای اطلاع بیشتر از توکن ها [این صفحه](../api-tokens/) را مطالعه نمایید.