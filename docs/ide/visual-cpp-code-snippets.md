---
title: Visual C++ kod parçacıkları
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CPP
ms.workload:
- cplusplus
ms.openlocfilehash: bb091701384d36ca5aa8154701d94cda5fb34a5b
ms.sourcegitcommit: a8e01952be5a539104e2c599e9b8945322118055
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="visual-c-code-snippets"></a>Visual C++ kod parçacıkları

Visual Studio'da kod parçacıkları, yaygın olarak kullanılan kod C++ kodu dosyalarınıza eklemek için kullanabilirsiniz. Genel olarak, benzer şekilde olduğu gibi C# kod parçacıkları kullanabilirsiniz, ancak varsayılan kod parçacıkları farklı kümesidir.

Kod parçacığı belirli bir konumda kodunuzda (ekleme) ekleyebilir veya bir kod parçacığı seçili bazı koduyla çevreleyen.

## <a name="insert-a-code-snippet"></a>Kod parçacığı ekleme

Kod parçacığı eklemek için bir C++ kod dosyasını açın (*.cpp* veya *.h*) içindeki dosyanın bir yere tıklayın ve aşağıdakilerden birini yapın:

- Bağlam menüsü alma ve seçmek için sağ **parçacığı Ekle**

- İçinde **Düzenle / IntelliSense** menüsünde, select **parçacığı Ekle**

- Kısayol tuşlarını kullanın: **Ctrl**+**K**+**X**

İtibaren tercih listesi görmelisiniz **#if**. Seçtiğinizde, **#if**, dosyasına eklenen aşağıdaki kodu görmeniz gerekir:

```cpp
#if 0

#endif // 0
```

Daha sonra değiştirebilirsiniz **0** doğru koşulu.

## <a name="use-a-code-snippet-to-surround-selected-code"></a>Seçili kod surround için bir kod parçacığı kullanın

Seçili kod surround için bir kod parçacığı kullanmak için bir satırı (veya birden çok satır) seçin ve aşağıdakilerden birini yapın:

- Bağlam menüsü almak için sağ tıklatın ve seçin **Surround With**

- Gelen **Düzenle** > **IntelliSense** menüsünde, select **Surround With**

- Klavyeyi kullanarak tuşuna basın: **Ctrl**+**K**+**S**

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

**Sınıfı** parçacığı sağlar adlı bir sınıf tanımını `MyClass`, burada tanımları oluşturucusu ve yıkıcı bulunur sınıf dışında bir yıkıcı ve uygun varsayılan oluşturucu ile:

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

**Classi** kod parçacığını ayrıca adlı bir sınıf tanımını sağlar `MyClass`, ancak varsayılan oluşturucu ve yıkıcı sınıf tanımı içinde tanımlanır:

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

Yok Edicisi parçacığı eklerseniz, yıkıcı için sağladığı `SomeClass`:

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

- [Kod parçacıkları](../ide/code-snippets.md)