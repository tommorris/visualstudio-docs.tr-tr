---
redirect_url: /visualstudio/csharp-ide/refactoring/change-method-signature
title: "Parametreleri Kaldır yeniden düzenlemesi (C#) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.csharp.refactoring.remove
dev_langs: CSharp
helpviewer_keywords:
- parameters [C#], removing
- refactoring [C#], Remove Parameters
- Remove Parameters refactoring [C#]
ms.assetid: f4fc3265-0ef8-4398-a691-c338178697a6
caps.latest.revision: "24"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: d5e53d813d9b2dcefd2b2d19da2a76b6c0d1f989
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="remove-parameters-refactoring-c"></a>Parametreleri Kaldır Yeniden Düzenlemesi (C#)
`Remove Parameters`parametreleri yöntemleri, dizin oluşturucular ya da temsilciler kaldırmak için kolay bir yol sağlar düzenleme bir işlemdir. Parametreleri değişiklik bildirimini kaldırın; Burada üye olarak da adlandırılır her konumda parametre yeni bildirimi yansıtmak üzere kaldırılır.  
  
 Yöntemi, dizin oluşturucu veya temsilci imleci getirerek parametreleri Kaldır işlemini gerçekleştirin. İmleç konumu Kaldır çağrılacak olsa `Parameters` işlemi, tıklatın **yeniden düzenlemeniz** menüsünde klavye kısayol tuşuna basın veya kısayol menüsünden komutu seçin.  
  
> [!NOTE]
>  Bir genişletme yöntemi, ilk parametre kaldıramazsınız.  
  
### <a name="to-remove-parameters"></a>Parametreleri kaldırmak için  
  
1.  Adlı bir konsol uygulaması oluşturun `RemoveParameters`ve ardından Değiştir `Program` aşağıdaki kod ile.  
  
    ```csharp  
    class A  
    {  
        // Invoke on 'A'.  
        public A(string s, int i) { }  
    }  
  
    class B  
    {  
        void C()  
        {  
            // Invoke on 'A'.  
            A a = new A("a", 2);  
        }  
    }  
    ```  
  
2.  İmleci yöntemini getirin `A`, yöntem bildirimi veya yöntem çağrısı.  
  
3.  Gelen **yeniden düzenlemeniz** menüsünde, select **parametreleri Kaldır** görüntülemek için **parametreleri Kaldır** iletişim kutusu.  
  
     Ayrıca CTRL + R, görüntülenecek V klavye kısayolunu yazabilirsiniz **parametreleri Kaldır** iletişim kutusu.  
  
     Ayrıca, imleci sağ işaret **yeniden düzenlemeniz**ve ardından **parametreleri Kaldır** görüntülemek için **parametreleri Kaldır** iletişim kutusu.  
  
4.  Kullanarak **parametreleri** alanı, üzerinde imleç Konumlandır `int i`ve ardından **kaldırmak**.  
  
5.  **Tamam**'ı tıklatın.  
  
6.  İçinde **Değişiklikleri Önizle — Parametreleri Kaldır** iletişim kutusu, tıklatın **Uygula**.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir yöntem bildirimi veya yöntem çağrısı parametreleri kaldırabilirsiniz. İmleç yöntemi bildirimine veya temsilci adına getirin ve parametreleri Kaldır komutunu çağırın.  
  
> [!CAUTION]
>  Parametreleri etkinleştirir, başvurulan bir parametre üye, ancak gövdesinde kaldırmak için bu parametre başvuruları yöntemi gövdesinde kaldırmaz kaldırın. Bu, kodunuza yapı hatalara neden olabilir. Ancak, kullanabileceğiniz **Değişiklikleri Önizle** iletişim kutusunu yeniden düzenleme işlemi yürütmeden önce kodunuzu gözden geçirin.  
  
 Kaldırılmakta olan bir parametre için bir yöntem çağrısı sırasında değiştirilirse, parametre kaldırılmasını değişiklik de kaldırılır. Bir yöntem çağrısı, örneğin, değiştirilirse  
  
```csharp  
MyMethod(param1++, param2);  
```  
  
 to  
  
```csharp  
MyMethod(param2);  
```  
  
 yeniden düzenleme işlemi tarafından `param1` artmaz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yeniden düzenlemesi (C#)](refactoring-csharp.md)