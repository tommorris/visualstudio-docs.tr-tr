---
title: "Kod parçacıkları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.ExpansionManagerImport
- vs.codesnippetmanager
helpviewer_keywords:
- code snippets, replacement parameters
- code snippets, surround with
- replacement parameters
- code snippets, expansion
- surround with
- code snippets
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: e2b973b00e132973b8569bc5cad8c1f1318317cd
ms.sourcegitcommit: 49aa031cbebdd9c7ec070c713afb1a97d1ecb701
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2018
---
# <a name="code-snippets"></a>Kod parçacıkları

Kod parçacıkları, bağlam menü komutu veya kısayollarıyla birleşimini kullanarak bir kod dosyasında eklenebilir yeniden kullanılabilir kod küçük taşlarıdır. Try-finally gibi sık kullanılan kod blokları veya if-else blokları genellikle içerir, ancak tüm sınıfları veya yöntemleri eklemek için kullanılabilir.

## <a name="expansion-snippets-and-surround-with-snippets"></a>Genişletme parçacıkları ve Surround-With kod parçacıkları

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

Tıklatarak bu parçacığı ekleyebilirsiniz **Ekle parçacığı** kod penceresinin bağlam menüsünden **Visual C#**, yazın `tryf`ve tuşuna basın **sekmesini**, veya yazabilirsiniz `tryf` ve basın **sekmesini** iki kez.

Surround-with kod parçacığında örneği: c++ kısayol `if` ekleme parçacığını veya Çevrele kod parçası olarak kullanılabilir. Bir kod satırı seçerseniz (örneğin `return FALSE;`) ve ardından **Surround With**, ardından **varsa**, kod parçacığında satırında genişletilir:

```cpp
if (true)
{
    return FALSE;
}
```

## <a name="snippet-replacement-parameters"></a>Kod parçacığında değiştirme parametreleri

Kod parçacıkları yazmakta olduğunuz kesin kod uyacak şekilde değiştirmeniz gerekir yer tutucuları olan değiştirme parametreleri içerebilir. Önceki örnekte `true` uygun koşulu ile değiştirirsiniz değiştirme parametresi. Yaptığınız değişikliği parçacığında bulunan aynı değiştirme parametresi, her örneği için tekrarlanır.

Örneğin, Visual Basic'te bir özellik ekler bir kod parçacığı yoktur. ' I tıklatın **Ekle parçacığı** kod penceresinin bağlam menüsünde **kod düzenleri**, sonra **özellikleri, yordamlar, olayları**, özelliği tanımlarsınız. Aşağıdaki kod eklenir:

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

## <a name="code-snippet-manager"></a>Kod parçacığı Yöneticisi

Seçerek disk üzerinde şu an yüklü olan tüm kod parçacıkları ve konumlarını görebilirsiniz **Araçları**, **kod parçacıkları Yöneticisi**. Kod parçacıkları dili tarafından görüntülenir.

Kod parçacığında dizinlerle ekleyip çıkarabilirsiniz **Ekle** ve **kaldırmak** içinde düğmeleri **kod parçacıkları Yöneticisi** iletişim. Kod parçacıkları eklemek için kullanın **alma** düğmesi.

## <a name="see-also"></a>Ayrıca bkz.

[İzlenecek Yol: Kod Parçacığı Oluşturma](../ide/walkthrough-creating-a-code-snippet.md)  
[Nasıl Yapılır: Kod Parçacıklarını Dağıtma](../ide/how-to-distribute-code-snippets.md)  
[Kod Parçacıkları İçin En İyi Uygulamalar](../ide/best-practices-for-using-code-snippets.md)  
[Kod Parçacıklarının Sorunlarını Giderme](../ide/troubleshooting-snippets.md)  
[Visual C# Kod Parçacıkları](../ide/visual-csharp-code-snippets.md)  
[Visual C++ Kod Parçacıkları](../ide/visual-cpp-code-snippets.md)  
[Kod Parçacıkları Şema Başvurusu](../ide/code-snippets-schema-reference.md)