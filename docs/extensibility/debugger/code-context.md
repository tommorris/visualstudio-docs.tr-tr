---
title: Kod bağlam | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], contexts
ms.assetid: 65e4d37a-086b-426e-9394-a3534967fd59
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 9a84596246ae930cdffc0265f2f2e09652661819
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31097841"
---
# <a name="code-context"></a>Kod bağlamı
İçinde [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] hata ayıklama, bir **kodu bağlamı**:  
  
-   Bir Özet konumlarından kodda hata ayıklama altyapısı (DE) bilinen sağlar. Çoğu çalışma zamanı mimari için bugün, bir kod bağlamı, adresi bir programın yönerge akış olarak düşünülebilir. Burada kod yönergeleri ile temsil edilebilir değil, nontraditional diller için başka bir şekilde bir kod bağlamı temsil edilebilir.  
  
-   Ayıklanacak program yürütme akışında geçerli konumu açıklar.  
  
-   Yalnızca bir program kesme noktasında zaman durdurdu bulunmaktadır.  
  
-   Bir ilişkili belge bağlamının vardır.  
  
-   Tarafından uygulanan bir [IDebugCodeContext2](../../extensibility/debugger/reference/idebugcodecontext2.md) arabirimi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Belge bağlamı](../../extensibility/debugger/document-context.md)   
 [Hata Ayıklayıcı Bağlamları](../../extensibility/debugger/debugger-contexts.md)