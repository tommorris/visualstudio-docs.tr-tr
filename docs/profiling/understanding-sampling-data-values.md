---
title: "Örnekleme veri değerlerini anlama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- sampling profiling method
- Profiling Tools, sampling
ms.assetid: fad540a8-24b6-4ff9-91ce-e67e9a58399d
caps.latest.revision: "22"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 95869fd4c3b52853417c847d32f7507c90471c2d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="understanding-sampling-data-values"></a>Örnekleme Veri Değerlerini Anlama
*Örnekleme* profili oluşturma yöntemi, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] profil oluşturma araçları Bilgisayar işlemcisi belirlenen aralıklarla keser ve işlev çağrı yığını toplar. A *çağrı yığını* işlemci yürütülen işlevler hakkında bilgi depolar dinamik bir yapıdır.  
  
 **Gereksinimler**  
  
-   [!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)], [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)], [!INCLUDE[vsPro](../code-quality/includes/vspro_md.md)]  
  
 Profil Oluşturucu analiz işlemci hedef işleminde kod yürütmek olup olmadığını belirler. İşlemci kod hedef işleminde yürütülmüyor, örnek atılır.  
  
 İşlemci hedef kod yürütüyor, profil oluşturucu çağrı yığınında her işlevi örnek sayısını artırır. Örnek alındıktan aynı anda yalnızca bir işlevi çağrı yığınında kodu yürütülüyor. Diğer yığında döndürmek bunların alt öğeleri için bekleyen işlev çağrılarını hiyerarşideki üst işlevlerdir.  
  
 Profil Oluşturucu artışlarla örnek olayı için *özel* örnek kendi yönergeleri yürütülmekte işlevi sayısı. Özel bir örnek de toplam parçası olduğundan (*dahil*) örnekleri işlevinin, şu anda etkin işlevi (bunlar dahil) örnek sayısı da artar.  
  
 Profil Oluşturucu diğer işlevleri çağrı yığınında kapsayıcı örnek sayısını artırır.  
  
## <a name="inclusive-samples"></a>Kapsayıcı örnekleri  
 Hedef işlevi yürütülmesi sırasında toplanan örnek toplam sayısı.  
  
 Bu işlev kodu doğrudan yürütülmesi sırasında toplanan örnekleri ve hedef işlev tarafından çağrılan alt işlevleri yürütülmesi sırasında toplanan örnekleri içerir.  
  
## <a name="exclusive-samples"></a>Özel örnekleri  
 Hedef işlevi yönergeleri doğrudan yürütülmesi sırasında toplanan örnek sayısı.  
  
 Özel örnekleri hedef işlev tarafından çağrılan işlevleri yürütülmesi sırasında toplanan örnekleri dahil etmeyin.  
  
## <a name="inclusive-percent"></a>Kapsayıcı yüzde  
 Toplam işlevi veya veri aralığının her ikisi de dahil örnekleri olan profil çalıştırın (bunlar dahil) örnek sayısını yüzdesi.  
  
## <a name="exclusive-percent"></a>Özel yüzde  
 Toplam işlevi veya veri aralığı özel örnekleri olan çalıştırmak Profil özel örnek sayısını yüzdesi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: Koleksiyon yöntemleri seçme](../profiling/how-to-choose-collection-methods.md)   
 [Araçları verilerini performansını analiz etme](../profiling/analyzing-performance-tools-data.md)