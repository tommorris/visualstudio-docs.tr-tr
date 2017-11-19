---
title: "Verileri çözümlemek için performans kurallarını kullanma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1deed23e-b31b-4714-982f-08ceebfc3096
caps.latest.revision: "16"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7b99a2dd7de0c462f434231e3741138a15ab7047
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="using-performance-rules-to-analyze-data"></a>Verileri Analiz Etmek için Performans Kurallarını Kullanma
Performans uyarıları [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] profil oluşturma araçları program yürütme yavaşlatabilir profili bir uygulama sorunları gösterir. Uyarılar, daha kullanışlı verileri toplamak için koleksiyon yöntemleri değiştirmeniz gerekebilir de belirtebilirsiniz. Performans uyarıları, bir profil oluşturma oturumu otomatik olarak oluşturulur. Uyarılar görüntülenir **hata listesi** bir profil oluşturma veri dosyası Visual Studio'da açıldığında penceresi. Gelen **hata listesi** penceresinde, sorunu kaynak kodunu bulun ve sorunun nasıl giderileceği hakkındaki bilgiler gibi hatayla ilgili ayrıntılı bilgileri görüntüleyebilirsiniz. Ayrıca, ilgilendiğiniz değil uyarılarını devre dışı bırakabilirsiniz.  
  
> [!NOTE]
>  Profil Oluşturucu performans uyarıları program yürütme dinamik çözümlemesi tarafından oluşturulur ve Kod Analizi uyarıları bağımsızdır. Kod çözümleme kaynak kodunu statik analize dayalı yönetilen kod için performans uyarıları de oluşturabilirsiniz. Daha fazla bilgi için bkz: [yönetilen kod kalitesini analiz etme](../code-quality/analyzing-managed-code-quality-by-using-code-analysis.md) ve [performans uyarıları](../code-quality/performance-warnings.md).  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Nasıl yapılır: Performans uyarılarını görüntüleme](../profiling/how-to-view-performance-warnings.md)  
 Nasıl açılacağı hakkında bilgi sağlar **hata listesi** profil oluşturucu performans uyarıları görüntülemek için pencere.  
  
 [Nasıl yapılır: performans kurallarını yapılandırma](../profiling/how-to-configure-performance-rules.md)  
 Bireysel performans uyarıları açma veya kapatma hakkında bilgi sağlar.  
  
 [Performans kuralları başvurusu](../profiling/performance-rules-reference.md)  
 Performans uyarıları profil oluşturucu hakkında ayrıntılı bilgiler sağlar