---
title: "Genel Bakış (hata ayıklama arabirimi Erişim SDK'sı) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
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
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: cb13b9a77bcd34b22a7a82182a63440cb02a4e76
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="overview-debug-interface-access-sdk"></a>Genel Bakış (Arabirim Erişimi SDK'sında Hata Ayıklama)
Microsoft hata ayıklama bilgileri erişmek için DIA SDK'yı kullanın. Microsoft hata ayıklama bilgileri biçimi değiştiğinde kodunuzu yeniden yazma gereğini ortadan kaldırır API kümesi bir COM tabanlı DIA SDK'sı sağlar. DIA SDK'sı tarafından oluşturulan .pdb ve .dbg dosyaları bulunan hata ayıklama bilgileri önceki sürümlerinin bir dizi okuma da sağlar [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] 5.0 ve sonraki sürümleri.  
  
 Her bir arabirime DIA SDK'sındaki farklı bir COM nesnesi dışında aksi belirtilmediği burada temsil eder. Ek arabirimleri ve bu nedenle ek nesneler oluşturulur açık sorguları yoluyla gibi [Idiadatasource::opensession](../../debugger/debug-interface-access/idiadatasource-opensession.md) veya [Idiasession::findchildren](../../debugger/debug-interface-access/idiasession-findchildren.md), yerine çağırarak`QueryInterface` varolan arabirim işaretçileri.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiadatasource::opensession](../../debugger/debug-interface-access/idiadatasource-opensession.md)   
 [IDiaSession::findChildren](../../debugger/debug-interface-access/idiasession-findchildren.md)