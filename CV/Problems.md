
# Basic Problems

## Neighboring
objects are group of color/gray connected neighbor pixels.
![](media/Pasted%20image%2020251021040412.png)
### Connectivity:
1. neighbors -> N4,N8,Nd
2. their values are in the connectivity set.
- NOTE: the values itself should be in the set, it's not a range.

### How to solve?
- بكوّن من كل مجموعة بيكسلز label معين في الصورة، ممكن تكون بيكسل جنبي، فوقي -> مبنزلش للصف إللي بعدي غير لما أخلص الصفّ إللي معايا.
- بمشي من الشمال لليمين من فوق لتحت، بعمل label للصف إللي أنا فيه مع إللي فوقيه
- لو الصف إللي فوقي مش فيه label أنضم ليه -> بعمل واحد جديد
- لو 2 labels اتقابلوا -> merge بقوا label واحد خلاص.
1. extract connectivity set + neighboring type.
2. we read the matrix as if it's placed in the 4th quarter, so 4 would be: f(1,0)
3. ![](media/Pasted%20image%2020251021041357.png)
---
## Image Path
sequence of connected pixels between 2 pixels, sometimes it doesn't exist, sometimes we got multiple paths, sometimes one unique path.
applies same connectivity rules.
![](media/Pasted%20image%2020251021041819.png)

### How to solve?
- نفس قوانين ال Neighbor وطريقته بالظبط.
- لو فيه بيكسل ملقيتلهاش Neighbor -> برجع للي قبلها وأجرب طريق مختلف.
- بكتب البيكسل إللي ببدأ بيها أول حاجة في ال label وبعدها أكتب الطريق إللي همشي فيه.
- Image path length = hops - 1
---

## Labeling of connected regions
region: group of connected pixels
labeling: finding all regions in matrix.

### How to solve?
- بيديني {0 -> 20} connectivity set{10,30,..} ORRRR connectivity region
- بستخدم نفسسس ال Neighbor + Image path 
- بحدد نوع ال neigh + بشتغل الصف وما فوقه لحد ما أخلص 
- لو 2 labels مختلفين اتقابلوا -> merge.
![](media/Pasted%20image%2020251021043250.png)
---
## Histogram
count the number of occurrences per gray/color component value in image matrix.

- حرفيًا باخد الماتريكس -> بشوف جواها أرقام إيه، مثلاً 0 و 3 و 5
- ببدأ أشوف ال 0 اتكرر كام مرة؟ بعمل جدول فيه القيمة : عدد مرات التكرار.
- سواءً كانت ال values في ماتريكس أو رسمة أو جدول.

---


# Image Enhancement
T(f(x, y)) = f′(x, y)
- برسم معادلة خطيّة اكا علاقة بين f(x, y) قبل التغيير و f′(x, y) بعد ال enhance => مش علاقة بين x, y نوبببب
- آخر الخط بيكون دايمًا L - 1 = 255 إلا لو حددلي في المسألة range أقف عنده.
---
## Image Negative
f′(x, y)neg = (L − 1) − f(x, y)original

### How to solve?
- حرفيًا بقلب الأبيض أسود والعكس، هعمل دا إزاي؟ هجيب ال negative بتاعهم => يعني القيمة إللي كانوا هياخدوها لو مشوا بالعكس => بطرحهم من 255.
- لو عاطيني RANGE معين بقا؟ L=2^q 
- (q=No. of bits. if q=8, then L=28 =256)*

---
## Contrast Stretching & Contraction
- Dynamic Range: the range in which image details exist.
- we wanna INCREASE that range -> increasing contrast -> increase difference between elements -> expand intensity range.
- making the white whiter & dark darker.
- works best for: low contrast, narrow range of intensities.

### How to solve?
![](media/Pasted%20image%2020251021050217.png)

- دلوقتي عندي علاقة خطية بين الدالة قبل تحسينها والدالة بعد تحسينها، كل واحدة بال x, y بتوعها -> f = dynamic range.
- عايزين نجيب العلاقة بينهم في مدى الألوان بتاعي 255.
- طيب دلوقتي التغيّر في العلاقة دي مش ثابت/كتير -> هعتبر كل واحدة منهم علاقة لوحدها وأجيب معادلتها منفصلة وحدودها منفصلين.
- عندي رقمين مهمين، ال dynamic range دا ليه نقطة بداية ونهاية، بسمّيهم r1, r2 ->r1= أصغر قيمة في الgray levels || r2 = أكبر قيمة في ال gray levels.
- عايزة أفرد الخط دا لحد ما يوصل بدل r1, r2 => S1, S2.
- هقسم العلاقة بتاعتي حسب النقط المهمة دي:


1. الخط الأول: 0 -> r1
	- معادلة الخط دا = قيمة ال X * الميل m
	- f′(x, y) = f(x, y) * m
	- لأن ال X عندي هنا هي ال f = dynamic range.


2. الخط التاني: r1 -> r2
	- عندي هنا جزء مقطوع من محور ال y (إللي عملتله معادلته في الأول) مش عايزينه يدخل في الحسابات معانا، ف هنلغيه في المعادلة بإننا نطرح آخر قيمة فيه * الميل الحالي بتاعي، وهزود آخر قيمة في ال y بتاعته S1.
	- الميل = فرق الصادات / فرق السينات.
	- ![](media/Pasted%20image%2020251021051344.png)


3. الأخير: r2 -> (L-1) aka 255:
	- نفس التانية بالظبط، بس آخر قيمة في الصادات عندي = L-1 = 255.
	- ![](media/Pasted%20image%2020251021051732.png)

---
