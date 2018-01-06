---
title: "İş akışları uzak bir bilgisayardan (eski) hata ayıklama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- workflows, debugging remotely
- debugging workflows, remotely
- remote debugging, workflows
- debugging, remote
ms.assetid: 44eaec8f-9959-4ae7-a374-670946f933c1
caps.latest.revision: "6"
author: ErikRe
ms.author: erikre
manager: erikre
ms.workload: multiple
ms.openlocfilehash: b4b9207702e6b4c3b93838eccfe1da15c42b5baa
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="debugging-workflows-from-a-remote-computer-legacy"></a>Hata ayıklama iş akışları uzak bir bilgisayardan (eski)
Bu konu, uzak eski hata ayıklamak açıklar [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)] eski ile oluşturulan uygulamaların [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)]. Eski kullanmak [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] uygulamanızı gerektiği zaman ya da hedeflemek [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] veya [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)].  
  
 Yüklediğinizde [!INCLUDE[vs_current_long](../misc/includes/vs_current_long_md.md)], bileşen yükleme seçeneklerden biri yüklemek için [!INCLUDE[vs_current_long](../misc/includes/vs_current_long_md.md)] için hata ayıklayıcı [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)]. Uzaktan hata ayıklama bileşenleri yükler. Bu uzaktan hata ayıklama bileşenleri uzak iş akışı hata ayıklama için hedeflediğiniz bilgisayara yüklenmesi gerekir.  
  
 Ayrıca, uzak bir bilgisayarda hata ayıklama eski iş akışının iş akışı tanımını içeren derlemenin genel derleme önbelleğinde (GAC) hata ayıklama yaptığınız yerel bilgisayarın yüklenmesi gerekir. Örneğin, bir uzak bilgisayarda bir eski bir iş akışını çalıştıran ve yerel bilgisayardan B ayıkladığınız, iş akışı tanımı b bilgisayarı GAC içinde bulunması gerekir Bu seri durumdan ve B bilgisayarında uzaktan A. bilgisayarda çalışan bir iş akışı iş akışı biçimlendirmesi görüntülemek tasarımcı sağlar Genel Derleme Önbelleği hakkında daha fazla bilgi için MSDN Kitaplığı bakın.  
  
 [!INCLUDE[wf2](../workflow-designer/includes/wf2_md.md)]Uzaktan hata ayıklama, işlevleri diğer için uzaktan hata ayıklama ile aynı [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] bileşenleri. Daha fazla bilgi için bkz: [!INCLUDE[vs_current_long](../misc/includes/vs_current_long_md.md)] uzaktan hata ayıklama MSDN Kitaplığı'nda.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eski İş Akışlarında Hata Ayıklama](../workflow-designer/debugging-legacy-workflows.md)