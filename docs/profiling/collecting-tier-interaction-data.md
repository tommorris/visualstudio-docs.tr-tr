---
title: "Katman etkileşim verileri toplama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.performance.property.tierinteraction
helpviewer_keywords:
- Profiling Tools,ADO.NET profiling
- tier interaction profiling method
- Profiling Tools,tier-interaction method
- ADO.NET performance profiling
ms.assetid: 47a944c2-3098-497c-8fc7-e1f43d750bbc
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: c12d279541e60353a9e6e4354a16870713498b66
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="collecting-tier-interaction-data"></a>Katman etkileşim verileri toplama
Katman etkileşim profil veritabanları ADO.NET Hizmetleri aracılığıyla iletişim çok katmanlı uygulamaların işlevlerini yürütme sürelerinin hakkında ek bilgi sağlar. Verileri yalnızca zaman uyumlu işlev çağrıları için toplanır.  
  
 **Visual Studio sürümleri**  
  
 Visual Studio Ultimate, Visual Studio Premium ya da Visual Studio Professional kullanarak katman etkileşim profil oluşturma verileri toplanabilir. Ancak, yalnızca VS Ultimate ve VS Premium katman etkileşimli profil oluşturma verilerini görüntülenebilir.  
  
 **Windows 8 ve Windows Server 2012**  
  
 Masaüstü uygulamaları Windows 8 ve Windows Server 2012 uygulamalar katman etkileşim verileri toplamak için izleme metodunu kullanmanız gerekir. UWP uygulamalar için katman etkileşim verileri toplayamazsınız. Bkz: [Windows 8 ve Windows Server 2012 uygulamaların performans araçları](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md). Desteklenen diğer Windows sürümünde tüm profil oluşturma yöntemlerini katman etkileşim verileri içerebilir.  
  
 **Performans Sihirbazı**  
  
 Performans Sihirbazı bir hata nedeniyle, katman etkileşim verileri toplama seçeneğini profil çalışmaya performans Gezgini'nden eklemeniz gerekir. Proje, yürütülebilir dosya veya Web sitesi performans Gezgini hedef düğüme eklemelisiniz.  
  
### <a name="to-add-tier-interaction-data-to-a-profiling-run-by-using-the-performance-session-property-pages"></a>Bir performans oturumu özellik sayfalarını kullanarak çalıştırmak profil için katman etkileşim verileri eklemek için  
  
1.  Performans Gezgini seçin **özellikleri** ve bağlam menüsünden.  
  
2.  Seçin **katman etkileşimleri** sayfasında ve ardından denetleyin **katman etkileşim profil etkinleştirmek** onay kutusu.  
  
3.  Performans Gezgini içinde seçin **hedefleri** düğümü, proje, yürütülebilir dosya veya profil oluşturmayı istediğiniz web sitesi belirtin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Katman Etkileşimleri Görünümü](../profiling/tier-interactions-view.md)