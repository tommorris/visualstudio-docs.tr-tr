---
title: "Nasıl yapılır: yönetilen kod projesi için kod analizini yapılandırma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.codeanalysis.propertypages.csvb
helpviewer_keywords:
- code analysis, selecting rule sets
- code analysis, rule sets
ms.assetid: 618f6ff3-db0e-46cb-b08d-dfa35e62c9e7
caps.latest.revision: "33"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: d62957a75c844d736a1168010616d5cf2c795bee
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-configure-code-analysis-for-a-managed-code-project"></a>Nasıl yapılır: Yönetilen Kod Projesi İçin Kod Çözümlemesini Yapılandırma
İçinde [!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)], [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)] ve [!INCLUDE[vsPro](../code-quality/includes/vspro_md.md)], Kod Analizi listesinden seçebilirsiniz *kural kümeleri* yönetilen kod projesi için uygulanacak. Varsayılan kural Microsoft Minimum önerilen kurallar kümesidir. Başka bir kural bir proje veya bir çözümdeki tüm projeleri kümesi uygulayabilirsiniz.  
  
> [!NOTE]
>  Bir kural kümesini ASP.NET Web uygulamaları için yapılandırma hakkında daha fazla bilgi için bkz: [nasıl yapılır: ASP.NET Web uygulaması için Kod Analizi yapılandırma](../code-quality/how-to-configure-code-analysis-for-an-aspnet-web-application.md).  
  
### <a name="to-configure-a-rule-set-for-a-net-framework-project"></a>Bir kural yapılandırmak için .NET Framework projesi için ayarlayın  
  
1.  İçinde **Çözüm Gezgini**, projeye tıklayın.  
  
2.  Üzerinde **Çözümle** menüsünde tıklatın **yapılandırmak için Kod Analizi** *ProjectName*.  
  
3.  İçinde **yapılandırma** ve **Platform** listeler, derleme yapılandırmasını ve hedef platformu'i tıklatın.  
  
4.  Kod çözümleme proje seçilen yapılandırma kullanılarak oluşturulmuştur her zaman çalıştırmak için seçin **etkinleştirme kodu (tanımlar CODE_ANALYSIS sabiti) çözümleme yapı** onay kutusu. Ayrıca Kod Analizi el ile açarak çalıştırabilirsiniz **Çözümle** menü ve tıklayarak **çalıştırmak kod çözümleme** *ProjectName*.  
  
5.  Varsayılan olarak, Kod Analizi uyarıları dış araçları tarafından otomatik olarak oluşturulan kodundan bildirmiyor. Oluşturulan kodundan uyarıları görüntülemek için temizleyin **bastırmak oluşturulan kod sonuçlarından** onay kutusu.  
  
    > [!NOTE]
    >  Hataları ve Uyarıları formlar ve şablonlar görüntülendiğinde bu seçenek kod çözümleme hataları ve Uyarıları oluşturulan kodundan engelleme. Hem görüntülemek ve bir form veya şablon için kaynak kodunu sağlayabilirsiniz.  
  
6.  İçinde **bu kural kümesini çalıştırmak** listesinde, aşağıdakilerden birini yapın:  
  
    -   Kullanmak istediğiniz kuralı Ayarla'yı tıklatın.  
  
    -   Tıklatın  **\<Gözat... >** var olan bir özel kural kümesini belirlemek için listede değil.  
  
    -   Özel bir kural kümesini tanımlar.  
  
         Daha fazla bilgi için bkz: [özel kural kümeleri oluşturma](../code-quality/creating-custom-code-analysis-rule-sets.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İzlenecek yol: Yapılandırma ve özel bir kural kümesini kullanma](../code-quality/walkthrough-configuring-and-using-a-custom-rule-set.md)