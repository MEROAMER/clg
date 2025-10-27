
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
---

## Low Pass Filtering
---
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
- باخد 9 بيكسلز في المرة => بجمع كل قيم التسعة / حجم الفلتر اكا 9 
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
 ---
 
### Cone Filter

---
### Gaussian Filter


---
---
### Non-Linear

### Median Filter

### Kuwhara Filter


---
---
---
## High Pass Filtering

### Derivative/Differential

