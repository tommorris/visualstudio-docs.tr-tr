---
title: Idiasession::put_loadaddress | Microsoft Docs
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
- IDiaSession::put_loadAddress method
ms.assetid: b157b245-1ea0-4b80-8962-d8b278dbc742
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e39ac68468113f371c032f2f29b4613fa229a3b7
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42675180"
---
# <a name="idiasessionputloadaddress"></a>IDiaSession::put_loadAddress
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [Idiasession::put_loadaddress](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiasession-put-loadaddress).  
  
Yükleme adresine karşılık gelen yürütülebilir dosyası için sembolleri bu sembol deposu içerisinde ayarlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT put_loadAddress (   
   ULONGLONG NewVal  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `NewVal`  
 [in] Yürütülebilir dosya için adres yükleyin.  
  
## <a name="remarks"></a>Açıklamalar  
 Sembol sanal adres (VA) özellikleri, bu yöntem değeri kullanılarak hesaplanır. Bu özellik sıfır olmayan ayarlanmadığı sürece sanal adresleri hesaplanmaz.  
  
> [!NOTE]
>  Aldığınızda, bu yöntemi çağırmanız gerekir [Idiasession](../../debugger/debug-interface-access/idiasession.md) başlamadan önce sanal özellikler üzerinde sembolleri kullanmanız gerekiyorsa nesneyi kullanmayı ve nesne.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)



