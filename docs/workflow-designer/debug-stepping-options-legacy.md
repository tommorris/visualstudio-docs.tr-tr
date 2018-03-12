---
title: "Hata ayıklama sürüm seçenekleri (eski) | Microsoft Docs"
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- branch stepping
- stepping, options in workflow debugging
- debugging, stepping options
- debugging workflows, stepping options
- instance stepping
ms.assetid: 3e9e3041-68c7-4f16-9bd6-da5e5144744b
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: beb4191b56bb0b2b0d80b30aa7956bc23d0cfa9d
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/12/2018
---
# <a name="debug-stepping-options-legacy"></a>Hata ayıklama sürüm seçenekleri (eski)
Bu konu, hata ayıklamak açıklar [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)] eski Windows iş akışı Tasarımcısı'nda eşzamanlı etkinlikler içeren uygulamalar. Eski kullanmak [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] ya da hedeflemek gerektiğinde [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] veya [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)].

 Ne zaman ayıkladığınız eş zamanlı yürütme sahip eski etkinlikler **ParallelActivity** veya **ConditionedActivityGroup**, kodunuzu adımı için aşağıdaki iki seçenekten birini kullanabilirsiniz .

-   **Atlama dal.** Bu mod Adımlama, adım adım ve dalı bileşik bir etkinlik gibi hata ayıklama sağlar **ParallelActivity** veya **ConditionalActivityGroup** etkinlik. Hata ayıklamak için bu seçeneği kullandığınızda, bir değişiklik denetimi diğer etkinliklerin iş akışı eşzamanlı olarak yürütülmesini nedeniyle meydana olduğunu fark etmez. Hata ayıklayıcı yalnızca adımları etkinlikleri diğer etkinlikler iş akışı içinde eşzamanlı olarak yürütülen ederken Seçili dal. Örneğin, varsayılan olarak, soldaki dalında bir **ParallelActivity** etkinliği ve ilk alt etkinliğini bir **ConditionedActivityGroup** etkinliği atlama için kullanılır. Kullanıcının diğer dal ya da alt etkinlik hata ayıklama ilgileniyorsa, açık bir kesme noktası, dal ya da alt faaliyete yerleştirilmelidir. Kesme noktası tetiklendiğinde atlama bu dalında devam eder.

-   **Atlama örneği.** Bu mod Adımlama, adım adım ilerleyin ve hata ayıklama etkinlikleri iş akışı içinde eşzamanlı olarak yürütülen olanak tanır. Bu seçenek ile bir değişiklik denetimi eşzamanlı iş akışı içinde çalıştırmak etkinlikleri yürütülürken meydana fark edeceksiniz.

 Varsayılan olarak şube sürüm seçeneğinin işaretli olduğundan ve kullanıcıların eski bir iş akışı hata ayıklama sırasında iki seçenek arasında geçiş yapabilirsiniz.

 Eski Durum makinesi iş akışları hata ayıklama sırasında seçeneği atlama örneğini seçmeniz gerekir.

## <a name="see-also"></a>Ayrıca bkz.

- [Eski İş Akışlarında Hata Ayıklama](../workflow-designer/debugging-legacy-workflows.md)
- [Nasıl Yapılır: Hata Ayıklama Adımlama Seçeneğini Değiştirme (Eski)](../workflow-designer/how-to-change-the-debug-stepping-option-legacy.md)