---
title: "Visual C++ kod parçacıkları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 74e26fd4-e5ca-4611-a816-0a521b4947a0
caps.latest.revision: "2"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 0d9a34e371797317d3163f8288474e7a902b4f82
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="visual-c-code-snippets"></a>Visual C++ kod parçacıkları
Visual Studio'da kod parçacıkları, yaygın olarak kullanılan kod C++ kodu dosyalarınıza eklemek için kullanabilirsiniz. Genel olarak, benzer şekilde olduğu gibi C# kod parçacıkları kullanabilirsiniz, ancak varsayılan kod parçacıkları farklı kümesidir.  
  
 Kod parçacığı belirli bir konumda kodunuzda (ekleme) ekleyebilir veya bir kod parçacığı seçili bazı koduyla çevreleyen.  
  
## <a name="inserting-a-code-snippet"></a>Kod parçacığı ekleme  
 Kod parçacığı eklemek için (.cpp veya .h) C++ kod dosyasını açın ve herhangi bir yerde içindeki dosyanın aşağıdakilerden birini yapın:  
  
-   Bağlam menüsü alma ve seçmek için sağ **parçacığı Ekle**  
  
-   İçinde **Düzenle / IntelliSense** menüsünde, select **parçacığı Ekle**  
  
-   Kısayol tuşlarını kullanın: **CTRL + K + X**  
  
 İtibaren tercih listesi görmelisiniz **#if**. Seçtiğinizde, **#if**, dosyasına eklenen aşağıdaki kodu görmeniz gerekir:  
  
```cpp  
#if 0  
  
#endif // 0  
```  
  
 0 ile doğru koşul daha sonra değiştirebilirsiniz.  
  
## <a name="using-a-code-snippet-to-surround-selected-code"></a>Seçili kod Surround için bir kod parçacığı kullanma  
 Seçili kod surround için bir kod parçacığı kullanmak için bir satırı (veya birden çok satır) seçin ve aşağıdakilerden birini yapın:  
  
1.  Bağlam menüsü alma ve seçmek için sağ **Surround With**  
  
2.  İçinde **Düzenle / IntelliSense** menüsünde, select **Surround With**  
  
3.  Kısayol tuşlarını kullanın: **CTRL + K + S**  
  
 Seçin **#if**. Şöyle bir şey görmeniz gerekir:  
  
```cpp  
#if 0  
#include "pch.h"  // or whatever line you had selected  
#endif // 0  
```  
  
 0 ile doğru koşul daha sonra değiştirebilirsiniz.  
  
## <a name="where-can-i-find-a-complete-list-of-the-c-code-snippets"></a>C++ kod parçacıkları tam bir listesini nereden bulabilirim?  
 Giderek C++ kod parçacıkları tam listesini bulabilirsiniz **kod parçacıkları Yöneticisi** (üzerinde **Araçları** menüsü) ve ayarı **dil** için **Visual C++** . Penceresinde **Visual C++**. Alfabetik sırada tüm C++ kod parçacıkları adını görmeniz gerekir.  
  
 Çoğu kod parçacıkları adlarını açıklar niteliktedir, ancak bazı adları kafa karıştırıcı olabilir.  
  
## <a name="class-vs-classi"></a>Sınıf classi karşılaştırması  
 **Sınıfı** parçacığı MyClass, burada tanımları oluşturucusu ve yıkıcı bulunur sınıf dışında bir yıkıcı ve uygun varsayılan oluşturucu ile adlı bir sınıf tanımını sağlar:  
  
```cpp  
class MyClass  
{  
public:  
MyClass();  
~MyClass();  
  
private:  
  
};  
  
MyClass::MyClass()  
{  
}  
  
MyClass::~MyClass()  
{  
}  
```  
  
 Classi kod parçacığını ayrıca MyClass adlı bir sınıf tanımını sağlar, ancak varsayılan oluşturucu ve yıkıcı sınıf tanımı içinde tanımlanmıştır:  
  
```cpp  
class MyClass  
{  
public:  
MyClass()  
{  
}  
  
~MyClass()  
{  
}  
  
private:  
  
};  
```  
  
## <a name="for-vs-foreach-vs-forr-vs-rfor"></a>İçin foreach forr vs rfor karşılaştırması karşılaştırması  
 Vardır dört farklı sağlayan parçacıkları farklı, döngüler için.  
  
 **İçin** parçacığı sağlayan bir `for` döngü koşulunu uzunluğa dayanır (içinde `size_t`) bir nesnenin:  
  
```cpp  
for (size_t i = 0; i < length; i++)  
{  
  
}  
```  
  
 **Foreach** parçacığı sağlayan bir `for each` bir koleksiyonun üyelerini döngü:  
  
```cpp  
for each (object var in collection_to_loop)  
{  
  
}  
```  
  
 **Forr** parçacığı sağlayan bir ters `for` döngü koşulunu uzunluğunu nesnenin üzerinde (tamsayı) dayanır:  
  
```cpp  
for (int i = length - 1; i >= 0; i--)  
{  
  
}  
```  
  
 **Rfor** parçacığı sağlayan bir [aralık tabanlı](/cpp/cpp/range-based-for-statement-cpp) for döngüsü (bağlantı):  
  
```cpp  
for (auto& i : v)  
{  
  
}  
```  
  
## <a name="the-destructor-snippet-"></a>Yok Edicisi kod parçacığını (~)  
 Yok Edicisi kod parçacığını (**~**) farklı bağlamlarda farklı bir davranış gösterir. Bu kod parçacığında bir sınıf içinde eklerseniz, o sınıf için bir yıkıcı sağlar. Örneğin, aşağıdaki kodu verilir:  
  
```cpp  
class SomeClass {  
  
};  
```  
  
 Yok Edicisi parçacığı eklerseniz, bir yıkıcı için SomeClass sağlar:  
  
```cpp  
class SomeClass {  
    ~SomeClass()  
    {  
  
    }  
};  
```  
  
 Sınıf dışındaki yıkıcı parçacığı eklemeye çalışırsanız, bir yıkıcı bir yer tutucu adla sağlar:  
  
```cpp  
~TypeNamePlaceholder()  
{  
  
```