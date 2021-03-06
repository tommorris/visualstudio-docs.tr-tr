---
title: Katman etkileşim verileri toplama | Microsoft Docs
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
- vs.performance.property.tierinteraction
helpviewer_keywords:
- Profiling Tools,ADO.NET profiling
- tier interaction profiling method
- Profiling Tools,tier-interaction method
- ADO.NET performance profiling
ms.assetid: 47a944c2-3098-497c-8fc7-e1f43d750bbc
caps.latest.revision: 18
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0c2c3b8d9aa9f7f6b8afc801841def0e1e2e6ec4
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42694628"
---
# <a name="collecting-tier-interaction-data"></a>Katman etkileşim verileri toplama
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [katman etkileşim verileri toplama](https://docs.microsoft.com/visualstudio/profiling/collecting-tier-interaction-data).  
  
Katman etkileşim profili oluşturma, ADO.NET Hizmetleri aracılığıyla veritabanları ile iletişim kuran çok katmanlı uygulamaların işlevlerini yürütme sürelerini hakkında ek bilgi sağlar. Verileri yalnızca zaman uyumlu işlev çağrıları için toplanır.  
  
 **Visual Studio sürümleri**  
  
 Katman etkileşimi profil oluşturma verileri, Visual Studio Ultimate, Visual Studio Premium veya Visual Studio Professional'ı kullanarak toplanabilir. Ancak, yalnızca VS Ultimate ve VS Premium katman etkileşimli profil oluşturma veri görüntülenebilir.  
  
 **Windows 8 ve Windows Server 2012**  
  
 Masaüstü uygulamalarını Windows 8 ve Windows Server 2012 uygulamalar üzerinde katman etkileşim verileri toplamak için Araçlar yöntemini kullanmanız gerekir. Windows Store uygulamaları için katman etkileşim verileri toplanamıyor. Bkz: [Windows 8 ve Windows Server 2012 uygulamalarında performans araçları](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md). Desteklenen diğer Windows sürümünde tüm profil oluşturma yöntemlerini katman etkileşim verileri içerebilir.  
  
 **Performans Sihirbazı**  
  
 Performans Sihirbazı bir hata nedeniyle, bir profil oluşturma yürütmesine katman etkileşim verileri toplama seçeneği performans Gezgini'nden eklemelisiniz. Ayrıca proje, yürütülebilir dosya veya Web performans Gezgini hedef düğüme eklemeniz gerekir.  
  
### <a name="to-add-tier-interaction-data-to-a-profiling-run-by-using-the-performance-session-property-pages"></a>Bir performans oturumu özellik sayfaları kullanarak profil oluşturma için katman etkileşim verileri ekleme  
  
1.  Performans Gezgini'nde **özellikleri** bağlam menüsünden.  
  
2.  Seçin **katman etkileşimleri** sayfasında ve ardından **Katman etkileşimi profili oluşturmayı etkinleştir** onay kutusu.  
  
3.  Performans Gezgini içinde seçin **hedefleri** düğümünü ve ardından Proje, yürütülebilir dosya veya profil oluşturmak istediğiniz web sitesi belirtin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Katman Etkileşimleri Görünümü](../profiling/tier-interactions-view.md)



