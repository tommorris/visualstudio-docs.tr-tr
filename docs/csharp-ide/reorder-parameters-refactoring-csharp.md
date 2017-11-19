---
redirect_url: /visualstudio/csharp-ide/refactoring/change-method-signature
title: "Yeniden düzenlemesi (C#) parametreleri yeniden Sırala | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.csharp.refactoring.reorder
dev_langs: CSharp
helpviewer_keywords:
- refactoring [C#], Reorder Parameters
- Reorder Parameters refactoring [C#]
ms.assetid: 4dabf21a-a9f0-41e9-b11b-55760cf2bd90
caps.latest.revision: "26"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 3469e9ae7101c9e180fba5558fce389c6dfcc72d
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="reorder-parameters-refactoring-c"></a>Parametreleri Yeniden Sırala (C#) yeniden düzenlemesi
`Reorder Parameters`Visual C# yöntemler, dizin oluşturucular ve temsilciler parametreleri sırasını değiştirmek için kolay bir yol sağlayan işlemidir. `Reorder Parameters`bildirimi değiştirir ve burada üyenin çağrıldığı her konumda parametreleri yeni sırayı yansıtmak için yeniden düzenlenir.  
  
 Gerçekleştirmek için `Reorder Parameters` işlemi, ya da bir yöntemi, dizin oluşturucu veya temsilci yanındaki imleci yerleştirin. İmleç konumu olduğunda çağırma `Reorder Parameters` işlemi klavye kısayol tuşuna basarak veya kısayol menüsünden komutunu tıklatarak.  
  
> [!NOTE]
>  Bir genişletme yöntemi ilk parametreyi sıralayamazsınız.  
  
### <a name="to-reorder-parameters"></a>Parametreleri yeniden sıralamak için  
  
1.  Adlı bir sınıf kitaplığı oluşturmak `ReorderParameters`ve ardından Değiştir `Class1` aşağıdaki kod örneği ile.  
  
    ```csharp  
    class ProtoClassA  
    {  
        // Invoke on 'MethodB'.  
        public void MethodB(int i, bool b) { }  
    }  
  
    class ProtoClassC  
    {  
        void D()  
        {  
            ProtoClassA MyClassA = new ProtoClassA();  
  
            // Invoke on 'MethodB'.  
            MyClassA.MethodB(0, false);  
        }  
    }  
    ```  
  
2.  İmleç Yerleştir `MethodB`, yöntem bildirimi veya yöntem çağrısı.  
  
3.  Üzerinde **yeniden düzenlemeniz** menüsünde tıklatın **parametreleri yeniden Sırala**.  
  
     **Parametreleri yeniden Sırala** iletişim kutusu görüntülenir.  
  
4.  İçinde **parametreleri yeniden Sırala** iletişim kutusunda `int i` içinde **parametreleri** listesinde ve aşağı düğmesini tıklatın.  
  
     Alternatif olarak, sürükleyebilirsiniz `int i` sonra `bool b` içinde **parametreleri** listesi.  
  
5.  İçinde **parametreleri yeniden Sırala** iletişim kutusu, tıklatın **Tamam**.  
  
     Varsa **başvuru değişikliklerini Önizleme** seçeneği seçildiğinde, **parametreleri yeniden Sırala** iletişim kutusu, **Değişiklikleri Önizle - Parametreleri Yeniden Sırala** iletişim kutusu görüntülenir. Önizleme için parametre listesinde değişikliklerden sağlar `MethodB` imza ve yöntem çağrısının.  
  
    1.  Varsa **Değişiklikleri Önizle - Parametreleri Yeniden Sırala** iletişim kutusu görüntülenirse, tıklatın **Uygula**.  
  
         Bu örnekte yöntem bildirimi ve tüm yöntem çağırma siteleri `MethodB` güncelleştirilir.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir yöntem bildirimi veya yöntem çağrısı parametrelerinden sıralayabilirsiniz. Üzerinde veya yöntem veya temsilci bildiriminin yanındaki ancak gövdesi imleç Konumlandır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yeniden düzenlemesi (C#)](refactoring-csharp.md)