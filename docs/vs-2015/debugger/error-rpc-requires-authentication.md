---
title: 'Hata: RPC kimlik doğrulaması gerektiriyor. | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.error.rpc_requires_authentication
dev_langs:
- FSharp
- VB
- CSharp
- C++
ms.assetid: 88362b3b-8fbe-431f-96a4-80e2d822bbc7
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1e606c0e730b279723248a3fdbdd5b3e2bca1c4a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42688196"
---
# <a name="error-rpc-requires-authentication"></a>Hata: RPC Kimlik Doğrulaması Gerektiriyor
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [hata: RPC kimlik doğrulaması gerektirir](https://docs.microsoft.com/visualstudio/debugger/error-rpc-requires-authentication).  
  
Visual Studio hata ayıklayıcı uzak bilgisayara bağlanamıyor. Yerel bilgisayarda uzaktan hata ayıklamayı engelleyen bir RPC ilkesi etkin.  
  
### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
1.  Çalıştırma `\` *windir*`\system32\regedt32.exe`  
  
2.  Bulun ve Sil `HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows NT\RPC\RestrictRemoteClients`.  
  
3.  Kayıt defteri değişikliği etkili şekilde bilgisayarınızı yeniden başlatın.  
  
4.  Sorun devam ederse, ilgili etki alanı yöneticinizle iletişime **bilgisayar yapılandırması -> Yönetici Şablonları - > Sistem -> uzak yordam çağrısı, kimliği doğrulanmamış RPC istemciler için kısıtlamaları ->** grubu ilke ayarı.



