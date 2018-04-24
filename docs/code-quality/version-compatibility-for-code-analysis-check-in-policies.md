---
title: Kod Çözümleme İade İlkeleri için Sürüm Uyumluluğu
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
helpviewer_keywords:
- version compatibility, code analysis check-in policy
- check-in policies, version compatibility for code analysis
ms.assetid: 1af376e3-3be7-4445-803b-76a858567a5b
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 25e8ee0bf46840d420f5537a2ca28965522dea43
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="version-compatibility-for-code-analysis-check-in-policies"></a>Kod Çözümleme İade İlkeleri için Sürüm Uyumluluğu
Değerlendirmek ve yazar kod çözümleme iade ilkeleri farklı sürümlerini kullanan [!INCLUDE[esprtfc](../code-quality/includes/esprtfc_md.md)], nasıl farklılıkları bilmelisiniz [!INCLUDE[vstsTfsOrcasLong](../code-quality/includes/vststfsorcaslong_md.md)] ve [!INCLUDE[vstsTfsRosarioShort](../code-quality/includes/vststfsrosarioshort_md.md)] iade ilkelerini değerlendirir.

## <a name="version-compatibility-for-evaluating-check-in-policies"></a>İade ilkeleri değerlendirmek için sürüm uyumluluğu

-   Ne zaman kod çözümleme iade ilkeleri değerlendirilir içinde [!INCLUDE[vstsTfsOrcasShort](../code-quality/includes/vststfsorcasshort_md.md)], varolan herhangi bir kuralın [!INCLUDE[vstsTfsRosarioShort](../code-quality/includes/vststfsrosarioshort_md.md)] ancak içinde yok [!INCLUDE[vstsTfsOrcasShort](../code-quality/includes/vststfsorcasshort_md.md)] göz ardı edilir.

-   Ne zaman kod çözümleme iade ilkeleri değerlendirilir içinde [!INCLUDE[vstsTfsRosarioShort](../code-quality/includes/vststfsrosarioshort_md.md)], özel tüm yeni kurallar [!INCLUDE[vstsTfsOrcasShort](../code-quality/includes/vststfsorcasshort_md.md)] göz ardı edilir.

-   Kod çözümleme iade ilkesi kuralları derlemeleri belirtiyorsa [!INCLUDE[vstsTfsOrcasShort](../code-quality/includes/vststfsorcasshort_md.md)] tarafından tanınmayan derlemeleri tarafından belirtilen tüm kuralları yok sayar.

-   Kod çözümleme iade ilkesi kuralları derlemeleri belirtirse, [!INCLUDE[vstsTfsRosarioShort](../code-quality/includes/vststfsrosarioshort_md.md)] tanımıyor, bir ileti görüntülenir.

## <a name="version-compatibility-for-authoring-check-in-policies"></a>İade ilkeleri geliştirme için sürüm uyumluluğu

-   Bir kod çözümleme İade İlkesi kullanarak oluşturduysanız [!INCLUDE[vstsTfsOrcasShort](../code-quality/includes/vststfsorcasshort_md.md)] sürümü [!INCLUDE[esprtfc](../code-quality/includes/esprtfc_md.md)], kullanamazsınız [!INCLUDE[vstsTfsRosarioShort](../code-quality/includes/vststfsrosarioshort_md.md)] sürümü [!INCLUDE[esprtfc](../code-quality/includes/esprtfc_md.md)] değiştirmek için. Ve ayrıca, [!INCLUDE[vstsTfsRosarioShort](../code-quality/includes/vststfsrosarioshort_md.md)] İlkesi değerlendirilemiyor.

-   Bir kod çözümleme İade İlkesi kullanarak oluşturduysanız [!INCLUDE[esprtfc](../code-quality/includes/esprtfc_md.md)] içinde [!INCLUDE[vstsTfsRosarioShort](../code-quality/includes/vststfsrosarioshort_md.md)], kullanabileceğiniz [!INCLUDE[esprtfc](../code-quality/includes/esprtfc_md.md)] içinde [!INCLUDE[vstsTfsOrcasShort](../code-quality/includes/vststfsorcasshort_md.md)] ve ilkeyi değiştirmek için aynı zamanda göre değerlendirilebilir [!INCLUDE[vstsTfsOrcasShort](../code-quality/includes/vststfsorcasshort_md.md)]. İlkeyi kullanarak değiştirdikten sonra [!INCLUDE[esprtfc](../code-quality/includes/esprtfc_md.md)] içinde [!INCLUDE[vstsTfsOrcasShort](../code-quality/includes/vststfsorcasshort_md.md)], artık ilke kullanarak düzenleyebileceğiniz [!INCLUDE[esprtfc](../code-quality/includes/esprtfc_md.md)] içinde [!INCLUDE[vstsTfsRosarioShort](../code-quality/includes/vststfsrosarioshort_md.md)]. [!INCLUDE[vstsTfsRosarioShort](../code-quality/includes/vststfsrosarioshort_md.md)] eşleşmeyen tanımlayıcı adlar ile sorunsuz ilkeleri değerlendirebilirsiniz.

-   Her ikisi için geçerli olan kural ayarları ile bir kod çözümleme iade ilkesi oluşturmak için [!INCLUDE[vstsTfsRosarioShort](../code-quality/includes/vststfsrosarioshort_md.md)] ve [!INCLUDE[vstsTfsOrcasShort](../code-quality/includes/vststfsorcasshort_md.md)], ilkede oluşturmalısınız [!INCLUDE[vstsTfsRosarioShort](../code-quality/includes/vststfsrosarioshort_md.md)], gerekli tüm değişiklikleri yapın ve ilkeyi kaydedin. Kuralları yapılan değişiklikler yalnızca varsa [!INCLUDE[vstsTfsOrcasShort](../code-quality/includes/vststfsorcasshort_md.md)], değiştirebilir ve ilkede kaydedebilirsiniz [!INCLUDE[vstsTfsOrcasShort](../code-quality/includes/vststfsorcasshort_md.md)].

     İlkeyi kaydettikten sonra [!INCLUDE[vstsTfsOrcasShort](../code-quality/includes/vststfsorcasshort_md.md)], artık mevcut kurallar için ayarları değiştirebilirsiniz [!INCLUDE[vstsTfsRosarioShort](../code-quality/includes/vststfsrosarioshort_md.md)] yalnızca.