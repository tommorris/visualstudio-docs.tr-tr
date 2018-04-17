---
title: 'Hata: RPC kimlik doğrulaması gerektiriyor. | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: reference
f1_keywords:
- vs.debug.error.rpc_requires_authentication
dev_langs:
- CSharp
- VB
- FSharp
- C++
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 7134a52f4c219b985cff3174703cf217057a5150
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="error-rpc-requires-authentication"></a>Hata: RPC Kimlik Doğrulaması Gerektiriyor
Visual Studio hata ayıklayıcısı uzak bilgisayara bağlanamıyor. Uzaktan hata ayıklama önleyen yerel bilgisayarda bir RPC ilkesi etkindir.  
  
### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
1.  Çalıştırma `\` *windir*`\system32\regedt32.exe`  
  
2.  Bulup silin `HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows NT\RPC\RestrictRemoteClients`.  
  
3.  Kayıt defteri değişikliği etkili şekilde bilgisayarınızı yeniden başlatın.  
  
4.  Sorun devam ederse, ilgili etki alanı yöneticinize başvurun **bilgisayar yapılandırması > Yönetim Şablonları > Sistem > uzak yordam çağrısı > kısıtlamaları kimliği doğrulanmamış RPC istemcileri için** Grup İlkesi ayar.