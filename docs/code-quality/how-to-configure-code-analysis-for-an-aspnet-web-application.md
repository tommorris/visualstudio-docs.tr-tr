---
title: "Nasıl yapılır: bir ASP.NET Web uygulaması için kod analizini yapılandırma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.codeanalysis.propertypages.asp
ms.assetid: b3000b31-fd9d-489e-81a2-a4bee49453ba
caps.latest.revision: "13"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: dbc2ba8f78cc8f38bce62adbd3d91604875bffa3
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-configure-code-analysis-for-an-aspnet-web-application"></a>Nasıl yapılır: Bir ASP.NET Web Uygulaması İçin Kod Çözümlemesini Yapılandırma
İçinde [!INCLUDE[vsPreShort](../code-quality/includes/vspreshort_md.md)] ve [!INCLUDE[vsUltShort](../code-quality/includes/vsultshort_md.md)] Kod Analizi listesinden seçebilirsiniz *kural kümeleri* uygulamak için [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] Web uygulaması. Varsayılan kural Microsoft Mininimum önerilen kurallar kümesidir. Başka bir kural Web sitesine uygulamak için kümesini seçebilirsiniz.  
  
### <a name="to-configure-a-rule-set-for-an-aspnet-page-framework-project"></a>Bir kural yapılandırmak için bir ASP.NET sayfası Framework projesi için ayarlayın  
  
1.  Web sitesini seçin **Çözüm Gezgini**.  
  
2.  Üzerinde **Çözümle** menüsünde tıklatın **Web sitesi için Kod Analizi yapılandırma**.  
  
3.  Çözüm seçili birden çok proje çözümü vardır, derleme, yapılandırma ve hedef işletim sisteminden seçin ve **yapılandırma** ve **Platform** listeler.  
  
4.  Çözümdeki her projeye için tıklayarak **kural kümesi** sütun ve kuralın adını ayarlayın çalıştırmak için tıklatın.  
  
5.  Varsayılan olarak, Çözümdeki tüm projeleri üzerinde kod analizi çalıştırılır. Devre dışı bırakmak veya belirli bir projede için Kod Analizi etkinleştirmek için şu adımları izleyin:  
  
    1.  Proje adına sağ tıklayın ve ardından Özellikler'i tıklatın.  
  
    2.  Denetleyin veya temizleyin **etkinleştirmek Kod Analizi** onay kutusu. Ayrıca Kod Analizi el ile seçerek çalıştırabilirsiniz **çalıştırmak Kod Analizi Web sitesinde** gelen **Çözümle** menüsü.  
  
6.  İçinde **bu kural kümesini çalıştırmak** aşağı açılan listesinde, aşağıdaki adımları izleyin:  
  
    -   Kullanmak istediğiniz kural kümesini seçin.  
  
    -   Seçin  **\<Gözat >** var olan bir özel kural kümesini belirlemek için listede değil.  
  
    -   Özel bir kural kümesini tanımlar. Daha fazla bilgi için bkz: [özel kural kümeleri oluşturma](../code-quality/creating-custom-code-analysis-rule-sets.md).