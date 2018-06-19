---
title: Bağlantı noktası Üreticiler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- port suppliers
- debugging [Debugging SDK], port suppliers
ms.assetid: a8f3db96-1a13-4e93-9ef6-0861880369e0
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 1f1ba09c1802bdeb1c6a402e95a6de408b277532
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31099076"
---
# <a name="port-suppliers"></a>Bağlantı noktası Üreticiler
Hata ayıklayıcı mimarisi bakımından bir **bağlantı noktası tedarikçi**:  
  
-   Bir sunucu tarafından bulunan ve bu sunucuya istek bağlantı noktaları sağlar.  
  
-   Ekleyebilir ve bağlantı noktalarını içeren sunucudan kaldırın.  
  
-   Sunucuya sağlanan tüm bağlantı noktaları sıralayabilirsiniz.  
  
-   Tarafından temsil edilen bir [IDebugPortSupplier2](../../extensibility/debugger/reference/idebugportsupplier2.md) Visual Studio ile kayıt defteri aracılığıyla kayıtlı arabirimi. Bu arabirim çağırarak elde edilebilir [GetPortSupplier](../../extensibility/debugger/reference/idebugcoreserver2-getportsupplier.md).  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Varsayılan bağlantı noktası Tedarikçi ve varsayılan bir bağlantı noktası sağlar. Özel bir bağlantı noktası uygulanması gerekirse, özel bir bağlantı noktası tedarikçi Ayrıca bu özel bağlantı noktalarını sağlamak için uygulanması gerekir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sunucuları](../../extensibility/debugger/servers-visual-studio-sdk.md)   
 [Bağlantı noktaları](../../extensibility/debugger/ports.md)   
 [Hata ayıklayıcı kavramları](../../extensibility/debugger/debugger-concepts.md)   
 [IDebugPortSupplier2](../../extensibility/debugger/reference/idebugportsupplier2.md)   
 [GetPortSupplier](../../extensibility/debugger/reference/idebugcoreserver2-getportsupplier.md)