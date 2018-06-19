---
title: toString yöntemi (tarih) | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: d3037289-d805-409b-8781-045c59a2c404
caps.latest.revision: 3
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 67b6dce74e3796c8b54431b56809473e3c5e59a5
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791585"
---
# <a name="tostring-method-date"></a>toString Yöntemi (Tarih)
Bir tarih dize gösterimini döndürür. Dize biçimi bölgesel ayarına bağlıdır. ABD İngilizce (en-us), onu şu şekildedir:  
  
 *Haftanın günü* *ay* *gün* *saat*: *minute*:*ikinci* *saat dilimi* *yıl*  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
date.toString()  
```  
  
## <a name="parameters"></a>Parametreler  
 `date`  
 Gerekli. Bir dize olarak göstermek için tarih.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Tarih dize gösterimini döndürür.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını göstermektedir `toString` bir tarihle yöntemi.  
  
```JavaScript  
var myDate = new Date();  
myDate.setFullYear(2100, 5, 5);  
var dateString = myDate.toString();  
document.write(dateString);  
  
// Output: <date>  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]