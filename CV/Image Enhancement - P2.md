
# Border Treatments For Filters

- لما بحط فلتر على الصورة => بركز على البيكسل إللي في النص بس، هي إللي بيظهر فيها كل الشغل.
- طيب لو عايز أخلي أول بيكسل في الكورنر هي إللي تتأثر؟ هخليها في النص إزاي وهي مش حواليها حاجة من جانبين؟
- بعالج النقطة دي ب 3 طرق:

## How to solve?

### 1. Ignore
- ولا كأني شايفهم، همشي على البيكسلز إللي تحتهم وحواليهم وهما هينزلوا زي ما هما في الصورة الجديدة بنفس القيم القديمة.

### 2. Repeat
- هاخد القيم بتاع ال border دي وأعمل بيها فريم جديد للصورة، يعني كأني زودت مربع حوالين الصورة كلها بنفس القيم بتاع ال border 
- ![](media/Pasted%20image%2020251027172106.png)


### 3. Reflect
- شبه ال repeat، بس بدال ما بزود نفس القيم بالظبط، باخد الصفوف/العواميد الزيادة عن البيكسل اللي فالنص بتاعتي وكأني حطيت مرايا على آخر عامود فيهم => هيظهرلي فيها العامود الأخير وبعده إللي قبل الأخير من برا
- ![](media/Pasted%20image%2020251027173023.png)


--- 

# Filtering in Spatial Domain


## Low Pass Filtering

### Linear
- square odd grid
- we only filter on the center of the matrix(1 pixel)
- linear filters has weights
- generally => it's AVG/weighted AVG.
---
### Spark Noise
- نقط بيضا في الصورة
- بحلّها إني أعمل فلتر mean للصورة كلها بيكسل بيكسل
#### How to solve?
- بجيب الفلتر بتاعي => مثال: حجمه 3 × 3
- باخد 9 بيكسلز في المرة => بجمع كل قيم بيكسلز الصورة / مجموع ال weights في الفلتر  
- أحط القيمة في البيكسل إللي في النص بس
- أحرك الفلتر بيكسل كمان علشان البيكسل اللي بعد البيكسل اللي لسه مغيراه يكون هو في النص وأطبق الفلتر عليه
- وهكذا لحد ما أخلصهم كلهم.
### Problem caused: 
- الفلتر دا سببلي مشكلة تانية: ال edges بقت blurred => مش واضحة خالص
- مفترض ال edge بتكون قيمته عالية جدًا علشان يكون واضح
- ![](media/Pasted%20image%2020251027174220.png)

---
### Circular Filter

- circle of ones around
- بستخدمه بنفس طريقة فلتر ال spark.
![](media/Pasted%20image%2020251027174404.png)

---
### Pyramidal Filter
- pyramid all over
- الدكتور قالت هتدينا الأرقام مش هنحفظها.
![](media/Pasted%20image%2020251027174739.png)
 ---
### Cone Filter
- cone of numbers
![](media/Pasted%20image%2020251027174922.png)

---
### Gaussian Filter
![](media/Pasted%20image%2020251027175038.png)

- AVG(spark noise) Vs. Gaussian
- ![](media/Pasted%20image%2020251027175135.png)
---
---


### Non-Linear
- DOESN'T HAVE WEIGHTS
- square odd grid
---
### Median Filter
- perform smoothing without blurring edges 
- حل مشكلة ال spark noise 
- ![](media/Pasted%20image%2020251027175539.png)

#### How to solve?
- Sort the gray values under the filter(Ascending)
- Consider min value (Median of gray values) the new center pixel value.
- ![](media/Pasted%20image%2020251027175505.png)

---
### Kuwhara Filter
- ![](media/Pasted%20image%2020251027175655.png)

#### How to solve?
- بقسم الفلتر ل 4 مربعات
- بجيب ال mean, variance لكل مربع
- بشوف المربع اللي عنده أقل variance (أقل noise) => البيكسل إللي في النص = ال mean بتاعه
---
---
---
## High Pass Filtering

### Derivative/Differential

- اسمها derivative لأنها بتطلعلي قيمة لما يكون فيه تغيير في القيم بسسسس
- ممكن نستخدمها علشان تحسّن ال edges/corners علشان تساعدنا في ال labeling/segmentation/feature extraction/CNN
- ممكن تكون موجبة أو سالبة
- ممكن أجيبها من low/high pass filters
	- لو معايا low => هطرح من 255 لو عايز high والعكس.
	- ![](media/Pasted%20image%2020251027181746.png)
---
### Laplacian Operator
#### 1. (8-Neighbor) Derivative
- مجموع weights الفلتر = 0
- لو البيكسلز إللي هيمشي عليها كلها نفس الرقم(مفيهاش تغيير) => هيصفرها
- لو فيها تغيير => هيطلع قيم بناءً على مقدار التغيير دا

![](media/Pasted%20image%2020251027180948.png)

#### 2. (4-Neighbor) Derivative
- بيتعرف على الخطوط الرأسية/الأفقية في الصورة
- - بيتعرف على الخطوط العمودية عن طريق إنه يفصل البيكسل إللي في النص عن + حواليها
![](media/Pasted%20image%2020251027181220.png)


### Laplacian Corner
#### 3. Corner Detector
- بيتعرف على ال corners بتاع الصورة => يديها weight أكبر ويصفر الباقي
![](media/Pasted%20image%2020251027181506.png)

### Other Operators
#### 4. Robert Operators
- بيتعرف على الخطوط المحورية
![](media/Pasted%20image%2020251027181543.png)

#### Corners + Perpendicular + Diagonal
#### 5. Prewitt Differential Filter
![](media/Pasted%20image%2020251027181717.png)

#### 6. Sobel Operators
![](media/Pasted%20image%2020251027181724.png)
