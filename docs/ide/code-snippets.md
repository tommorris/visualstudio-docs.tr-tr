---
title: Kod parçacıkları
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
f1_keywords:
- vs.ExpansionManagerImport
- vs.codesnippetmanager
helpviewer_keywords:
- surround with
- code snippets
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CSharp
- VB
- CPP
ms.workload:
- multiple
ms.openlocfilehash: a054ba07596135b08260ded028f07701fce9196d
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31924478"
---
# <a name="code-snippets"></a>Kod parçacıkları

Kod parçacıkları, bağlam menü komutu veya kısayollarıyla birleşimini kullanarak bir kod dosyasında eklenebilir yeniden kullanılabilir kod küçük taşlarıdır. Bunlar genellikle yaygın olarak kullanılan kod blokları gibi içeren `try-finally` veya `if-else` tüm sınıfları veya yöntemleri eklemek için engeller, ancak kullanılabilir.

Kod parçacıkları diller, C#, C++, Visual Basic, XML ve T-SQL, birkaçıdır dahil olmak üzere çok sayıda için kullanılabilir. Tüm kullanılabilir yüklü parçacıkları bir dil için görüntülemek için açın **kod parçacıkları Yöneticisi** gelen **Araçları** Visual Studio menüsünde ve üstünde açılan menüsünden dili seçin.

![Kod parçacıkları Yöneticisi iletişim kutusu](media/code-snippets-manager.png)

Kod parçacıkları aşağıdaki genel yollarla erişilebilir:

- Menü çubuğunda seçin **Düzenle** > **IntelliSense** > **parçacığı Ekle...**

- Kod düzenleyicisinde sağ tıklatın veya bağlam menüsünden seçin **parçacığı** > **parçacığı Ekle...**

- Klavyeden basın **Ctrl**+**K**+**X**

## <a name="expansion-snippets-and-surround-with-snippets"></a>Genişletme parçacıkları ve surround-with kod parçacıkları

Visual Studio'da kod parçacığını iki tür vardır: Belirtilen ekleme noktasına eklenir ve bir kod parçacığında kısayol değiştirebilir, genişletme parçacıkları ve seçili kod bloğunu eklenen surround-with kod parçacıkları (C# ve C++ yalnızca).

Bir genişletme parçacığı örneği: C# ' ta kısayol tryf try-finally bloğu eklemek için kullanılır:

```csharp
try
{

}
finally
{

}
```

Tıklatarak bu parçacığı ekleyebilirsiniz **Ekle parçacığı** kod penceresinin bağlam menüsünden **Visual C#**, yazın `tryf`ve tuşuna basın **sekmesini**. Ya da yazabilirsiniz `tryf` ve basın **sekmesini** iki kez.

Surround-with kod parçacığında örneği: c++ kısayol `if` ekleme parçacığını veya Çevrele kod parçası olarak kullanılabilir. Bir kod satırı seçerseniz (örneğin `return FALSE;`) ve ardından **Surround With** > **varsa**, kod parçacığında satırında genişletilir:

```cpp
if (true)
{
    return FALSE;
}
```

## <a name="snippet-replacement-parameters"></a>Kod parçacığında değiştirme parametreleri

Kod parçacıkları yazmakta olduğunuz kesin kod uyacak şekilde değiştirmeniz gerekir yer tutucuları olan değiştirme parametreleri içerebilir. Önceki örnekte `true` uygun koşulu ile değiştirirsiniz değiştirme parametresi. Yaptığınız değişikliği parçacığında bulunan aynı değiştirme parametresi, her örneği için tekrarlanır.

Örneğin, Visual Basic'te bir özellik ekler bir kod parçacığı yoktur. Kod parçacığını eklemek için seçin **parçacığı...**   >  **Ekle parçacığı** bir Visual Basic kod dosyasını sağ tıklatın veya bağlam menüsünden. Ardından, **kod düzenleri** > **özellikleri, yordamlar, olayları** > **bir özellik tanımlamak**.

![Kod parçacığı menü tanımla bir özellik için](media/code-snippets-vb-property.png)

Aşağıdaki kod eklenir:

```vb
Private newPropertyValue As String
Public Property NewProperty() As String
    Get
        Return newPropertyValue
    End Get
    Set(ByVal value As String)
        newPropertyValue = value
    End Set
End Property
```

Değiştirirseniz `newPropertyValue` için `m_property`, ardından her örneğinin `newPropertyValue` değiştirilir. Değiştirirseniz `String` için `Int` özelliği bildiriminde sonra ayarlama yöntemi değeri de değiştirilir `Int`.

## <a name="see-also"></a>Ayrıca bkz.

- [İzlenecek yol: kod parçacığı oluşturma](../ide/walkthrough-creating-a-code-snippet.md)
- [Nasıl yapılır: kod parçacıklarını dağıtma](../ide/how-to-distribute-code-snippets.md)
- [Kod parçacıkları için en iyi uygulamalar](../ide/best-practices-for-using-code-snippets.md)
- [Kod parçacıkları sorunlarını giderme](../ide/troubleshooting-snippets.md)
- [C# kod parçacıkları](../ide/visual-csharp-code-snippets.md)
- [Visual C++ kod parçacıkları](../ide/visual-cpp-code-snippets.md)
- [Kod parçacıkları şema başvurusu](../ide/code-snippets-schema-reference.md)