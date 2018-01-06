---
title: "Nasıl yapılır: yönetilen kod için tam çözüm analizini devre | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: full solution analysis
ms.assetid: 04315147-5792-47f0-8b5f-9ac8413c6a57
caps.latest.revision: "12"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-code-analysis
ms.workload: dotnet
ms.openlocfilehash: eb69b6c2e26aab36ec4dac0a664cb20b411a815a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-enable-and-disable-full-solution-analysis-for-managed-code"></a>Nasıl yapılır: etkinleştirme ve yönetilen kod için tam çözüm analizini devre dışı
> [!NOTE]
>  Bu konu yalnızca Visual Studio 2015 güncelleştirme 3 RC ve sonrası için geçerlidir.  
  
 *Tam çözüm analizini* Kod Analizi sorunlarını yalnızca dosyalarında açık Visual C# veya Visual Basic çözümünüzü veya açık ve kapalı Visual C# veya Visual Basic dosyaları çözümünüzdeki görüp görmediğinizi seçmenize olanak tanıyan bir Visual Studio özelliğidir.  
  
 Tüm dosyaları tüm sorunları yapamamasına yararlı olsa da, çözümünüzü çok büyük veya çok sayıda dosya varsa bu dikkat dağıtabilir ve Visual Studio aşağı bile yavaş olabilir.  Gösterilen sorunları sayısı sınırı ve Visual Studio performansı artırmak için tam çözüm analizini devre dışı bırakabilirsiniz. İstiyorsanız, bu özellik kolayca yeniden etkinleştirebilirsiniz.  
  
#### <a name="to-toggle-full-solution-analysis"></a>Tam çözüm analizini geçiş yapmak için  
  
1.  Visual Studio'da ana menüde seçin **Araçları** &#124; **Seçenekleri** görüntülemek için **seçenekleri** iletişim kutusu.  
  
2.  İçinde **seçenekleri** iletişim kutusunda, seçin **metin düzenleyici** &#124; **C#** veya **temel** &#124; **Gelişmiş**.  
  
3.  Seçin **tam çözüm analizini etkinleştir** onay kutusunu tam çözüm analizini etkinleştirme veya devre dışı bırakmak kutusunun işaretini kaldırın. Seçin **Tamam** tamamladığınızda düğmesine tıklayın.  
  
     ![Tam çözüm analizi onay kutusunu etkinleştirin. ] (../code-quality/media/fsa_toolsoptions.png "FSA_ToolsOptions")  
  
## <a name="results-of-enabling-and-disabling-full-solution-analysis"></a>Sonuçlarını etkinleştirme ve tam çözüm analizini devre dışı bırakma  
 Aşağıdaki ekran görüntüsünde, tam çözüm analizini etkinleştirildiğinde sonuçlarını görebilirsiniz. Tüm hataları ve Kod Analizi sorunlarını *tüm* çözüm dosyalarını, dosyalar veya açık olup bağımsız olarak görünür.  
  
 ![Tam çözüm analizini etkin. ] (../code-quality/media/fsa_enabled.png "FSA_Enabled")  
  
 Aşağıdaki ekran görüntüsünde, tam çözüm analizini devre dışı bıraktıktan sonra aynı çözümden sonuçlarını gösterir. Yalnızca hataları ve Kod Analizi sorunlarını dosyaları görünür çözümü hata listesinde açın.  
  
 ![Tam çözüm analizini devre dışı. ] (../code-quality/media/fsa_disabled.png "FSA_Disabled")  
  
## <a name="automatically-disabling-full-solution-analysis"></a>Otomatik olarak tam çözüm analizini devre dışı bırakma  
 Visual Studio algılarsa, 200MB veya daha az sistem belleği için kullanılabilir, etkinleştirildiğinde, otomatik olarak tam çözüm analizini (bazı diğer özellikler için olduğu gibi) devre dışı bırakır. Bu meydana gelirse, bu bildiren bir uyarı görüntülenir. Bir düğme, bunu yapmak istiyorsanız, tam çözüm analizini yeniden olanak tanır.  
  
 ![Uyarı metni tam çözüm analizini askıya](../code-quality/media/fsa_alert.png "FSA_Alert")  
  
## <a name="additional-details"></a>Ek ayrıntılar  
 Varsayılan olarak, tam çözüm analizini etkin için Visual Basic ve Visual C# için devre dışı.  
  
 Visual Studio güncelleştirme 3 RC, önemli ölçüde bellek kullanımını azaltır ve tam çözüm analizini etkinleştirilse bile boşta için CPU süresi azalır bir Gelişmiş kod Çözümleyicisi tanılama v2 alt içerir.