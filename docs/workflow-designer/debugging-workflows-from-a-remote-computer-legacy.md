---
title: İş akışları uzak bir bilgisayardan (eski) hata ayıklama | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- workflows, debugging remotely
- debugging workflows, remotely
- remote debugging, workflows
- debugging, remote
ms.assetid: 44eaec8f-9959-4ae7-a374-670946f933c1
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e6a3058d61d2aff0369fd52e1f03726a91a2267c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="debugging-workflows-from-a-remote-computer-legacy"></a>Hata ayıklama iş akışları uzak bir bilgisayardan (eski)
Bu konu, uzak eski hata ayıklamak açıklar [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)] eski Windows iş akışı Tasarımcısı ile oluşturulan uygulamaların. Eski kullanmak [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] uygulamanızı gerektiği zaman ya da hedeflemek [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] veya [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)].

 Yüklediğinizde [!INCLUDE[vs_current_long](../misc/includes/vs_current_long_md.md)], bileşen yükleme seçeneklerden biri yüklemek için [!INCLUDE[vs_current_long](../misc/includes/vs_current_long_md.md)] için hata ayıklayıcı [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)]. Uzaktan hata ayıklama bileşenleri yükler. Bu uzaktan hata ayıklama bileşenleri uzak iş akışı hata ayıklama için hedeflediğiniz bilgisayara yüklenmesi gerekir.

 Ayrıca, uzak bir bilgisayarda hata ayıklama eski iş akışının iş akışı tanımını içeren derlemenin genel derleme önbelleğinde (GAC) hata ayıklama yaptığınız yerel bilgisayarın yüklenmesi gerekir. Örneğin, bir uzak bilgisayarda bir eski bir iş akışını çalıştıran ve yerel bilgisayardan B ayıkladığınız, iş akışı tanımı b bilgisayarı GAC içinde bulunması gerekir Bu seri durumdan ve B bilgisayarında uzaktan A. bilgisayarda çalışan bir iş akışı iş akışı biçimlendirmesi görüntülemek tasarımcı sağlar Genel Derleme Önbelleği hakkında daha fazla bilgi için MSDN Kitaplığı bakın.

 [!INCLUDE[wf2](../workflow-designer/includes/wf2_md.md)] Uzaktan hata ayıklama, işlevleri diğer için uzaktan hata ayıklama ile aynı [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] bileşenleri. Daha fazla bilgi için bkz: [!INCLUDE[vs_current_long](../misc/includes/vs_current_long_md.md)] uzaktan hata ayıklama MSDN Kitaplığı'nda.

## <a name="see-also"></a>Ayrıca bkz.

- [Eski İş Akışlarında Hata Ayıklama](../workflow-designer/debugging-legacy-workflows.md)