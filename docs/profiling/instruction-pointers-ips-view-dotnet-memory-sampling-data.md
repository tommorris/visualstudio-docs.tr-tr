---
title: "Yönerge işaretçileri (IP) görünümü - .NET bellek örnekleme verileri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Instruction Pointers view
ms.assetid: 7d91cc14-e8e9-4ebb-b14f-b9f0da770508
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- dotnet
ms.openlocfilehash: 193497f6fd995c8e3a31b5228675130d97641ffa
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="instruction-pointers-ips-view---net-memory-sampling-data"></a>Yönerge işaretçileri (IP) görünümü - .NET bellek örnekleme verileri
Profil oluşturma çalışması sırasında bellek tahsis derleme yönergeleri örnekleme yöntemini kullanarak toplanan .NET bellek ayırma profil oluşturma verileri IP'leri görünümünü listeler. Görünümün sütunlarını ayırmaları sayısı ve boyutu da listeler.  
  
 Yalnızca özel değerleri listelenmektedir.  
  
|Sütun|Açıklama|  
|------------|-----------------|  
|**İşlem kimliği**|İşlemi çalıştırmak profil oluşturma kimliği (PID).|  
|**İşlem adı**|İşlemin adı.|  
|**Modül adı**|Yönergeyi içeren modülü adı.|  
|**Modül yolu**|Yönergeyi içeren modülü yolu.|  
|**Kaynak dosya**|Yönerge içeren kaynak dosyası.|  
|**İşlev adı**|İşlevin adı.|  
|**İşlev satır numarası**|Bu işlev kaynak dosyadaki başlangıç satır sayısı.|  
|**İşlev adresi**|İşlev başlangıç adresi.|  
|**Kaynak satırı başlangıç**|Ayırma gerçekleştiği kaynak dosyasında başlangıç satır numarası.|  
|**Kaynak satır sonu**|Ayırma gerçekleştiği kaynak dosyasında bitiş satır numarası.|  
|**Kaynak karakter başlangıç**|Ayırma gerçekleştiği kaynak dosyası satırı başlangıç karakteri uzaklığı.|  
|**Kaynak karakter ucu**|Ayırma gerçekleştiği kaynak dosya satırında bir bitiş karakteri uzaklığı.|  
|**Yönerge adresi**|Yönerge adresi.|  
|**Özel ayırmaları**|Yönerge tarafından oluşturulan nesneleri toplam sayısı.|  
|**Özel ayırmaları %**|Yönerge tarafından ayrılan çalıştırmak profil oluşturulan tüm nesneler yüzdesi.|  
|**Özel bayt sayısı**|Profil çalışmasını ayrılan belleğin bayt sayısı yönergesi tarafından ayrılan.|  
|**Özel bayt %**|Yönerge tarafından ayrılan tüm profil çalıştırmak ayrılan belleği bayt yüzdesi.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yönerge İşaretçileri (IP) Görünümü](../profiling/instruction-pointers-ips-view-sampling-data.md)