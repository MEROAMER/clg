
# Basic Problems
---
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
