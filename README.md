# Virgool-APIs
The virgool.io website's, API documentions that created with other developers, of all of them :)
<div dir="rtl">
این مخزن برای دسترسی به api ویرگول و استفاده دز انواع نرم افزار ها تشکیل شده. از آنجایی که ویرگول به خودی خود داکیومنتی برای apiاش ارائه نداده است، این ریپازیتوری میتواند به صورت "ناکامل" این مساله را حل کند.
  
**سلب مسئولیت** : 
 بدیهیست ویرگول به دلیل مخالفت با ارائه api این عمل را انجام داده است. بنابر این تمام مسئولیت های عمل صورت گرفته، تنها بر عهده فردیست که آن قسمت خاص از داکیومنت را به صورت پول ریکوئست تولید کرده است
  
برای تکمیل کردن تنها پول ریکوئست بفرستید.
  
  
** نحوه استفاده **

برای استفاده از این داکیومنت، به طور کلی چند المان موجودست که کاربرد های آنها همچون "واژه نامه" نگاشته میشود

قالب کلی به این صورت است:
  

# نام عمل

- method: متود(GET-POST-DELETE-...)
  
- params: [پارامتر1,پارامتر2,پارامتر3,...]
  
```آدرس```
  
```
{
  پارامتر1:...
  پارامتر2:...
  ...
}
```
  
  
**LOGIN :** *_ (TRUE[✔] or FALSE[❌]) _*
  
**_Desc：کمی اطلاعات درمورد نحوه استفاده_**
  
Note : اختیاری، نکات احتمالی مورد نظر

Response :

```
{
  پارامتر1:...
  پارامتر2:...
  ...
}
```
</div>  


# API-Version : 1.4

# ME

- method: GET
  
- params: []
  
```https://virgool.io/api/v1.4/user/info```
  
```
{
}
```
  
  
**LOGIN :** *_TRUE[✔] _*
  
**_Desc：بعد از لاگین کردن، میتوان با ارسال ریکوئست به این آدرس اطلاعات کمی درمورد حساب کاربری خود بدست آورید_**
  
Note : تنها بعد از لاگین کردن استفاده شود

Response :

```
{
success:	true,
user:	
  id : ...
  name : "..."
  username : ""
  hash : "..."
  avatar : "https://virgool.io/images/default-avatar.jpg"
  bio	"..."
  followers_count	...
  following_count	...
  activated	[true-false]
  blocked	[true-false]
}
```


# User Existence

- method: POST
  
- params: [method,type,username]
  
```https://virgool.io/api/v1.4/auth/user-existence```
  
```
{
  "username":"ebad84.025@gmail.com",
  "type":"login",
  "method":"email"
}
```
  
  
**LOGIN :** *_False[❌] _*
  
**_Desc：برسی موجود بودن یک یوزر، و ادامه فرایند لاگین _**
  
Note : در ارسال ریکوئست، type یکی از موارد این لیست میباشد [username,email,phone] که بنا بر ورودی باید مشخص گردد.

Response :

IF TRUE:
```
{
success	true
user_exist	true
activated	true
recaptcha	false
verify_options	
phone	"09*******00"
email	"..."
password	true
}
```
IF FALSE:
```
{
success	true
msg	"کاربری با این مشخصات یافت نشد."
recaptcha	false
}
```
