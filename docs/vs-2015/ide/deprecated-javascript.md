---
title: '&lt;kullanım dışı&gt; (JavaScript) | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cf33d371-59da-4310-95ee-d7524fd9d58c
caps.latest.revision: 10
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 9d62067b8bd888c40a8cbc0f67d209760d487cf5
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42686542"
---
# <a name="ltdeprecatedgt-javascript"></a>&lt;kullanım dışı&gt; (JavaScript)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [Visual Studio 2017 belgeleri](https://docs.microsoft.com/en-us/visualstudio/).  
  
Bir kullanım dışı işlev veya metot belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<deprecated  
    type="deprecate|remove"  
    locid="descriptionID">description  
</deprecated>  
```  
  
#### <a name="parameters"></a>Parametreler  
 `type`  
 İsteğe bağlı. İşlev veya yöntem gelecekteki bir sürümde olup olmadığını kaldırılacak veya olup işlev veya yöntem zaten kaldırıldı ve kullanımını hataya neden belirtir. Kümesine `deprecate` işlev veya yöntem gelecekteki bir sürümde kaldırılacak belirtmek için. Kümesine `remove` işlev veya yöntem zaten kaldırıldığını belirtmek için.  
  
 `locid`  
 İsteğe bağlı. Yerelleştirme bilgilerini işlev veya yöntem tanımlayıcısı. Tanımlayıcıdır ya da bir üye kimliği veya karşılık gelen `name` öznitelik değeri bir ileti paketteki OpenAjax meta verileri tarafından tanımlanır. Belirtilen biçim tanımlayıcı türü bağımlı [ \<loc >](../ide/loc-javascript.md) öğesi.  
  
 `description`  
 İsteğe bağlı. İşlev veya kullanım dışı yöntem açıklaması.  
  
## <a name="remarks"></a>Açıklamalar  
 İçeren İşlevler, ek açıklama eklemek için kullanılan öğelerin `<deprecated>`, işlev gövdesinin herhangi bir deyim önce yerleştirilmelidir. Bir işlev kullanım dışı olarak işaretlediğinizde, değiştirmeniz önerilir, [ \<Özet >](../ide/summary-javascript.md) öğeyle `<deprecated>` öğesi.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod nasıl kullanılacağını gösterir `<deprecated>` öğesi.  
  
```javascript  
function areaFunction(radiusParam) {  
    /// <deprecated type="deprecate" >Determines the area of a circle when supplied a radius parameter.</deprecated>  
    /// <param name="radiusParam" type="Number">The radius of the circle.</param>  
    /// <returns type="Number">The area.</returns>  
    var areaVal;  
    areaVal = Math.PI * radiusParam * radiusParam;  
    return areaVal;  
}  
  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [XML Belge Açıklamaları](../ide/xml-documentation-comments-javascript.md)



