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
ms.assetid: 85976ad9-4c9a-4e7b-896e-66ec6f955199
caps.latest.revision: "13"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 6c295efd0cb6fcf46ed9d76f080a951d9ae79080
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="code-snippets"></a>Kod Parçacıkları
Kod parçacıkları, bağlam menü komutu veya kısayollarıyla birleşimini kullanarak bir kod dosyasında eklenebilir yeniden kullanılabilir kod küçük taşlarıdır. Try-finally gibi sık kullanılan kod blokları veya if-else blokları genellikle içerir, ancak tüm sınıfları veya yöntemleri eklemek için kullanılabilir.  
  
## <a name="expansion-snippets-and-surround-with-snippets"></a>Genişletme parçacıkları ve Surround-With kod parçacıkları  
 Visual Studio'da kod parçacığını iki tür vardır: Belirtilen ekleme noktasına eklenir ve bir kod parçacığında kısayol değiştirebilir, genişletme parçacıkları ve seçili kod bloğunu eklenen surround-with kod parçacıkları (C# ve C++ yalnızca).  
  
 Bir ekleme parçacığı örneği: C# ' ta kısayol tryf try-finally bloğu eklemek için kullanılır:  
  
```  
try  
{  
  
}  
finally  
{  
  
}  
  
```  
  
 Tıklatarak bu parçacığı ekleyebilirsiniz **Ekle parçacığı** kod penceresinin bağlam menüsünden **Visual C#**, yazın `tryf`, sekme veya yazın `tryf` sekmesini + SEKME tuşuna basın.  
  
 Surround-with kod parçacığında örneği: c++ kısayol `if` ekleme parçacığını veya Çevrele kod parçası olarak kullanılabilir. Bir kod satırı seçerseniz (örneğin `return FALSE;`) ve ardından **Surround With**, ardından **varsa**, kod parçacığında satırında genişletilir:  
  
```  
if (true)  
{  
    return FALSE;  
}  
  
```  
  
## <a name="snippet-replacement-parameters"></a>Kod parçacığında değiştirme parametreleri  
 Kod parçacıkları yazmakta olduğunuz kesin kod uyacak şekilde değiştirmeniz gerekir yer tutucuları olan değiştirme parametreleri içerebilir. Önceki örnekte `true` uygun koşulu ile değiştirirsiniz değiştirme parametresi. Yaptığınız değişikliği parçacığında bulunan aynı değiştirme parametresi, her örneği için tekrarlanır.  
  
 Örneğin, Visual Basic'te bir özellik ekler bir kod parçacığı yoktur. ' I tıklatın **Ekle parçacığı** kod penceresinin bağlam menüsünde **kod düzenleri**, sonra **özellikleri, yordamlar, olayları**, özelliği tanımlarsınız. Aşağıdaki kod eklenir:  
  
```  
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
 Tıklatarak diskte, şu an yüklü olan tüm kod parçacıkları artı konumlarını görebilirsiniz **Araçlar/kod parçacıkları Yöneticisi**. Kod parçacıkları dili tarafından görüntülenir.  
  
 Kod parçacığında dizinlerle ekleyip çıkarabilirsiniz **Ekle** ve **kaldırmak** içinde düğmeleri **kod parçacıkları Yöneticisi** iletişim. Kod parçacıkları eklemek için kullanın **alma** düğmesi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İzlenecek yol: kod parçacığı oluşturma](../ide/walkthrough-creating-a-code-snippet.md)   
 [Nasıl yapılır: kod parçacıklarını dağıtma](../ide/how-to-distribute-code-snippets.md)   
 [Kod parçacıkları için en iyi uygulamalar](../ide/best-practices-for-using-code-snippets.md)   
 [Kod parçacıkları sorunlarını giderme](../ide/troubleshooting-snippets.md)   
 [Visual C# kod parçacıkları](../ide/visual-csharp-code-snippets.md)   
 [Visual C++ kod parçacıkları](../ide/visual-cpp-code-snippets.md)   
 [Kod parçacıkları şema başvurusu](../ide/code-snippets-schema-reference.md)