---
title: "Kod bağlam | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: debugging [Debugging SDK], contexts
ms.assetid: 65e4d37a-086b-426e-9394-a3534967fd59
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 92d6ed317bcf6ceead42db850ee61969409eb136
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
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
 [Hata ayıklayıcı bağlamları](../../extensibility/debugger/debugger-contexts.md)