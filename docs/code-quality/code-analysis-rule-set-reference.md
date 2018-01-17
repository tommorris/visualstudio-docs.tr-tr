---
title: "Kod çözümleme kural kümesi başvurusu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: code analysis, rule sets
ms.assetid: 5874e854-e298-4d2e-bbe4-95e899d22587
caps.latest.revision: "43"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 9e132146ce1ae19e95a7e8f6974dab25be38db5b
ms.sourcegitcommit: d922eabedbeaedccecc5ca497ff12eb1f37933f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/17/2018
---
# <a name="code-analysis-rule-set-reference"></a>Kod çözümleme kural kümesi başvurusu
Yönetilen kod projeleri için Kod Analizi yapılandırdığınızda [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)], [!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)], veya [!INCLUDE[vsPro](../code-quality/includes/vspro_md.md)] yerleşik bir listesi sunulur *kural kümeleri*. Standart kural kümeleri birini ya da kullanabilir veya bir kural kümesini proje gereksinimlerinizi karşılayacak şekilde özelleştirebilirsiniz.  
  
## <a name="available-rule-sets"></a>Kullanılabilir kural kümeleri  
 Aşağıdaki tabloda, varsayılan kural kümeleri listelenmektedir:  
  
|||  
|-|-|  
|[Tüm Kurallar kural kümesi](../code-quality/all-rules-rule-set.md)|Bu kural kümesine tüm kurallar içerir. Bu kural kümesi çalıştıran çok sayıda uyarı raporlandığını neden olabilir. Bu kural tüm sorunlara ilişkin kapsamlı bir resim kodunuzu almak için kümesi kullanın. Bu, daha odaklı kural kümeleri projeleriniz için çalıştırmak en uygun olan karar vermenize yardımcı olabilir.|  
|[Yönetilen kod için Temel Doğruluk Kuralları kural kümesi](../code-quality/basic-correctness-rules-rule-set-for-managed-code.md)|Bu kurallar mantık hataları ve framework API'leri kullanımlarda yapılan ortak hataları odaklanır. Bu kural minimum önerilen kurallar tarafından bildirilen Uyarılar listesinde genişletmek için kümesi içerir.|  
|[Yönetilen kod için Temel Tasarım Yönerge Kuralları kural kümesi](../code-quality/basic-design-guideline-rules-rule-set-for-managed-code.md)|Bu kurallar, kodunuzu anlamak ve kullanmak kolay hale getirmek için en iyi yöntemler zorlamayı odaklanın. Bu kural, projenizin kitaplık kodu içeriyorsa veya kolayca Bakımı yapılabilir kodu için en iyi uygulamaları zorunlu kılmak istiyorsanız kümesi içerir.|  
|[Yönetilen kod için Genişletilmiş Doğruluk Kuralları kural kümesi](../code-quality/extended-correctness-rules-rule-set-for-managed-code.md)|Bu kurallar bildirilen mantığı ve framework kullanımı hataların en üst düzeye çıkarmak için temel doğruluk kuralları'nı genişletin. COM birlikte çalışma ve mobil uygulamalar gibi belirli senaryolara ek Vurgu yerleştirilir. Bu kural Bu senaryolardan biri, projenizin veya ek sorunlar projenizde bulmak için geçerliyse kümesi de dahil olmak üzere göz önünde bulundurun.|  
|[Yönetilen kod için Genişletilmiş Tasarım Yönerge Kuralları kural kümesi](../code-quality/extended-design-guidelines-rules-rule-set-for-managed-code.md)|Bu kurallar bildirilen kullanılabilirliğini ve bakım sorunları en üst düzeye çıkarmak için temel tasarım yönerge kuralları'nı genişletin. Adlandırma yönergeleri fazladan Vurgu yerleştirilir. Bu kural, projenizin kitaplık kodu içeriyorsa veya bakımı yapılabilir kodu yazmak için en yüksek standartları zorunlu kılmak istiyorsanız kümesi de dahil olmak üzere göz önünde bulundurun.|  
|[Yönetilen kod için Genelleştirme Kuralları kural kümesi](../code-quality/globalization-rules-rule-set-for-managed-code.md)|Bu kurallar, farklı diller, yerel ayarlar ve kültürlere kullanıldığında doğru bir şekilde görüntülenmesini uygulamanızdaki verileri engelleyen sorunları odaklanır. Bu kural, uygulamanızın yerelleştirilmiş ya da globalized kümesi içerir.|  
|[Yönetilen kod için yönetilen Minimum kurallar kural kümesi](../code-quality/managed-minimun-rules-rule-set-for-managed-code.md)|Bu kurallar, Kod Analizi en doğru olur, kodunuzda en kritik sorunlar odaklanır.  Bu kurallar numarasında küçük ve yalnızca sınırlı Visual Studio sürümlerinde çalıştırmak için tasarlanmıştır.  MinimumRecommendedRules.ruleset diğer Visual Studio sürümleriyle kullanın.|  
|[Yönetilen kod için Yönetilen Önerilen Kurallar kural kümesi](../code-quality/managed-recommended-rules-rule-set-for-managed-code.md)|Bu kurallar, olası güvenlik açıklarını, uygulama çökme (Crash) ve diğer önemli mantığı ve tasarım hataları gibi kodunuzda en kritik sorunlar odaklanır. Projeler için oluşturduğunuz herhangi bir özel kural kümesi içinde bu kural kümesi içermelidir.|  
|[Karışık Minimum Kurallar kural kümesi](../code-quality/mixed-minimum-rules-rule-set.md)|Bu kurallar, en kritik sorunlar olası güvenlik açıklarını ve uygulama çökme (Crash) dahil olmak üzere ortak dil çalışma desteği, C++ projelerine odaklanır. Ortak dil çalışma zamanı desteği, C++ projeleri için oluşturduğunuz herhangi bir özel kural kümesi içinde bu kural kümesi içermelidir.|  
|[Karışık Önerilen Kurallar kural kümesi](../code-quality/mixed-recommended-rules-rule-set.md)|Bu kurallar, en yaygın ve kritik sorunları olası güvenlik açıklarını, uygulama çökme (Crash) ve diğer önemli mantığı ve tasarım hataları gibi ortak dil çalışma desteği, C++ projelerine odaklanır. Ortak dil çalışma zamanı desteği, C++ projeleri için oluşturduğunuz herhangi bir özel kural kümesi içinde bu kural kümesi içermelidir.  Bu ruleset Visual Studio Professional edition ile ve daha yüksek yapılandırılması için tasarlanmıştır.|  
|[Yerel Minimum Kurallar kural kümesi](../code-quality/native-minimum-rules-rule-set.md)|Bu kurallar, olası güvenlik açıklarını ve uygulama çökme (Crash) dahil olmak üzere, yerel kodunuzda en kritik sorunlar odaklanır. Yerel projeleriniz için oluşturduğunuz herhangi bir özel kural kümesi içinde bu kural kümesi içermelidir.|  
|[Yerel Önerilen Kurallar kural kümesi](../code-quality/native-recommended-rules-rule-set.md)|Bu kurallar, olası güvenlik açıklarını ve uygulama çökme (Crash) dahil olmak üzere, yerel kodunuzda en kritik ve ortak sorunları odaklanır.  Yerel projeleriniz için oluşturduğunuz herhangi bir özel kural kümesi içinde bu kural kümesi içermelidir.  Bu ruleset Visual Studio Professional edition ile ve daha yüksek çalışmak üzere tasarlanmıştır.|  
|[Yönetilen kod için Güvenlik Kuralları kural kümesi](../code-quality/security-rules-rule-set-for-managed-code.md)|Bu kural kümesine tüm Microsoft Güvenlik kuralları içerir. Bu kural bildirilen olası güvenlik sorunlarını sayısı en üst düzeye çıkarmak için kümesi içerir.|
