---
title: "Belge bağlam | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: debugging [Debugging SDK], contexts
ms.assetid: 8e8b5702-5c16-4988-953d-69dd807d8b84
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: b121259f9be23d235386d7156ca8d326c5847f87
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="document-context"></a>Belge bağlamı
İçinde [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] hata ayıklama, bir **belge bağlam**:  
  
-   Bir kaynak dosyasında bir konumu temsil eder. Burada kaynak dosya bulunmayabilir diller için genellikle çalışma zamanı ortamı tarafından oluşturulan bir belge konumda bir belge bağlamı tanımlar. Örneğin, bir komut dosyası motoru komut dosyasından bir belge oluşturabilir. Daha fazla bilgi için bkz: [belge konumu](../../extensibility/debugger/document-position.md).  
  
-   Kod bağlamına karşılık gelen bir kaynak belge konumda açıklar. Sembol işleyici kodu bağlamı derleyici veya yorumlayıcı tarafından oluşturulan bilgileri kullanarak belge bağlamı eşler.  
  
-   Tarafından uygulanan bir [IDebugDocumentContext2](../../extensibility/debugger/reference/idebugdocumentcontext2.md) arabirimi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kod bağlamı](../../extensibility/debugger/code-context.md)   
 [Sembol sağlayıcısı](../../extensibility/debugger/symbol-provider.md)   
 [Sembol sağlayıcısı arabirimleri](../../extensibility/debugger/reference/symbol-provider-interfaces.md)   
 [Hata Ayıklayıcı Bağlamları](../../extensibility/debugger/debugger-contexts.md)