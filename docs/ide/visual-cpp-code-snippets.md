---
title: "Visual C++ kod parçacıkları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
author: gewarren
ms.author: gewarren
manager: ghogen
dev_langs:
- CPP
ms.workload:
- cplusplus
ms.openlocfilehash: b2a8b1c99d1b084a6f8d3c050302e16ea40d64ac
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="visual-c-code-snippets"></a>Visual C++ kod parçacıkları

Visual Studio'da kod parçacıkları, yaygın olarak kullanılan kod C++ kodu dosyalarınıza eklemek için kullanabilirsiniz. Genel olarak, benzer şekilde olduğu gibi C# kod parçacıkları kullanabilirsiniz, ancak varsayılan kod parçacıkları farklı kümesidir.

Kod parçacığı belirli bir konumda kodunuzda (ekleme) ekleyebilir veya bir kod parçacığı seçili bazı koduyla çevreleyen.

## <a name="inserting-a-code-snippet"></a>Kod parçacığı ekleme

Kod parçacığı eklemek için (.cpp veya .h) C++ kod dosyasını açın ve herhangi bir yerde içindeki dosyanın aşağıdakilerden birini yapın:

- Bağlam menüsü alma ve seçmek için sağ **parçacığı Ekle**

- İçinde **Düzenle / IntelliSense** menüsünde, select **parçacığı Ekle**

- Kısayol tuşlarını kullanın: **Ctrl**+**K**+**X**

İtibaren tercih listesi görmelisiniz **#if**. Seçtiğinizde, **#if**, dosyasına eklenen aşağıdaki kodu görmeniz gerekir:

```cpp
#if 0

#endif // 0
```

0 ile doğru koşul daha sonra değiştirebilirsiniz.

## <a name="using-a-code-snippet-to-surround-selected-code"></a>Seçili kod surround için bir kod parçacığı kullanma

Seçili kod surround için bir kod parçacığı kullanmak için bir satırı (veya birden çok satır) seçin ve aşağıdakilerden birini yapın:

- Bağlam menüsü almak için sağ tıklatın ve seçin **Surround With**

- Gelen **Düzenle** > **IntelliSense** menüsünde, select **Surround With**

- Klavyeyi kullanarak tuşuna basın: **CTRL**+**K**+**S**

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

**Classi** kod parçacığını ayrıca MyClass adlı bir sınıf tanımını sağlar, ancak varsayılan oluşturucu ve yıkıcı sınıf tanımı içinde tanımlanmıştır:

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

## <a name="for-vs-forr-vs-rfor"></a>için forr vs rfor karşılaştırması

Vardır üç farklı **için** farklı sağlamak parçacıkları, `for` döngüler.

**Rfor** parçacığı sağlayan bir [aralık tabanlı](/cpp/cpp/range-based-for-statement-cpp) for döngüsü (bağlantı). Dizin tabanlı üzerinden bu yapıyı tercih edilir `for` döngüler.

```cpp
for (auto& i : v)
{

}
```

**İçin** parçacığı sağlayan bir `for` döngü koşulunu uzunluğa dayanır (içinde `size_t`) bir nesnenin.

```cpp
for (size_t i = 0; i < length; i++)
{

}
```

**Forr** parçacığı sağlayan bir ters `for` döngü koşulunu uzunluğunu nesnenin üzerinde (tamsayı) dayanır.

```cpp
for (int i = length - 1; i >= 0; i--)
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

## <a name="see-also"></a>Ayrıca bkz.

[Kod parçacıkları](../ide/code-snippets.md)
