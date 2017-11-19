---
title: "Genel Bakış (hata ayıklama arabirimi Erişim SDK'sı) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- user-defined types
- .dbg files
- modules
- interfaces [DIA SDK]
- DBG files
- procedures [DIA SDK]
- executable files
- COM objects, in DIA SDK
- compilands
- executable images
ms.assetid: 720b4479-a8bc-4fec-860e-80c1a0780405
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d4cd0206e402600cbe9002c931adb7ff6a2cc680
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="overview-debug-interface-access-sdk"></a>Genel Bakış (Arabirim Erişimi SDK'sında Hata Ayıklama)
Microsoft hata ayıklama bilgileri erişmek için DIA SDK'yı kullanın. Microsoft hata ayıklama bilgileri biçimi değiştiğinde kodunuzu yeniden yazma gereğini ortadan kaldırır API kümesi bir COM tabanlı DIA SDK'sı sağlar. DIA SDK'sı tarafından oluşturulan .pdb ve .dbg dosyaları bulunan hata ayıklama bilgileri önceki sürümlerinin bir dizi okuma da sağlar [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] 5.0 ve sonraki sürümleri.  
  
 Her bir arabirime DIA SDK'sındaki farklı bir COM nesnesi dışında aksi belirtilmediği burada temsil eder. Ek arabirimleri ve bu nedenle ek nesneler oluşturulur açık sorguları yoluyla gibi [Idiadatasource::opensession](../../debugger/debug-interface-access/idiadatasource-opensession.md) veya [Idiasession::findchildren](../../debugger/debug-interface-access/idiasession-findchildren.md), yerine çağırarak`QueryInterface` varolan arabirim işaretçileri.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiadatasource::opensession](../../debugger/debug-interface-access/idiadatasource-opensession.md)   
 [Idiasession::findchildren](../../debugger/debug-interface-access/idiasession-findchildren.md)