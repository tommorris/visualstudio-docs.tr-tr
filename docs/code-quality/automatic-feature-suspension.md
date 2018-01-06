---
title: "Otomatik özelliği askıya | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- full solution analysis
- performance
- low-memory
ms.assetid: 572c15aa-1fd0-468c-b6be-9fa50e170914
caps.latest.revision: "6"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-code-analysis
ms.workload: multiple
ms.openlocfilehash: 0bb8155f2ec1ed6815ac37f1124dfbf57cf838b2
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="automatic-feature-suspension"></a>Otomatik özelliği askıya alma
Kullanılabilir sistem belleğini 200 MB veya daha az kalırsa, Visual Studio aşağıdaki iletiyi Kod düzenleyicisinde görüntüler.  
  
 ![Uyarı metni tam çözüm analizini askıya](../code-quality/media/fsa_alert.png "FSA_Alert")  
  
 Otomatik olarak Visual Studio bellek yetersizliği algıladığında, kararlı kalmasını sağlayacak bazı gelişmiş özellikleri askıya alır. Bu gelişmiş özellik askıya uyarı görünür, Visual Studio'nun önceki gibi çalışmaya devam eder, ancak kendi performansını biraz daha düşük olacağını.  
  
 Bir yetersiz bellek durumu aşağıdakiler gerçekleşir:  
  
-   Visual C# ve Visual Basic için tam çözüm analizini devre dışı bırakılır.  
  
-   [Çöp toplama](/dotnet/standard/garbage-collection/index) Visual C# ve Visual Basic (GC) düşük gecikme süreli modunu devre dışı bırakılır.  
  
-   Visual Studio önbellekleri temizlenir.  
  
## <a name="improve-visual-studio-performance"></a>Visual Studio performansı  
 İpuçları ve püf noktaları büyük çözümlerde veya düşük bellek koşullarla ilgilenirken Visual Studio performansını artırmak nasıl için bkz: [büyük çözümler için başarım düşünceleri](https://github.com/dotnet/roslyn/wiki/Performance-considerations-for-large-solutions).  
  
## <a name="full-solution-analysis-suspended"></a>Tam çözüm analizini askıya alındı  
 Varsayılan olarak, tam çözüm analizini etkin için Visual Basic ve Visual C# için devre dışı. Ancak, bir yetersiz bellek durumu tam çözüm analizini otomatik olarak hem Visual Basic ve Visual C# için Seçenekler iletişim kutusu ayarlarına bakılmaksızın devre dışıdır. Ancak, tam çözüm analizini seçerek yeniden etkinleştirebilirsiniz **yeniden etkinleştirmek** zaman, seçerek göründüğü çubuğu bilgisi düğmesini **tam çözüm analizini etkinleştir** onay kutusunu Seçenekleri iletişim kutusunda veya Visual Studio'yu yeniden başlatmayı. Seçenekler iletişim kutusu, her zaman geçerli tam çözümü çözümleme ayarlarını gösterir. Daha fazla bilgi için bkz: [nasıl yapılır: devre dışı tam çözüm analizini etkinleştirme ve](../code-quality/how-to-enable-and-disable-full-solution-analysis-for-managed-code.md).  
  
## <a name="gc-low-latency-disabled"></a>GC düşük devre dışı Gecikmeli  
 GC düşük gecikme süreli modunu yeniden etkinleştirmek için Visual Studio'yu yeniden başlatın.  Yazdıklarınızı GC işlemleri engellemediğinden emin olun yazmakta olduğunuz zaman varsayılan olarak, Visual Studio GC düşük gecikme süreli modu sağlar. Ancak, otomatik askıya uyarı görüntüleyecek şekilde Visual Studio bellek yetersizliği neden olursa, GC düşük gecikme süreli modu bu oturum için devre dışı bırakılır. Visual Studio'yu yeniden başlatmayı varsayılan GC davranışı yeniden etkinleştirir. Daha fazla bilgi için bkz: [GCLatencyMode numaralandırma](http://msdn.microsoft.com/Library/057757a5-cd62-4d13-8a40-370eb7f47c87).  
  
## <a name="visual-studio-caches-flushed"></a>Visual Studio önbellekleri temizlendi  
 Tüm Visual Studio önbellekleri hemen boşaltılıp, ancak geçerli geliştirme oturumunuz devam veya Visual Studio yeniden başlatırsanız yeniden başlar. Temizlenen önbellekleri önbellekler için aşağıdaki özellikleri içerir.  
  
-   Tüm başvuruları Bul  
  
-   Gidin  
  
-   Using ekleme  
  
 Ayrıca, iç Visual Studio işlemleri için kullanılan önbellekleri de temizlenir.  
  
> [!NOTE]
>  Otomatik özelliği askıya uyarı çözüm başına temelinde, bir oturum başına temelinde yalnızca bir kez gerçekleşir. Bu, Visual Basic'ten Visual C# (veya tersi) geçin ve başka bir bellek yetersizliği çalıştırırsanız, başka bir otomatik özelliği askıya uyarı büyük olasılıkla alabilirsiniz anlamına gelir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: etkinleştirme ve devre dışı tam çözüm analizini](../code-quality/how-to-enable-and-disable-full-solution-analysis-for-managed-code.md)   
 [Çöp toplamanın temelleri](/dotnet/standard/garbage-collection/fundamentals)   
 [Büyük çözümlerde için başarım düşünceleri](https://github.com/dotnet/roslyn/wiki/Performance-considerations-for-large-solutions)