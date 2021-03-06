# رابط خط فرمان

## نصب ابزار CLI
جهت نصب ابزار CLI از نصب بودن `nodejs` و `npm` در سیستم عامل خود مطمئن شوید. سپس دستور زیر را در ترمینال وارد نمایید:

``` {.sh linenums="1"}
npm i -g @deploca/cli
```

کمی صبر نمایید تا ابزار، دانلود و نصب شود.

## به روز رسانی یک برنچ با پکیج build شده در سیستم
درصورتی که یک پکیج را در سیستم خود آماده کرده اید و قصد بروز رسانی برنچ دیپلوکا را دارید از دستور زیر استفاده نمایید:

``` {.sh linenums="1"}
deploca package:deploy \
        --target <target> \
        --token <your-api-token> \
        --path <package-path>
```

پارامتر ها بصورت زیر میباشند:

  * `target`: نام کلیدی پروژه بهمراه نام برنچ با فرمت `app-key/branch`. بعنوان مثال `knowledgebase/development` به این معنی است که بروز رسانی در پروژه `knowledgebase` برنچ `development` انجام شود. درصورتی که نام برنچ را ذکر نکنید، برنچ `development` درنظر گرفته میشود.
  * `token`: مقدار api-token را میتوانید از تنظیمات Account در پنل خود مشاهده نمایید یا توکن جدیدی ساخته و از آن استفاده نمایید. برای اطلاع بیشتر از توکن ها [این صفحه](../api-tokens/) را مطالعه نمایید.
  * `path`: آدرس پوشه ای که محتویات پکیج در آن قرار دارد. درصورتی که ترمینال در همان پوشه قرار گرفته میتوانید از `.` استفاده نمایید.
