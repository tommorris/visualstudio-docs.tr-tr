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
ms.openlocfilehash: 5a38d0ad28ad01b9e106cf06127b934dedfe5bba
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
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
 [Hata ayıklayıcı bağlamları](../../extensibility/debugger/debugger-contexts.md)