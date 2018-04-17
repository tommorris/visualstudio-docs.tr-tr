---
title: 'Nasıl yapılır: hata ayıklama atlama seçeneği (eski) değiştirme | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- branch stepping
- debugging, stepping options
- debugging workflows, stepping options
- stepping, changing options
- instance stepping
ms.assetid: aedc06af-d58a-44d6-aee4-f397f1f923a0
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: aedb8e738dc2e6ca2b066dd9a2cd42e332bbd8be
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-change-the-debug-stepping-option-legacy"></a>Nasıl yapılır: hata ayıklama atlama seçeneği (eski) değiştirme
Bu konu, hata ayıklama sürüm seçeneğini değiştirmek açıklar [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)] eş zamanlı eylemleri içeren uygulamalar eski Windows iş akışı Tasarımcısı'nda. Eski kullanmak [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] ya da hedeflemek gerektiğinde [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] veya [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)].

 Ne zaman ayıkladığınız eş zamanlı yürütme sahip eski etkinlikler **ParallelActivity** veya **ConditionedActivityGroup**, kodunuzun içinde ilerleyebilir için iki seçenekten birini kullanabilirsiniz.

 Hata ayıklama seçeneği eski iş akışı projenizdeki atlama değiştirmek için aşağıdaki adımları izleyin.

## <a name="procedures"></a>Yordamlar

#### <a name="to-change-the-debug-stepping-option"></a>Hata ayıklama sürüm seçeneği değiştirmek için

1.  Visual Studio'yu başlatın.

2.  Eşzamanlı etkinlikler kullanır ve ya da hedefleyen yeni bir proje oluşturun veya varolan bir eski iş akışı projesinde açın [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] veya [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)].

3.  Üzerinde **iş akışı** eski menüde [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)], işaret **hata ayıklama**, üzerine gelin ve ardından **atlama seçenekleri**.

4.  Şunlardan birini seçin **örneği** veya **şube**.

## <a name="see-also"></a>Ayrıca bkz.

- [Eski İş Akışlarında Hata Ayıklama](../workflow-designer/debugging-legacy-workflows.md)
- [Hata Ayıklama Adımlama Seçenekleri (Eski)](../workflow-designer/debug-stepping-options-legacy.md)