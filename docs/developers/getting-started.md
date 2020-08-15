# آغاز به کار

خوشحالیم که تصمیم گرفتید پروژه های خود را در دیپلوکا منتشر کنید. در این متن تمام مراحلی که از ابتدا باید انجام دهید تا نهایتا نرم افزار شما در دیپلوکا منتشر شود توضیح داده شده است. در حقیقت بیشتر این مراحل، مراحلی هستند که شما برای اجرای نرم افزار خود در هر محیط کانتینری (Container) دیگری نیاز به انجام آنها دارید. درصورتی که قبلا تجربه اجرای نرم افزار در محیط Docker یا Kubernetes را داشته باشید این مراحل کاملا برای شما آشنا هستند ولی اگر تجربه استفاده از موارد بالا را نداشتید، نگران نباشید. تمام مراحل با جزئیات و نمونه های کاربردی توضیح داده شده اند.

## ورود به سیستم به عنوان توسعه دهنده
در ابتدا به [کنسول دیپلوکا](https://console.deploca.com/) وارد شده و در آن ثبت نام نمایید. پس از ثبت نام و ورود به پنل کاربری باید نوع کاربری خود را به توسعه دهنده تبدیل کنید. برای این کار در همان صفحه داشبورد در سمت راست روی دکمه `Become a deploca developer` کلیک نمایید. ملاحضه میکنید که در صفحه داشبورد بخش های دیگری با عنوان Developer اضافه شده است.

## ساختن اولین [پروژه](../definitions/#project)
از منوی سمت چپ، زیر منوی Developers را باز کرده و روی Projects کلیک نمایید. در صفحه پروژه ها در گوشه بالا سمت راست تصویر دکمه `Create new App` را کلیک نمایید. در صفحه جدیدی که باز میشود اطلاعات فرم را طبق دستورات زیر وارد نمایید:

  * `App Name`: نامی برای پروژه خود وارد نمایید. در انتخاب نام هیچ محدودیتی وجود ندارد.
  * `Key Name`: نامی یکتا در تمام دیپلوکا میباشد که سیستم پروژه شما را با این نام میشناسد. در انتخاب این نام دقت کرده و توجه نمایید در انتخاب این نام فقط از کاراکترهای کوچک انگلیسی و اعداد و خط تیره و زیرخط میتوانید استفاده نمایید.
  * `Type`: نوع دسترسی پروژه میباشد. در صورتی که `Public` انتخاب شده باشد انتشار های آن درون بازارچه قابل مشاهده خواهد بود و درصورت انتخاب `Private` انتشارات آن هیچ اثری در بازارچه نخواهد داشت.
  * `Description`: توضیحاتی درباره پروژه است که در بازارچه زیر عنوان آن نمایش داده میشود.

پس از اینکه اطلاعات فرم را وارد کردید روی دکمه `Submit` کلیک نموده تا پروژه شما ساخته شود. سپس به صفحه مشخصات پروژه هدایت میشوید. در ابتدا در تب `Details` قرار میگیرید که میتوانید در این بخش توضیحاتی تکمیلی درباره پروژه خود وارد نمایید. این متن جهت اطلاع رسانی بیشتر برای مشتریانی که میخواهند از پروژه شما اطلاع کسب کنند میباشد.

## تعریف ساختار [پروژه](../definitions/#project)
در صفحه اطلاعات پروژه تبی با عنوان `Structure` قرار دارد که ساختار پروژه را در آن میتوان تعریف کرد.
هر پروژه شامل تعدادی [`Branch`](../definitions/#branch-1) و [`Release`](../definitions/#release-2) میباشد. در قسمت های بعد هر یک کاملا توضیح داده شده است. هر برنچ نسخه ای از نرم افزار درحال توسعه میباشد که حاوی سرویسهای نرم افزار و روابط بین آنها و همچنین تنظیماتی که منجر به اجرای نرم افزار میشود، میباشد. در زمان ساخت هر پروژه یک برنچ پیشفرض به نام `development` ساخته میشود که میتوانید درون آن شروع به ثبت سرویسهای نرم افزار خود نمایید.

## افزودن [سرویس](../definitions/#service) بانک اطلاعات
یکی از انواع سرویسهایی که میتوانید به نرم افزار خود اضافه کنید سرویسهای سیستمی میباشند. سرویسهای سیستمی در حقیقت یک ایمیج داکر میباشد که قبلا در دیپلوکا تعریف شده و میتوانید در کنار برنامه خود از آن استفاده کنید که شامل انواع بانک های اطلاعاتی، سیستمهای پیام رسانی و ... میباشد. برای مثال برنامه شما نیاز به بانک اطلاعاتی `postgres` دارد. برای افزودن این سرویس در تب `Structure` روی دکمه `Add System Service` کلیک نمایید. در صفحه افزودن سرویس سیستمی پارامترها را بصورت زیر وارد نمایید:

  * `Select Image`: نام ایمیج داکر سرویس برای مثال `postgres:12.2-alpine` را انتخاب نمایید.
  * `Service Name`: نام سرویس است که بصورت خودکار بعد از انتخاب ایمیج پر میشود ولی میتوانید آنرا به میل خود تغییر دهید. برای مثال بعد از انتخاب ایمیج `postgres:12.2-alpine` نام سرویس بصورت خودکار به `postgres` تنظیم میشود. از آنجایی که نام سرویس یکی از راههای وصل شدن به آن سرویس در درون شبکه داخلی نرم افزار است نام آنرا به `database` تغییر میدهیم که برای اتصال به آن در رشته اتصال نام `database` را قرار دهیم.
  * `Service Visibility`: مشخص میکند که سرویس از بیرون قابل مشاهده است یا خیر. درصورتی که مقدار آنرا روی `Internal` قرار دهید سرویس فقط در شبکه داخلی نرم افزار قابل دسترسی میباشد ولی اگر مقدار آنرا `External` انتخاب کنید زما اجرا آدرسی عمومی به آن اختصاص داده میشود که غیر از نرم افزار، دیگران هم قابلیت دسترسی به آنرا خواهند داشت. پیشنهاد میکنیم برای سرویس بانک اطلاعات مقدار `Internal` را انتخاب کنید.

در نهایت روی دکمه `Submit` کلیک نمایید تا سرویس به پروژه شما اضافه شود.

## افزودن [سرویسهای](../definitions/#service) نرم افزار
نرم افزاری که تهیه کرده اید شامل یک یا چند سرویس میباشد. بعنوان مثال نرم افزار شامل یک پروژه VueJs بعنوان FrontEnd و یک پروژه Asp.net Core بعنوان BackEnd میباشد.

  1. ابتدا مطمئن شوید که هرکدام از پروژه ها دارای فایل Dockerfile جهت ساخت ایمیج داکر باشد. درصورتی که با Dockerfile آشنایی ندارید [این متن](../docker-file/) را مطالعه نمایید.
  2. پروژه های خود را Build کرده و مطمئن باشید که Dockerfile در مسیر اصلی پوشه Build شده قرار گرفته باشد.
  3. محتویات درون پوشه را zip کرده طوری که محتویات پوشه در شاخه اصلی فایل zip قرار داشته باشند.
  4. در تب `Structure` روی دکمه `Add Custom Service` کلیک نمایید. در صفحه افزودن سرویس سفارشی موارد زیر را وارد نمایید:
    * `Upload Image zip file`: فایل zip شده پوشه build شده خود را انتخاب نمایید.
    * `Service Name`: نامی برای سرویس خود انتخاب نمایید. توجه نمایید این نام برای دسترسی از بیرون استفاده خواهد شد.
    * `Service Visibility`: مقدار `External` را انتخاب نمایید که سرویسهای شما از بیرون (مرورگر یا درخواست های http) قابل دسترسی باشد.
    * `Use Entry URL`: در صورتی که این مورد را تیک بزنید آدرس این سرویس، آدرس اصلی برنامه اجرا شده خواهد بود. برای سرویس UI خود این تیک را علامت بزنید. برای اطلاعات بیشتر درباره آدرسهای اختصاص داده شده [این متن](../urls-and-domains/) را مطالعه نمایید.
  5. نهایتا روی دکمه `Submit` کلیک نمایید تا سرویس شما اضافه شود.

## [اجرای](../definitions/#run) نرم افزار
پس از اینکه همه سرویسها را به درستی اضافه کردید زمان آن رسیده که نرم افزار را اجرا نمایید. برای اجرای نرم افزار مراحل زیر را انجام دهید:

  1. در تب `Structure` روی دکمه سبز رنگ `Start` کلیک نمایید.
  2. در صفحه جدیدی که نمایش داده میشود میتوانید تنظیمات اجرا را تغییر داده یا اینکه مستقیما روی دکمه `Install` کلیک نمایید تا به صفحه [اجرا](../definitions/#run) منتقل شوید.
  3. منتظر بمانید تا علامت `Pending` به `Running` تغییر کند. در آن صورت برنامه اجرا شده و در آدرسی که در وسط صفحه مشخص شده قابل دسترسی میباشد.

## [انتشار](../definitions/#release-2) نرم افزار
پس از اینکه مطمئن شدید نرم افزار شما به درستی کار میکند و آماده این است که در بازارچه ابری دیپلوکا منتشر شود، باید از برنچی که شامل نسخه نرم افزار مورد نظر است یک انتشار (Release) جدید بسازید. برای این کار در صفحه مشخصات پروژه در تب `Structure` مطمئن باشید که برنچ مورد نظر شما انتخاب شده باشد. سپس روی دکمه `Create new Branch or Release` کلیک نمایید. در فرمی که به شما نمایش داده میشود موارد زیر را وارد نمایید:

  * `Branch Type`: مقدار `Release` را انتخابب نمایید.
  * `Branch Name`: در حقیقت نشان دهنده نسخه نرم افزار است. برای مثال مقدار `v1.0` را وارد کنید که نشان دهنده نسخه اول نرم افزار شما است.
  * `Description`: اطلاعاتی درباره نسخه نرم افزار است. میتوانید در این قسمت اطلاعاتی شامل مواردی که در این نسخه به نرم افزار اضافه شده است را وارد نمایید.
  * نهایتا روی دکمه `Submit` کلیک نمایید.

تبریک میگوییم. شما اولین نرم افزار خود را در دیپلوکا منتشر کردید.