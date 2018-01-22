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
ms.workload: cplusplus
ms.openlocfilehash: 28a5e13c2c56c7ecdb65efdfc1bd0b3c6eb47bfc
ms.sourcegitcommit: bd16e764134c436d2d2f46490f51234d5246ee50
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/22/2018
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
 Kod çözümleme aracı bir adım olarak çalıştırmak için tümleşik yapı sistem özelliklerini kullanabilirsiniz [!INCLUDE[esprtfs](../code-quality/includes/esprtfs_md.md)] derleme işlemi. Daha fazla bilgi için bkz: [derleme ve sürüm](/vsts/build-release/index).  
  
## <a name="command-line-support"></a>Komut satırı desteği  
 Geliştirme ortamında tam tümleştirme yanı sıra da komut satırından çözümleme aracı geliştiriciler, aşağıdaki örnekte gösterildiği gibi kullanabilirsiniz:  
  
 `C:\>cl /analyze Sample.cpp`