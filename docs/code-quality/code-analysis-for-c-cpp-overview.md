---
title: "Kod çözümleme için C/C++ genel bakış | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- annotations, code analysis
- build integration, code analysis
- C/C++ code analysis
- IDE, code analysis
- pragma directive, code analysis
- code analysis, C/C++
- code analysis tool
- command line, code analysis
- C++, code analysis
- check-in policies, code analysis
- '#pragma directives, code analysis'
- C, code analysis
ms.assetid: 81f0c9e8-f471-4de5-aac4-99db336a8809
caps.latest.revision: "25"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: f1634250d97e83b21cccd3ada90933fc0806d35f
ms.sourcegitcommit: f0ddee934713ea9126fa107018a57a94a05eafd3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/12/2017
---
# <a name="code-analysis-for-cc-overview"></a>C/C++ İçin Kod Çözümlemesine Genel Bakış
C/C++ kod analizi aracı geliştiricilerin kendi C/C++ kaynak kodu olası kusurlarını hakkında bilgi sağlar. Bellek ve kaynak sızıntılarını ve null işaretçiye veya aracı tarafından raporlanan genel kodlama hatalarını arabellek taşmaları, başlatılmamış bellek içerir.  
  
## <a name="ide-integrated-development-environment-integration"></a>IDE (tümleşik geliştirme ortamı) tümleştirme  
 Analiz aracı kullanmak geliştiricileri için doğal yapmak için tam olarak içinde tümleşik [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] IDE. Oluşturma işlemi sırasında kaynak kodunu oluşturulan tüm uyarılar hata listesinde görünür. Uyarı neden kaynak koduna gidebilir ve neden ve sorunun olası çözümleri hakkında ek bilgileri görüntüleyebilirsiniz.  
  
## <a name="pragma-support"></a>#pragma desteği  
 Geliştiricileri kullanabilir `#pragma` uyarıları hata ele; etkinleştirmek veya uyarıları devre dışı bırakmak ve tek tek satırlık bir kod için uyarıları bastırma yönergesi. Daha fazla bilgi için bkz: [nasıl yapılır: C/C++ projeleri için Kod Analizi Özellikleri Ayarla ](how-to-set-code-analysis-properties-for-c-cpp-projects.md).  
  
## <a name="annotation-support"></a>Ek açıklama desteği  
 Ek açıklamalar, Kod Analizi doğruluğunu geliştirin. Ek açıklamalar işlev parametreleri öncesi ve sonrası koşullar hakkında ek bilgiler sağlar ve dönüş türleri. Daha fazla bilgi için bkz: [nasıl yapılır: ek kod __analysis_assume kullanarak bilgilerini belirt](../code-quality/how-to-specify-additional-code-information-by-using-analysis-assume.md)  
  
## <a name="run-analysis-tool-as-part-of-check-in-policy"></a>İade ilkesini bir parçası olarak analiz aracı  
 Tüm kaynak kodu iadeler belirli ilkeleri karşılamak gerektiren isteyebilirsiniz. Özellikle, analiz en güncel bir adım olarak çalıştırıldığı emin olmak istersiniz. Bir kod çözümleme iade ilkesi etkinleştirme hakkında daha fazla bilgi için bkz: [oluşturma ve kod çözümleme iade ilkelerini kullanma](../code-quality/creating-and-using-code-analysis-check-in-policies.md)  
  
## <a name="team-build-integration"></a>Team derleme tümleştirmesi  
 Kod çözümleme aracı bir adım olarak çalıştırmak için tümleşik yapı sistem özelliklerini kullanabilirsiniz [!INCLUDE[esprtfs](../code-quality/includes/esprtfs_md.md)] derleme işlemi. Daha fazla bilgi için bkz: [uygulamayı derlediğinizde](http://msdn.microsoft.com/Library/a971b0f9-7c28-479d-a37b-8fd7e27ef692).  
  
## <a name="command-line-support"></a>Komut satırı desteği  
 Geliştirme ortamında tam tümleştirme yanı sıra da komut satırından çözümleme aracı geliştiriciler, aşağıdaki örnekte gösterildiği gibi kullanabilirsiniz:  
  
 `C:\>cl /analyze Sample.cpp`