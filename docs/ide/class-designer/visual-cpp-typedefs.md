---
title: Sınıf Tasarımcısında Visual C++ Typedefs
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
f1_keywords:
- vs.classdesigner.typedef
- vs.classdesigner.aliasofline
helpviewer_keywords:
- Class Designer [Visual Studio], typedefs
ms.assetid: c1984108-71fc-4d3a-b4d4-3eac2c6b4ebf
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- cplusplus
ms.openlocfilehash: 8ce99a4e4c4899502bf1f63edf2dbc1ad0c93cd0
ms.sourcegitcommit: 56018fb1f52f17bf35ae2ce71c50c763486e6173
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="visual-c-typedefs-in-class-designer"></a>Sınıf tasarımcısında Visual C++ typedefs

TypeDef deyimleri yöneltme bir ad ve temel alınan türü arasında bir veya daha fazla katmanı oluşturun. **Sınıf Tasarımcısı** anahtar sözcüğüyle bildirilen C++ typedef türlerini destekler `typedef`, örneğin:

```cpp
typedef class coord
{
   void P(x,y);
   unsigned x;
   unsigned y;
} COORD;
```

Ardından bu tür bir örneği bildirmek için de kullanabilirsiniz:

`COORD OriginPoint;`

Bir ad olmadan bir typedef bildirebilir rağmen **Sınıf Tasarımcısı** belirttiğiniz etiket adını kullanmaz; sınıf görünümü oluşturur adını kullanacaksınız. Örneğin, aşağıdaki bildirimi geçerlidir, ancak görünür **sınıf görünümü** ve **Sınıf Tasarımcısı** adlı bir nesne olarak **__unnamed**:

```cpp
typedef class coord
{
   void P(x,y);
   unsigned x;
   unsigned y;
};
```

Kullanma hakkında daha fazla bilgi için `typedef` yazın, bkz: [tür tanımları](/cpp/cpp/aliases-and-typedefs-cpp#typedefs).

Bir C++ typedef şekli typedef belirtilen türde şekli vardır. Örneğin, kaynak bildirirse `typedef class`, Şekil köşeleri ve etiket yuvarlanmış **sınıfı**. İçin `typedef struct`, Şekil kare köşeleri ve etiket sahip **yapısı**.

Sınıfları ve yapıları bunların içinde bildirilen iç içe geçmiş tür tanımları olabilir; Bu nedenle, sınıf ve yapısı şekilleri iç içe geçmiş typedef bildirimleri iç içe geçmiş şekil olarak gösterebilir.

TypeDef şekilleri Destek **Göster ilişkilendirmesi olarak** ve **Göster koleksiyon ilişkilendirmesini** bağlam menüsünde komutları.

Bazı örnekler typdef türleri verilmiştir **Sınıf Tasarımcısı** destekler:

`typedef type name`

*ad* : *türü*

typedef

Tür bağlanma ilişkisi çizgi çizer *adı*, mümkün olduğunda.

`typedef void (*func)(int)`

`func: void (*)(int)`

typedef

İşlev işaretçileri TypeDef. Hiçbir ilişki çizgi çizilir.

**Sınıf Tasarımcısı** kendi kaynak türü bir işlev işaretçisi ise bir typedef görüntülemez.

```cpp
typedef int MyInt;
class A {
   MyInt I;
};
```

`MyInt: int`

typedef

`A`

örneği

Kaynak türü şekle hedef türü şekle işaret eden bir ilişki çizgi çizer.

`Class B {};`

`typedef B MyB;`

`B`

örneği

`MyB : B`

typedef

Typedef şekli sağ tıklayarak ve tıklatarak **Göster ilişkilendirme** typedef veya sınıf görüntüler ve bir **diğer adını** (bir ilişkilendirme satırına benzer) iki şekil birleştirme satır.

`typedef B MyB;`

`typedef MyB A;`

`MyBar : Bar`

typedef

Yukarıdaki ile aynı.

```cpp
Class B {};
typedef B MyB;

class A {
   MyB B;
};
```

`B`

örneği

`MyB : B`

typedef

`A`

örneği

`MyB` bir iç içe geçmiş typedef şekli olur.

`#include <vector>`

`...`

`using namespace std;`

`...`

`typedef vector<int> MyIntVect;`

`vector<T>`sınıfı

`MyIntVect : vector<int>`

typedef

`class B {};`

`typedef B MyB;`

`class A : MyB {};`

`MyB : B`

typedef

B -&GT;

`B`

`A`

örneği

MyB ->

**Sınıf Tasarımcısı** bir bağlam menüsü komutu kullanarak bu tür bir ilişki görüntüleme desteklemiyor.

`#include <vector>`

`Typedef MyIntVect std::vector<int>;`

`Class MyVect : MyIntVect {};`

`std::vector<T>`

örneği

`MyIntVect : std::vector<int>`

typedef

`MyVect`

örneği

MyIntVect ->

### <a name="see-also"></a>Ayrıca bkz.

- [Visual C++ Kodu ile Çalışma](working-with-visual-cpp-code.md)  
- [Tür tanımları](/cpp/cpp/aliases-and-typedefs-cpp#typedefs)

