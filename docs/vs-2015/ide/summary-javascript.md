---
title: '&lt;Özet&gt; (JavaScript) | Microsoft Docs'
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
- summary JavaScript XML tag
- <summary> JavaScript XML tag
ms.assetid: 6540582d-bdb3-42ec-ad2f-c176783e6f9c
caps.latest.revision: 15
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 79aeb36e62279dcdafd2adb0143fa70ce2ee0eba
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42684582"
---
# <a name="ltsummarygt-javascript"></a>&lt;Özet&gt; (JavaScript)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [Visual Studio 2017 belgeleri](https://docs.microsoft.com/en-us/visualstudio/).  
  
Bir işlev veya metot için açıklamayı belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<summary locid="descriptionID">description  
</summary>  
```  
  
#### <a name="parameters"></a>Parametreler  
 `locid`  
 İsteğe bağlı. Yerelleştirme bilgilerini işlev veya yöntem tanımlayıcısı. Tanımlayıcıdır ya da bir üye kimliği veya karşılık gelen `name` öznitelik değeri bir ileti paketteki OpenAjax meta verileri tarafından tanımlanır. Belirtilen biçim tanımlayıcı türü bağımlı [ \<loc >](../ide/loc-javascript.md) öğesi.  
  
 `description`  
 İsteğe bağlı. İşlev veya yöntem açıklaması.  
  
## <a name="remarks"></a>Açıklamalar  
 İçeren İşlevler, ek açıklama eklemek için kullanılan öğelerin [ \<Özet >](../ide/summary-javascript.md), [ \<param >](../ide/param-javascript.md), ve [ \<döndürür >](../ide/returns-javascript.md), işlev gövdesi herhangi bir deyim önce yerleştirilmelidir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod nasıl kullanılacağını gösterir `<summary>` öğesi.  
  
```javascript  
function areaFunction(radiusParam)  
{  
    /// <summary>Determines the area of a circle when supplied a radius parameter.</summary>  
    /// <param name="radiusParam" type="Number">The radius of the circle.</param>  
    /// <returns type="Number">The area.</returns>  
    var areaVal;  
    areaVal = Math.PI * radiusParam * radiusParam;  
    return areaVal;  
}  
  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [XML Belge Açıklamaları](../ide/xml-documentation-comments-javascript.md)



