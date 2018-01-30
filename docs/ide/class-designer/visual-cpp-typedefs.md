---
title: "Sınıf tasarımcısında Visual C++ Typedefs | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.classdesigner.typedef
- vs.classdesigner.aliasofline
helpviewer_keywords:
- Class Designer [Visual Studio], typedefs
ms.assetid: c1984108-71fc-4d3a-b4d4-3eac2c6b4ebf
caps.latest.revision: 
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 96d7e8cee6ce024040184aca50b5f5cb6facf388
ms.sourcegitcommit: b18844078a30d59014b48a9c247848dea188b0ee
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/29/2018
---
# <a name="visual-c-typedefs-in-class-designer"></a>Sınıf Tasarımcısında Visual C++ Typedefs
TypeDef deyimleri yöneltme bir ad ve temel alınan türü arasında bir veya daha fazla katmanı oluşturun. Sınıf Tasarımcısı anahtar sözcüğüyle bildirilen C++ typedef türlerini destekler `typedef`, örneğin:  
  
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
  
Adı olmayan bir typedef bildirebilirsiniz, ancak Sınıf Tasarımcısı belirttiğiniz etiket adını kullanmaz; Sınıf Görünümü oluşturur adını kullanır. Örneğin, aşağıdaki bildirimi geçerlidir, ancak adlı bir nesne sınıf görünümü ve Sınıf Tasarımcısı göründüğü **__unnamed**:  
  
```cpp
typedef class coord  
{  
   void P(x,y);  
   unsigned x;  
   unsigned y;  
};  
```

Kullanma hakkında daha fazla bilgi için `typedef` yazın, bkz: [tür tanımları](/cpp/aliases-and-typedefs-cpp#typedefs).

Bir C++ typedef şekli typedef belirtilen türde şekli vardır. Örneğin, kaynak bildirirse `typedef class`, Şekil köşeleri ve etiket yuvarlanmış **sınıfı**. İçin `typedef struct`, Şekil kare köşeleri ve etiket sahip **yapısı**.  
  
Sınıfları ve yapıları bunların içinde bildirilen iç içe geçmiş tür tanımları olabilir; Bu nedenle, sınıf ve yapısı şekilleri iç içe geçmiş typedef bildirimleri iç içe geçmiş şekil olarak gösterebilir.  
  
TypeDef şekilleri Destek **Göster ilişkilendirmesi olarak** ve **Göster koleksiyon ilişkilendirmesini** bağlam menüsünde komutları.  
  
Sınıf Tasarımcısı desteklediği typdef türleriyle bazı örnekleri şunlardır:  
  
`typedef type name`  
  
*ad* : *türü*  
  
typedef  
  
Tür bağlanma ilişkisi çizgi çizer *adı*, mümkün olduğunda.  
  
`typedef void (*func)(int)`  
  
`func: void (*)(int)`  
  
typedef  
  
İşlev işaretçileri TypeDef. Hiçbir ilişki çizgi çizilir.  
  
Bir işlev işaretçisi kendi kaynak türü ise, Sınıf Tasarımcısı bir typedef görüntülemez.  
  
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
  
`MyB`bir iç içe geçmiş typedef şekli olur.  
  
`#include <vector>`  
  
`...`  
  
`using namespace std;`  
  
`...`  
  
`typedef vector<int> MyIntVect;`  
  
`vector<T>`Sınıfı  
  
`MyIntVect : vector<int>`  
  
typedef  
  
`class B {};`  
  
`typedef B MyB;`  
  
`class A : MyB {};`  
  
`MyB : B`  
  
typedef  
  
-> B  
  
`B`  
  
`A`  
  
örneği  
  
-> MyB  
  
Sınıf Tasarımcısı bir bağlam menüsü komutu kullanarak bu tür bir ilişki görüntüleme desteklemez.  
  
`#include <vector>`  
  
`Typedef MyIntVect std::vector<int>;`  
  
`Class MyVect : MyIntVect {};`  
  
`std::vector<T>`  
  
örneği  
  
`MyIntVect : std::vector<int>`  
  
typedef  
  
`MyVect`  
  
örneği  
  
-> MyIntVect  
  
## <a name="see-also"></a>Ayrıca bkz.

[Visual C++ Kodu ile Çalışma](working-with-visual-cpp-code.md)  
[Tür tanımları](/cpp/aliases-and-typedefs-cpp#typedefs)