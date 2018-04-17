---
title: 'Hata: Güvenlik duvarı yerel makinede | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: reference
f1_keywords:
- vs.debug.error.firewall.localmachine
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
ms.openlocfilehash: 98badb458be79e17684c5ce134813d25b6605352
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="error-firewall-on-local-machine"></a>Hata: Güvenlik Duvarı Yerel Makinede
Internet Bağlantısı Güvenlik Duvarı yerel makinede, Visual Studio'dan, kullanmakta olduğunuz makine uzaktan hata ayıklama izin verecek şekilde ayarlanır değil. Yönetilen veya özgün uzaktan ile varsayılan aktarma hata ayıklama için TCP 135 bağlantı noktası DCOM trafik için açılmalıdır. Dosya ve yazıcı paylaşımı açılması gerekir ve devenv.exe özel durumlar listesine eklenmesi gerekir. Bazı IPSec bağlantı noktaları açma de gerekebilir.  
  
 Daha fazla bilgi için bkz: [uzaktan hata ayıklama](../debugger/remote-debugging.md).