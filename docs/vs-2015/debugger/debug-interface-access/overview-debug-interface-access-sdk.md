---
title: (Hata ayıklama arabirimi Erişim SDK'sı) genel bakış | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
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
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8de5b25b1ece8c4523ba222a97f1107d2275ba3a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42688280"
---
# <a name="overview-debug-interface-access-sdk"></a>Genel Bakış (Arabirim Erişimi SDK'sında Hata Ayıklama)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [genel bakış (arabirim erişimi SDK'ı hata ayıklama)](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/overview-debug-interface-access-sdk).  
  
DIA SDK'sı Microsoft hata ayıklama bilgilerine erişmek için kullanın. DIA SDK'sı bir COM tabanlı Microsoft hata ayıklama bilgileri biçimi değiştiğinde kodunuzu yeniden yazma gereğini ortadan kaldırıyor API kümesi sağlar. DIA SDK Ayrıca, bir grup önceki sürümleri tarafından oluşturulan .pdb ve .dbg dosyaları bulunan hata ayıklama bilgilerini okumak sağlar [!INCLUDE[vcprvc](../../includes/vcprvc-md.md)] 5.0 ve üzeri sürümler.  
  
 Her arabirimi DIA SDK içinde farklı bir COM nesnesi dışında başka türlü nerede temsil eder. Ek arabirimleri ve bu nedenle ek nesneler, oluşturulma açık sorguları yoluyla gibi [Idiadatasource::opensession](../../debugger/debug-interface-access/idiadatasource-opensession.md) veya [Idiasession::findchildren](../../debugger/debug-interface-access/idiasession-findchildren.md), yerine çağırarak`QueryInterface` üzerinde varolan arabirim işaretçileri.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiadatasource::opensession](../../debugger/debug-interface-access/idiadatasource-opensession.md)   
 [IDiaSession::findChildren](../../debugger/debug-interface-access/idiasession-findchildren.md)



