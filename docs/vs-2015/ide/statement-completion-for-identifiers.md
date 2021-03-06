---
title: Tanımlayıcılar için ifade tamamlama | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IntelliSense [JavaScript], statement completion
- statement completion, JavaScript IntelliSense
ms.assetid: c2cd4945-c67e-471b-8057-96cfd25f7fb2
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 9ad7a83ac3eb7f0af57eed382ace32fdb80ccef2
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42693477"
---
# <a name="statement-completion-for-identifiers"></a>Tanımlayıcılar İçin İfade Tamamlama
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [Visual Studio 2017 belgeleri](https://docs.microsoft.com/en-us/visualstudio/).  
  
JavaScript için değişken bildirimlerini yazmaya açık izin vermez. Sonuç olarak, IntelliSense tamamlanma listeleri her zaman nesneler için sağlayamaz. Çeşitli durumlarda ortaya çıkabilir. Aşağıda birkaç yaygın olanlarından verilmiştir.  
  
-   Bir parametre bildirildi ancak bunu başka bir yerde etkin belgede aşağıdaki örnekte gösterildiği gibi çağrılmadı.  
  
    ```javascript  
    function illuminate(light) {  
             light.  // Accurate statement completion is not available   
                     // unless illuminate is called elsewhere with a   
                     // parameter that has a value. If it is called only  
                     // in a function that is a sibling to   
                     // illuminate(light) in the call hierarchy, the   
                     // IntelliSense engine also cannot determine the   
                     // parameter type.  
         }  
  
    // Sibling function. No statement completion for light   
    // object in preceding code.  
    function lightLamp() {  
        var x = illuminate(1);  
    }  
  
    // Uncomment the next line to obtain statement completion for  
    // light object in preceding code.  
    // var x = illuminate(1);  
    ```  
  
-   Bir olaya yanıt olarak çağrılan bir işlev nesnesidir. Tasarım zamanında IntelliSense altyapısı, bu durumda kullanılan nesnelerin türü belirlenemiyor.  
  
     IntelliSense altyapısı, olay, genellikle kullanımı çağrılması gerektiğini belirleyebilirseniz `addEventListener` etkin belgede bir olay için daha doğru IntelliSense bilgisi sağlanır.  
  
 IntelliSense bir nesnenin tanımlanamadı olduğunda, IntelliSense altyapısı tamamlanma listesi adlandırılmış varlıklar ya da etkin belgede bulunan tanımlayıcıları ile doldurur. Tamamlanma listesi bu tanımlayıcıları içerdiğinde, bilgi simgeleri bunları yanında görünür. Ayrıca, her bir tanımlayıcı için bir araç ipucu ifadesi bilinmeyen olduğunu gösterir. Aşağıdaki çizimde deyim tamamlama seçenekleri türünde bir nesne için gösterir. `light` , tanımlanamıyor nesne ve özelliklerini tanımsız olduğundan. Ancak, `intensity` özelliği olduğundan tanımlayıcı listesinde kullanılabilir olarak kullanılmış `illuminate` işlevi.  
  
 **Tanımlanamıyor bir nesne için tamamlama seçenekleri**  
  
 ![Tanımlayıcılar için JavaScript IntelliSense](../ide/media/js-intellisense-identifiers.png "js_intellisense_identifiers")  
  
 XML belge açıklamaları veya JavaScript IntelliSense genişletilebilirlik özelliklerini kullanarak tamamlanma listesi bir nesne için geçersiz kılabilirsiniz. Aksi takdirde kullanılabilir olmayabilir, bu özellikleri kullanarak, türü bilgilerini ve daha açıklayıcı IntelliSense bilgilerini sağlayabilirsiniz. Daha fazla bilgi için [JavaScript IntelliSense genişletme](../ide/extending-javascript-intellisense.md) ve [XML belge açıklamaları oluşturma](../ide/create-xml-documentation-comments-for-javascript-intellisense.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [JavaScript IntelliSense](../ide/javascript-intellisense.md)



