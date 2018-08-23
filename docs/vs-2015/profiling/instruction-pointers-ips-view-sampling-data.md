---
title: Yönerge işaretçileri (IP) görünümü - örnekleme verileri | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Instruction Pointers view
ms.assetid: c7f647bb-c5a3-4708-9f9d-33c0fd6e2e96
caps.latest.revision: 16
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d23c04906c9f1d3cd28ded7b88ee225c13240f53
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42629558"
---
# <a name="instruction-pointers-ips-view---sampling-data"></a>Yönerge İşaretçileri (IP) Görünümü- Örnekleme Verileri
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [yönerge işaretçileri (IP) görünümü - örnekleme verileri](https://docs.microsoft.com/visualstudio/profiling/instruction-pointers-ips-view-sampling-data).  
  
Örnekler, profil oluşturma çalışmasında toplanan doğrudan Yürütülüyor derleme yönergeleri için veri listeleri performans verilerini örnekleme IP'ler görünümü.  
  
> [!NOTE]
>  Windows 8 ve Windows Server 2012'deki Gelişmiş güvenlik özellikleri Visual Studio profil oluşturucu bu platformlarda veri toplayan bir şekilde önemli değişiklikler gerekmiştir. Windows Store apps ayrıca yeni toplama teknikleri gerektirir. Bkz: [Windows 8 ve Windows Server 2012 uygulamalarında performans araçları](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).  
  
|Sütun|Açıklama|  
|------------|-----------------|  
|**İşlem kimliği**|İşlem, profil oluşturma çalışması Kimliğine (PID).|  
|**İşlem adı**|İşlemin adı.|  
|**Modül adı**|Yönergeyi içeren modül adı.|  
|**Modül yolu**|Yönergeyi içeren modül yolu.|  
|**Kaynak dosyası**|Yönergeyi içeren kaynak dosyası.|  
|**İşlev adı**|Yönergeyi içeren işlev adı.|  
|**İşlevin satır numarası**|Satır numarası kaynak dosyada bu işlevin başlangıcı.|  
|**İşlev adresi**|Yüklenen ikili işlevinde başlangıç bellek adresi.|  
|**Kaynak satır başlangıcı**|Bu örnek, toplanan kaynak dosyadaki başlangıç satır numarası.|  
|**Kaynak satır sonu**|Bitiş satır numarası kaynak dosyada, bu örnek toplanmadı.|  
|**Kaynak karakter başlangıcı**|Bu örnek, toplanan kaynak dosya satırında başlangıç karakteri uzaklığı.|  
|**Kaynak karakter sonu**|Bu örnek, toplanan kaynak dosya satırdaki bitiş karakter uzaklığı.|  
|**Yönerge adresi**|Yüklenen ikili yönerge adresi.|  
|**Dışlamalı örnekler**|Yönerge yürütülürken, toplanan örneklerin toplam sayısı.|  
|**Dışlamalı örnek yüzdesi**|Yönerge yürütülürken, toplanmış olan profil oluşturma, tüm örneklerin yüzdesi.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yönerge işaretçileri (IP) görünümü - örnekleme](../profiling/instruction-pointers-ips-view-dotnet-memory-sampling-data.md)



