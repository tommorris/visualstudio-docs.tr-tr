---
title: Windows çalışma zamanı DateTime ve TimeSpan Beyanları | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- javascript
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- JavaScript, Windows Runtime dates and times
- TimeSpan [JavaScript]
- DateTime [JavaScript]
ms.assetid: 9743e9ac-9054-463e-8264-427183e4905f
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3d7c394b57eb0215e3dff857d935b367e602c2b0
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791909"
---
# <a name="windows-runtime-datetime-and-timespan-representations"></a>Windows çalışma zamanı DateTime ve TimeSpan temsili
Tarihler ve saatler JavaScript gösterimini Windows çalışma zamanı sürümünden farklıdır. Windows çalışma zamanı [DateTime](http://msdn.microsoft.com/library/windows/apps/windows.foundation.datetime.aspx) yapısı JavaScript temsil edilen bir [tarih](../javascript/reference/date-object-javascript.md) eşleşen bir yedekleme deposu olan `DateTime` verileri (ve farklı aralığı ve JavaScript duyarlılık `Date`). Bu özel değiştirirseniz `Date` nesnesi, bu duruma standart JavaScript `Date` ve duyarlık kaybeder. JavaScript `Date` değerleri Windows çalışma zamanı için geçirilebilir `DateTime` ve hangi özel durumlar hazırlama sonuçlanabilir aralığı işaretli olacaktır.  
  
 Windows çalışma zamanı [TimeSpan](http://msdn.microsoft.com/en-us/c5defb66-819c-4796-85b5-07ed249a5d86) yapısı milisaniye dönüştürülür ve JavaScript sayı olarak döndürdü.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Windows çalışma zamanı JavaScript kullanma](../jswinrt/using-the-windows-runtime-in-javascript.md)