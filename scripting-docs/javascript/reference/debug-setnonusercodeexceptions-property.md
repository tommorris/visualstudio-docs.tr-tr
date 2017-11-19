---
title: "Debug.setNonUserCodeExceptions özelliği | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 1dd2abee-a415-41bb-a359-017da62f9485
caps.latest.revision: "3"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3f53084d5580bc7b6b6c6356268dc60f519b2bd6
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="debugsetnonusercodeexceptions-property"></a>Debug.setNonUserCodeExceptions Özelliği
Hata ayıklayıcı kullanıcı işlenmemiş olarak kabul edilmesi için bu kapsamdaki herhangi bir try-catch bloğu olup olmadığını belirler. Özel durumlar durum, kullanıcının işlemediği olarak sınıflandırılmış veya işlenmemiş.  
  
 Bu özellik ayarlanmışsa `true` belirli bir kapsamda hata ayıklayıcı sonra bazı eylemler (örneğin, kesme) Geliştirici kullanıcının işlemediği özel durumları kesme isterse bu kapsam içinde oluşturulan özel durumları belirleyebilirsiniz. Bu özellik ayarlanmışsa `false` özelliği belirlenmemişse olarak aynıdır.  
  
 Hata ayıklama ile ilgili daha fazla bilgi için bkz: [etkin komut dosyası hata ayıklamaya genel bakış](http://go.microsoft.com/fwlink/p/?LinkId=249469).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Debug.setNonUserCodeExceptions [= bool];  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod bu özelliğinin nasıl ayarlanacağını gösterir.  
  
```JavaScript  
(function () {  
    Debug.setNonUserCodeExceptions = true;  
    try{  
        var x = null;  
        x.y();  
    } catch (e) {  
    // Catch the exception.  
    }  
})();  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]