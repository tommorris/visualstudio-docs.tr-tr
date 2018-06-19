---
title: C/C++ İçin Kod Çözümlemesine Genel Bakış
ms.date: 04/28/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
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
author: mikeblome
ms.author: mblome
manager: wpickett
ms.workload:
- cplusplus
ms.openlocfilehash: ea576ba794350e6cee6b20f8ef9adb62f82a9c51
ms.sourcegitcommit: 928885ace538bef5b25961358d4f166d648f196a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/27/2018
ms.locfileid: "32031572"
---
# <a name="code-analysis-for-cc-overview"></a>C/C++ genel bakış için Kod Analizi

C/C++ kod analizi aracı olası kusurlarını C/C++ kaynak kodu hakkında bilgi sağlar. Bellek ve kaynak sızıntılarını ve null işaretçiye veya aracı tarafından raporlanan genel kodlama hatalarını arabellek taşmaları, başlatılmamış bellek içerir. Aracı ayrıca denetimleri karşı çalıştırabilirsiniz [C++ çekirdek yönergeleri](http://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md).

## <a name="ide-integrated-development-environment-integration"></a>IDE (tümleşik geliştirme ortamı) tümleştirme

Kod çözümleme aracı, Visual Studio IDE içinde tam olarak tümleşiktir.

Oluşturma işlemi sırasında kaynak kodunu oluşturulan tüm uyarılar hata listesinde görünür. Uyarı neden kaynak koduna gidebilir ve neden ve sorunun olası çözümleri hakkında ek bilgileri görüntüleyebilirsiniz.

## <a name="command-line-support"></a>Komut satırı desteği

Komut satırından çözümleme aracı, aşağıdaki örnekte gösterildiği gibi de kullanabilirsiniz:

```cmd
C:\>cl /analyze Sample.cpp
```

**Visual Studio 2017 15.7 ve sonraki sürümleri** CMake dahil olmak üzere herhangi bir yapı sistemiyle komut satırından aracını çalıştırabilirsiniz.

## <a name="pragma-support"></a>#pragma desteği

Kullanabileceğiniz `#pragma` uyarıları hata ele; etkinleştirmek veya uyarıları devre dışı bırakmak ve tek tek satırlık bir kod için uyarıları bastırma yönergesi. Daha fazla bilgi için bkz: [nasıl yapılır: C/C++ projeleri için Kod Analizi Özellikleri Ayarla](how-to-set-code-analysis-properties-for-c-cpp-projects.md).

## <a name="annotation-support"></a>Ek açıklama desteği

Ek açıklamalar, Kod Analizi doğruluğunu geliştirin. Ek açıklamalar işlev parametreleri öncesi ve sonrası koşullar hakkında ek bilgiler sağlar ve dönüş türleri. Daha fazla bilgi için bkz: [nasıl yapılır: ek kod __analysis_assume kullanarak bilgilerini belirt](../code-quality/how-to-specify-additional-code-information-by-using-analysis-assume.md)

## <a name="run-analysis-tool-as-part-of-check-in-policy"></a>İade ilkesini bir parçası olarak analiz aracı

Tüm kaynak kodu iadeler belirli ilkeleri karşılamak gerektiren isteyebilirsiniz. Özellikle, analiz en güncel bir adım olarak çalıştırıldığı emin olmak istersiniz. Bir kod çözümleme iade ilkesi etkinleştirme hakkında daha fazla bilgi için bkz: [oluşturma ve kod çözümleme iade ilkelerini kullanma](../code-quality/creating-and-using-code-analysis-check-in-policies.md)

## <a name="team-build-integration"></a>Team derleme tümleştirmesi

Kod çözümleme aracı bir adım olarak çalıştırmak için tümleşik yapı sistem özelliklerini kullanabilirsiniz [!INCLUDE[esprtfs](../code-quality/includes/esprtfs_md.md)] derleme işlemi. Daha fazla bilgi için bkz: [derleme ve sürüm](/vsts/build-release/index).

## <a name="see-also"></a>Ayrıca bkz.

- [Hızlı Başlangıç: C/C++ için Kod Analizi](quick-start-code-analysis-for-c-cpp.md)
- [İzlenecek yol: Kusurları için C/C++ kod çözümleme](walkthrough-analyzing-c-cpp-code-for-defects.md)
- [C/C++ İçin Kod Analizi Uyarıları](code-analysis-for-c-cpp-warnings.md)
- [C++ Temel Yönergeleri denetleyicilerini kullanma](using-the-cpp-core-guidelines-checkers.md)
- [C++ çekirdek yönergeleri denetleyicisi başvurusu](code-analysis-for-cpp-corecheck.md)
- [Çalıştırılacak C++ Kurallarını Belirtmek için Kural Kümeleri Kullanma](using-rule-sets-to-specify-the-cpp-rules-to-run.md)
- [Kod çözümleme araçları kullanarak sürücü kalitesini çözümleme](/windows-hardware/drivers/develop/analyzing-driver-quality-by-using-code-analysis-tools)
- [Sürücüleri uyarılar için Kod Analizi](/windows-hardware/drivers/devtest/prefast-for-drivers-warnings)
