---
title: Satırlar görünümü - .NET bellek örnekleme verileri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- Lines view
ms.assetid: 6631ab87-0e62-4c76-a063-4ea7222b07da
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 518a05c72d25c5f1abc136e774d9867a9fc66c36
ms.sourcegitcommit: ce154aee5b403d5c1c41da42302b896ad3cf8d82
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/07/2018
ms.locfileid: "34845645"
---
# <a name="lines-view---net-memory-sampling-data"></a>Satırlar görünümü - .NET bellek örnekleme verileri
Satırlar görünümü örnekleme yöntemini kullanan .NET bellek ayırma profil oluşturma verileri için profil oluşturma çalışması sırasında bellek tahsis deyimleri listeler. Sütunları ayırmaları sayısı ve boyutu da içerir.  
  
 Bir kaynak dosyasında bir deyim bir kaynak dosyasında birden fazla satırı kapsayabilir ve tek bir satıra birden fazla deyim içerebilir.  
  
 Bir deyim aşağıdaki tarafından tanımlanır:  
  
-   Function deyimi içeren kaynak dosyası.  
  
-   Deyimi içeren işlev.  
  
-   Deyim başlatan kaynak satırı.  
  
-   Deyim başlatan kaynak satırdaki karakter.  
  
-   Deyim erdiği kaynak satırı.  
  
-   Deyim erdiği kaynak satırdaki karakter.  
  
 Satır ad sütunu tanımlayıcısı verileri sıralanabilir bir birleşimini sağlar.  
  
 Tanımı gereği, diğer işlevleri bir deyim çağırmaz. Bu nedenle, yalnızca özel değerler listelenmektedir.  
  
|Sütun|Açıklama|  
|------------|-----------------|  
|**İşlem kimliği**|İşlemi çalıştırmak profil oluşturma kimliği (PID).|  
|**İşlem adı**|İşlemin adı.|  
|**Modül adı**|Deyim içeren modülü adı.|  
|**Modül yolu**|Deyim içeren modülü yolu.|  
|**Kaynak dosya**|Deyimi içeren kaynak dosya.|  
|**İşlev adı**|Deyimi içeren işlevin adı.|  
|**İşlev satır numarası**|Bu işlev kaynak dosyadaki başlangıç satır sayısı.|  
|**İşlev adresi**|İşlev başlangıç adresi.|  
|**Kaynak satırı başlangıç**|Ayırma gerçekleştiği kaynak dosyasında başlangıç satır numarası.|  
|**Kaynak satır sonu**|Ayırma gerçekleştiği kaynak dosyasında bitiş satır numarası.|  
|**Kaynak karakter başlangıç**|Ayırma gerçekleştiği kaynak dosyası satırı başlangıç karakteri uzaklığı.|  
|**Kaynak karakter ucu**|Ayırma gerçekleştiği kaynak dosya satırında bir bitiş karakteri uzaklığı.|  
|**Satırı adı**|Aşağıdaki söz dizimini içeren satırı profil oluşturucu ürettiği tanıtıcısı:`Source File`**; [**  `Line Number Start` **,**`Character Start`**] ->; [** `Line Number Start,Character Start`**]**|  
|**Özel ayırmaları**|Bu satırda oluşturulan nesneleri toplam sayısı.|  
|**Özel ayırmaları %**|Bu satırda ayrılan çalıştırmak profil oluşturulan tüm nesneler yüzdesi.|  
|**Özel bayt sayısı**|Bu satırda ayrılan tüm profil çalıştırmak ayrılan belleği bayt yüzdesi.|  
|**Özel bayt %**|Bu satırda ayrılan tüm profil çalıştırmak ayrılan belleği bayt yüzdesi.|  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Satırlar Görünümü](../profiling/lines-view-sampling-data.md)