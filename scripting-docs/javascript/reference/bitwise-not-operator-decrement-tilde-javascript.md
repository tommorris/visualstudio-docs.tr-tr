---
title: "Bitwise NOT işleci (~) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: ~
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- NOT operator
- bitwise operators, NOT operator
ms.assetid: 39f92474-fe05-4a8b-9ad8-caca93f82bca
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: aec64b055b260efb7a4b0d952aed9b3a5d7ddc82
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="bitwise-not-operator--javascript"></a>Bit Düzeyinde NOT İşleci (~) (JavaScript)
Bitwise NOT gerçekleştirir (değilleme) üzerinde bir ifade.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
result = ~ expression  
```  
  
## <a name="parameters"></a>Parametreler  
 *Sonuç*  
 Herhangi bir değişken.  
  
 *ifade*  
 Herhangi bir ifade.  
  
## <a name="remarks"></a>Açıklamalar  
 Tüm birli işleçleri gibi `~` işleci, ifadeler gibi değerlendirin:  
  
-   Undefined olarak uyguladıysanız veya `null` ifadeleri, bir çalışma zamanı hatası oluşur.  
  
-   Nesneleri dizelere dönüştürülür.  
  
-   Dizeleri sayılara mümkünse dönüştürülür. Aksi durumda, bir çalışma zamanı hatası tetiklenir.  
  
-   Boole değerleri sayılar (0, false ise, true ise 1) kabul edilir.  
  
 İşleci, sonuçta elde edilen sayıya uygulanır.  
  
 `~` İşleci ifadedeki değerlerin ikili gösterimidir arar ve bir bit düzeyinde değilleme işlemi yapar.  
  
 İfadede bir 1. herhangi bir basamak sonuç 0 olur. 0 ifadesinde herhangi bir basamak sonuç 1 olur.  
  
 Aşağıdaki örnek bitwise kullanımını göstermektedir değil (~) işleci.  
  
```  
var temp = ~5;  
```  
  
 Sonuçta elde edilen -6, aşağıdaki tabloda gösterildiği gibi değerdir.  
  
|İfade|İkili değer (iki kişinin tamamlama)|Ondalık değer|  
|----------------|---------------------------------------|-------------------|  
|5|00000000 00000000 00000000 00000101|5|  
|~5|11111111 11111111 11111111 11111010|-6|  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Mantıksal NOT işleci (!)](../../javascript/reference/logical-not-operator-decrement-exclpt-javascript.md)   
 [İşleç önceliği](../../javascript/operator-subtractprecedence-javascript.md)   
 [İşleç özeti (JavaScript)](../../javascript/misc/operator-subtractsummary-javascript.md)