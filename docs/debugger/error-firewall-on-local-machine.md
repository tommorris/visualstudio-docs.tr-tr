---
title: "Hata: Güvenlik duvarı yerel makinede | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.debug.error.firewall.localmachine
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: ab60dda9-7934-4891-aa2f-001380d2ed83
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f0eb7158fe2274fbe8707a147fe63a0937689d23
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="error-firewall-on-local-machine"></a>Hata: Güvenlik Duvarı Yerel Makinede
Internet Bağlantısı Güvenlik Duvarı yerel makinede, Visual Studio'dan, kullanmakta olduğunuz makine uzaktan hata ayıklama izin verecek şekilde ayarlanır değil. Yönetilen veya özgün uzaktan ile varsayılan aktarma hata ayıklama için TCP 135 bağlantı noktası DCOM trafik için açılmalıdır. Dosya ve yazıcı paylaşımı açılması gerekir ve devenv.exe özel durumlar listesine eklenmesi gerekir. Bazı IPSec bağlantı noktaları açma de gerekebilir.  
  
 Daha fazla bilgi için bkz: [uzaktan hata ayıklama](../debugger/remote-debugging.md).