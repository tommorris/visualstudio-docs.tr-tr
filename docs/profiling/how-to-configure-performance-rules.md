---
title: "Nasıl yapılır: performans kurallarını yapılandırma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.performance.ruleseditor
ms.assetid: a148b468-b849-4858-880a-808a6b47e596
caps.latest.revision: "14"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2b1b5ac88e920a2bf684075bd89c7d1ddbec6904
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-configure-performance-rules"></a>Nasıl yapılır: performans kurallarını yapılandırma
Th Visual Studio profil oluşturma araçları için performans uyarıları program yürütme yavaşlatabilir profili uygulamasında sorunları gösterir. Uyarılar, daha kullanışlı verileri toplamak için koleksiyon yöntemleri değiştirmeniz gerekebilir de belirtebilirsiniz. Performans uyarıları bir profil oluşturma oturumu otomatik olarak oluşturulur ve görüntülenir **hata listesi** bir profil oluşturma veri dosyası açıldığında penceresi [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)]. Belirli uyarılar ilgilendiğiniz ve bazı uyarılar yanlış olarak yükseltilmiş senaryoları için geçerli olmayabilir. Performans uyarıları göstermek veya belirli uyarıları gizlemek için yapılandırabilirsiniz.  
  
### <a name="to-configure-profiler-performance-warnings"></a>Profil Oluşturucu performans uyarıları yapılandırmak için  
  
1.  Üzerinde **Araçları** menüsünde tıklatın **seçenekleri**.  
  
2.  Genişletme **performans araçları**ve ardından **kuralları**.  
  
3.  Etkinleştirmek veya devre dışı bir uyarı için seçin veya uyarı yanındaki onay kutusunu temizleyin **kimliği** ve adı.  
  
4.  Bir kural hanedan arasındaki düzeyini belirtmek için tıklatın **eylem** hücre yanındaki kuralı ve uyarı düzeyi'ye tıklayın.  
  
    -   **Devre dışı** -(Bu, kural kimliği yanındaki onay kutusunu temizleyerek ile aynı) kuralı devre dışı bırakır.  
  
    -   **Uyarı** -görüntüler kural bir uyarı olarak.  
  
    -   **Hata** - oluşturma yürütmesi durdurur ve kural hata olarak görüntüler.  
  
    -   **Bilgi** -görüntüler kural yalnızca bilgi olarak.