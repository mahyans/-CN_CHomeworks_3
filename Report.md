# الگوریتم های مسیریابی

در این تمرین الگوریتم های مسیریابی در شبکه مانند distance vector
و link state را پیاده سازی میکنیم .
علاوه بر آن یک توپولوژی عمومی از تعدادی router نیاز داریم .
در اینجا ۳ فایل داریم که یکی از آن ها به پباده سازی network اصلی اختصاص دارد.
فایل CommandHandler تمام ورودی ها و دستورات را مدیریت میکند و 
و فایل main برنامه را اجرا میکند .

## تعیین توپولوژی شبکه 

در این بخش با دریافت دو نود و هزینه ساخت آن یک توپولوژی شبکه میسازیم که تابع اصلی آن به صورت زیر است :

[![image](https://www.linkpicture.com/q/topolgy.png)](https://www.linkpicture.com/view.php?img=LPic647e077b99af91031985149)



## نمایش توپولوژی شبکه 

در این بخش باید توپولوژی شبکه را به وسیله یک adjacency matrix نمایش میدهیم . 
کد این بخش به صورت زیر است :

[![image](https://www.linkpicture.com/q/showTopology.png)](https://www.linkpicture.com/view.php?img=LPic647e077b99af91031985149)



## تغییر هزینه مسیریابی

در این بخش نود های مبدا و مقصد همراه با هزینه تغییر یافته به عنوان وروردی داده میشود و با توجه به آن اطلاعات را به روز رسانی میکنیم . 
تابع آن به صورت زیر است :


[![image](https://www.linkpicture.com/q/modify.png)](https://www.linkpicture.com/view.php?img=LPic647e077b99af91031985149)


## حذف ارتباط بین دو گره 

در این بخش با گرفتن نود ورودی و خروجی ارتباط بین آن ها را حذف میکنیم که این کار را با تغییر هزینه هر یال به     -۱ 
انجام میدهیم . تابع آن به شکل زیر است :


[![image](https://www.linkpicture.com/q/remove_2.png)](https://www.linkpicture.com/view.php?img=LPic647e077b99af91031985149)


## پیاده سازی الگوریتم Link State (LSRP)

این دستور شماره نود مبدا را گرفته و جدول مسیریابی آن به همراه تمام iteration ها را چاپ میکند .
این تابع ابتدا نودی که کمترین فاصله را از نود مبدا دارد پیدا کرده و فاصله را به روز میکند .
این عملیات از الگوریتم dijakstra استفاده میکند و درباره کل شبکه اطلاع دارد :


[![image](https://www.linkpicture.com/q/lsrp1.png)](https://www.linkpicture.com/view.php?img=LPic647e07f6054c01136119129)



در تابع زیر این کار را برای تمام نودهای شبکه انجام داده و مدت زمان آن را هم برمیگرداند :

[![image](https://www.linkpicture.com/q/lsrp2.png)](https://www.linkpicture.com/view.php?img=LPic647e07f6054c01136119129)


## پیاده سازی الگوریتم Distance Vector (DVRP)

این دستور شماره نود مبدا را گرفته و جدول مسیریابی را چاپ میکند . ابن روش از الگوریتم Bellman-Ford استفاده میکند 
و درباره تمام گره های شبکه اطلاع ندارد و فقط از گره های همسایه اطلاعات میگیرد .
در اینجا یک تابع داریم که یک نود به عنوان ورودی میگیرد و الگوریتم را اجرا میکند و تابع دوم runDVRP را
برای تمام نودهای شبکه اجرا میکند و مدت زمانی که طول میکشد تا کل فرایند تمام شود را محاسبه میکند :


[![image](https://www.linkpicture.com/q/DVRP-1.png)](https://www.linkpicture.com/view.php?img=LPic647e07f6054c01136119129)


[![image](https://www.linkpicture.com/q/DVRP2.png)](https://www.linkpicture.com/view.php?img=LPic647e07f6054c01136119129)


## نتایج 

نتایج حاصل از اجرای دستور show
و modify
و remove :


[![image](https://www.linkpicture.com/q/DVRP2.png)](https://www.linkpicture.com/view.php?img=LPic647e07f6054c01136119129)

[![image](https://www.linkpicture.com/q/DVRP2.png)](https://www.linkpicture.com/view.php?img=LPic647e07f6054c01136119129)

[![image](https://www.linkpicture.com/q/DVRP2.png)](https://www.linkpicture.com/view.php?img=LPic647e07f6054c01136119129)


نتایج حاصل از اجرای دستور lsrp :

[![image](https://www.linkpicture.com/q/lspr1.png)](https://www.linkpicture.com/view.php?img=LPic647e0a3215dad1532466876)

[![image](https://www.linkpicture.com/q/Screenshot-25_2.png)](https://www.linkpicture.com/view.php?img=LPic647e0a3215dad1532466876)


نتایج حاصل از اجرای دستور DVRP :

[![image](https://www.linkpicture.com/q/Screenshot-25_2.png)](https://www.linkpicture.com/view.php?img=LPic647e0a3215dad1532466876)


## مقایسه نتایج

[![image](https://www.linkpicture.com/q/Screen-Shot-2023-06-05-at-9.39.57-PM_1.png)](https://www.linkpicture.com/view.php?img=LPic647e259dc29cb1863726673)


هنگامی که عملیات مسیریابی را دفعه اول اجرا میکنیم میبینیم که lsrp 
از dvrp سریع تر است . 
عملیات lsrp زمانی 
برابر با 79 میکروثانیه طول میکشد در حالی 
که dvrp
حدود ۳۹۰ میکروثانیه طول میکشد .

پس از اینکه لینک بین دو گره ۴ و ۱۰ را حذف کردیم میبینیم که عملیات lsrp همچنان سریع تر است 
این دفعه این عملیات ۷۱ میکروثانیه طول میکشد یعنی زمان آن کمتر شده است .
عملیات dvrp
زمان ۴۰۳ میکروثانیه را میبرد که از دفعه قبل بیشتر شده است .

به طور کلی lsrp 
 پهنای باند و ترافیک بیشتری مصرف میکند و از الگوریتم dijakstra استفاده میکند 
 ولی درباره بقیه شبکه اطلاعات دارد و مهم تر از آن این است که سرعت آن زیاد است .
عملیات dvrp فقط درباره گره های همسایه اطلاعات دارد
 و سرعت آن کمتر است 
 و از الگوریتم bellman-ford استفاده میکند 
ولی پهنای باند مورد نیاز آن به دلیل local sharing
کمتر است .




