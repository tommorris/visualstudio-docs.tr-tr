---
title: 'Hata: Yerel makinede güvenlik duvarı | Microsoft Docs'
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
- vs.debug.error.firewall.localmachine
dev_langs:
- FSharp
- VB
- CSharp
- C++
ms.assetid: ab60dda9-7934-4891-aa2f-001380d2ed83
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6f4cee2d391038c9157666078c6fd83027bc35e6
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42688930"
---
# <a name="error-firewall-on-local-machine"></a>Hata: Güvenlik Duvarı Yerel Makinede
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [hata: yerel makinede güvenlik duvarı](https://docs.microsoft.com/visualstudio/debugger/error-firewall-on-local-machine).  
  
Internet Bağlantısı Güvenlik Duvarı, Visual Studio çalıştıran makinenin yerel makinede uzaktan hata ayıklamaya izin verecek şekilde ayarlanır değil. Yönetilen veya yerel uzaktan varsayılan aktarım ile hata ayıklama için TCP 135 bağlantı noktası DCOM trafik için açılmalıdır. Dosya ve yazıcı paylaşımı açılması gerekir ve devenv.exe özel durumlar listesine eklenmesi gerekir. Bazı IPSec bağlantı noktaları açma de gerekebilir.  
  
 Daha fazla bilgi için [ayarlanmış yukarı uzak Araçlar cihazda](http://msdn.microsoft.com/library/90f45630-0d26-4698-8c1f-63f85a12db9c).



