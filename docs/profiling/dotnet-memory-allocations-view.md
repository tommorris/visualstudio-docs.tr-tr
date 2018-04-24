---
title: .NET bellek ayırma görünümü | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.view.allocation
helpviewer_keywords:
- performance reports, allocation view
- Allocations view
- profiling tools, Allocation view
- profiling tools reports, Allocation view
ms.assetid: 01eb876e-c413-4516-977b-4f896929e8a6
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2b293c5a6fe64324cb306933d90049548e7a6098
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="net-memory-allocations-view"></a>.NET Bellek Ayırma Görünümü
Ayırmalar görünümü profil çalışması sırasında oluşturulan türlerini listeler. Her tür ayırma sonuçlandı işlevi yürütme yollarını görüntüler bir çağrı ağacı kök düğümü türüdür.  
  
 Veri türü satırda profil Çalıştır oluşturulan nesneleri türü toplam sayısı ve bu tür nesneleri için ayrılan bayt toplam sayısını görüntüler. (Bunlar dahil) ve özel bir tür için her zaman aynı değerlerdir.  
  
-   Kapsayıcı işlevi ve üst işlev çağrısı ağacında tarafından çağrılan alt işlevleri örneklerinde oluşturulan nesneler için değerlerdir.  
  
-   Özel üst işlevin adı veriliyordu olduğunda doğrudan işlevi tarafından oluşturulan nesneler için değerlerdir. Alt işlevlerde oluşturulan nesneler dahil edilmez.  
  
 Bir işlev için veri oluşturulan nesnelerin sayısı ve üst türündeki nesneler için ayrılan bayt sayısını görüntüler.  
  
## <a name="highlighting-the-execution-hot-path"></a>Yürütme etkin yolunuzda vurgulama  
 Üst tür çoğu nesnelerin oluşturulan çağrı ağacı yürütme yolunu bulabilirsiniz.  
  
-   En etkin yol görüntülemek için tür veya işleve sağ tıklayın ve ardından **genişletin etkin yolunuzda**.  
  
|Sütun|Açıklama|  
|------------|-----------------|  
|**Ad**|Ayrılmış tür veya işlev adı.|  
|**İşlem kimliği**|İşlemi çalıştırmak profil oluşturma kimliği (PID).|  
|**İşlem adı**|İşlemin adı.|  
|**Modül adı**|Tür veya işleve içeren modülü adı.|  
|**Modül yolu**|Tür veya işleve içeren modülü yolu.|  
|**Kaynak dosya**|Tür veya işlev için tanım içeriyor kaynak dosya.|  
|**İşlev satır numarası**|Bu tür tanımı veya kaynak dosya işlevi başlangıç satır sayısı.|  
|**düzeyi**|Verileri bir tür veya işlev için olup olmadığını gösterir.|  
|**Kapsayıcı ayırmaları**|-Bir işlev için üst türü işlev tarafından oluşturulan nesnelerin toplam sayısı. Bu sayı, alt işlevlerde oluşturulan nesneleri içerir.<br />-Bir türü için oluşturulan örnekleri bu türdeki toplam sayısı.|  
|**Kapsayıcı ayırmaları %**|-Bir işlev için işlevi tarafından üst tür (bunlar dahil) tahsis edilen profil Çalıştır oluşturulan tüm nesneler yüzdesi.<br />-İçin bir tür, profil çalıştırdığınızda oluşturulan nesneleri toplam sayısı yüzdesi türdeki örneklerin yoktu.|  
|**Özel ayırmaları**|-Bir işlev için işlevi, doğrudan çağrı yığını üstünde yürütülürken zaman, oluşturulan nesne sayısı. Bu sayı, alt işlevlerde oluşturulan nesneler içermez.<br />-Bir türü için oluşturulan örnekleri bu türdeki toplam sayısı.|  
|**Özel ayırmaları %**|-Bir işlev için özel ayırmaları işlevi tarafından üst türünde olan profil Çalıştır oluşturulan tüm nesneler yüzdesi.<br />-İçin bir tür, profil çalıştırdığınızda oluşturulan nesneleri toplam sayısı yüzdesi türdeki örneklerin yoktu.|  
|**Kapsayıcı bayt**|-Bir işlev için üst türündeki nesneler için işlevi tarafından ayrılan belleğin bayt sayısı. Bu sayı, alt işlevleri tarafından ayrılmış bellek içerir.<br />-Bir türü için profil türü örnekleri için Çalıştır ayrılan toplam bayt sayısı.|  
|**Kapsayıcı bayt %**|-Bir işlev için profil çalışmasını ayrılan tüm bellek yüzdesini işlevi tarafından üst tür (bunlar dahil) ayrılmasını oluştu.<br />-İçin bir tür, profil çalıştıran tüm bellek yüzdesi için ayrıldı türünün örnekleri.|  
|**Özel bayt sayısı**|-Bir işlev için üst türündeki nesneler için işlevi tarafından ayrılan belleğin bayt sayısı. Bu sayı, alt işlevleri tarafından ayrılmış bellek içermez.<br />-İçin bir tür, profil ayrılan bayt sayısı toplam türü örnekleri için çalıştırın.|  
|**Özel bayt %**|-Bir işlev için profil çalışmasını ayrılan tüm bellek yüzdesini işlevi tarafından üst tür özel ayrılmasını oluştu.<br />-İçin bir tür, profil çalıştıran tüm bellek yüzdesi için ayrıldı türünün örnekleri.|