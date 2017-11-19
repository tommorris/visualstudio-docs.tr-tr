---
title: "Nasıl yapılır: Windows sayaç verileri toplama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.performance.property.syscounter
- vs.performance.property.wincounter
helpviewer_keywords:
- windows counters
- performance tools, using windows counters
- profiling tools, using windows counters
ms.assetid: db4fbac2-bea5-4558-aa8b-160fcccf4b33
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d5b16cf6260932f11c9d4fd33f2eb5662327355a
ms.sourcegitcommit: 26419ab0cccdc30d279c32d6a841758cfa903806
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/11/2017
---
# <a name="how-to-collect-windows-counter-data"></a>Nasıl yapılır: Windows Sayaç Verileri Toplama
Windows sayaçlarını profil oluşturma sırasında belirlenen aralıklarla toplanabilir sistem performans sayaçları ' dir. Profil oluşturma araçları rapor işaretleri görünümünde bir satırın etiketli **otomatik işaret** her toplama aralığı için. Satır bu aralıkta performans sayacı değerlerini tanımlamak sütunları içerir. İki belirli işaretleri arasında bir süre için analiz kısıtlamak için işaretleri, sağ tıklatın ve ardından seçin **Filtresi tarafından** ->  **işaretleri** kısayol menüsünden.  
  
 **Gereksinimler**  
  
-   [!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)], [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)], [!INCLUDE[vsPro](../code-quality/includes/vspro_md.md)]  
  
> [!NOTE]
>  Gelişmiş güvenlik özellikleri Windows 8 ve Windows Server 2012 Visual Studio profil oluşturucu bu platformlarda toplar şekilde önemli değişiklikler gerekmiştir. UWP uygulamalar için yeni koleksiyon teknikler de gerekir. Bkz: [Windows 8 ve Windows Server 2012 uygulamaların performans araçları](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).  
  
### <a name="to-collect-windows-counter-data"></a>Windows sayaç verileri toplamak için  
  
1.  Windows sayaçları yapılandırmak ve seçmek istediğiniz oturumu performans Gezgini'nde sağ **özellikleri**.  
  
2.  İçinde **özellik sayfaları**, tıklatın **Windows sayaçları**.  
  
3.  Seçin **Windows sayaçlarını Topla** onay kutusu.  
  
4.  İçinde **toplama aralığı (milisaniye)** metin kutusuna, bir zaman aralığı yazın.  
  
5.  Bir kategori seçin **sayacı kategorisi** aşağı açılan liste.  
  
6.  Bir örnekten seçin **örneği** aşağı açılan liste.  
  
7.  Uygulamanıza profil, kullanmak istediğiniz sayaçları seçin.  
  
8.  Tıklatın **uygulayın.**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Performans oturumlarını yapılandırma](../profiling/configuring-performance-sessions.md)   
 [Performans oturum özellikleri](../profiling/performance-session-properties.md)   
 [CPU ve Windows sayaçları](../profiling/cpu-and-windows-counters.md)