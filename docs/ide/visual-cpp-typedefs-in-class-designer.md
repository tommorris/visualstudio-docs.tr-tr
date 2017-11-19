---
title: "Sınıf tasarımcısında Visual C++ Typedefs | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.classdesigner.typedef
- vs.classdesigner.aliasofline
helpviewer_keywords: Class Designer [Visual Studio], typedefs
ms.assetid: c1984108-71fc-4d3a-b4d4-3eac2c6b4ebf
caps.latest.revision: "12"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: d6df83d459165b4814fcac129bc36b64d821efb6
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="visual-c-typedefs-in-class-designer"></a>Sınıf Tasarımcısında Visual C++ Typedefs
TypeDef deyimleri yöneltme bir ad ve temel alınan türü arasında bir veya daha fazla katmanı oluşturun. Sınıf Tasarımcısı anahtar sözcüğüyle bildirilen C++ typedef türlerini destekler `typedef`, örneğin:  
  
```  
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
  
```  
typedef class coord  
{  
   void P(x,y);  
   unsigned x;  
   unsigned y;  
};  
```  
  
 Kullanma hakkında daha fazla bilgi için `typedef` yazın, bkz: [typedef belirleyici](https://msdn.microsoft.com/en-us/library/05w82thz.aspx).  
  
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
  
```  
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
  
```  
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
  
 B ->  
  
 `B`  
  
 `A`  
  
 örneği  
  
 MyB ->  
  
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
  
 MyIntVect ->  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual C++ kodu (Sınıf Tasarımcısı) ile çalışma](../ide/working-with-visual-cpp-code-class-designer.md)   
 [TypeDef belirticisi](https://msdn.microsoft.com/en-us/library/05w82thz.aspx)