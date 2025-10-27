
# Border Treatments For Filters

- لما بحط فلتر على الصورة => بركز على البيكسل إللي في النص بس، هي إللي بيظهر فيها كل الشغل.
- طيب لو عايز أخلي أول بيكسل في الكورنر هي إللي تتأثر؟ هخليها في النص إزاي وهي مش حواليها حاجة من جانبين؟
- بعالج النقطة دي ب 3 طرق:

## How to solve?

### 1. Ignore
- ولا كأني شايفهم، همشي على البيكسلز إللي تحتهم وحواليهم وهما هينزلوا زي ما هما في الصورة الجديدة بنفس القيم القديمة

### 2. Repeat
- هاخد القيم بتاع ال border دي وأعمل بيها فريم جديد للصورة، يعني كأني زودت مربع حوالين الصورة كلها بنفس القيم بتاع ال border 
### 3. Reflect
- شبه ال repeat، بس بدال ما بزود نفس القيم بالظبط، باخد الصفوف/العواميد الزيادة عن البيكسل اللي فالنص بتاعتي وكأني حطيت مرايا على آخر عامود فيهم => هيظهرلي فيها العامود الأخير وبعده إللي قبل الأخير من برا

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


### Spark Noise

### Circular Filter
### Pyramidal Filter

### Cone Filter

### Gaussian Filter



---
### Non-Linear

### Median Filter

### Kuwhara Filter


---

## High Pass Filtering

### Derivative/Differential

