---
title: Bağlantı noktaları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- ports
- debugging [Debugging SDK], ports
ms.assetid: 1d7f3aa7-7eff-4cab-bc53-0a566b1a9363
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: a350e0579f7e60d8a7ffc3e879d79364cfdf0317
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31099450"
---
# <a name="ports"></a>Bağlantı noktaları
Hata ayıklayıcı mimarisi bakımından bir **bağlantı noktası**:  
  
-   İşlemler kümesi için bir kapsayıcı, bir sunucu üzerinde çalışıyor. Örneğin, bir bağlantı noktası, Windows CE tabanlı bir cihaz seri kabloyu tarafından veya bir ağa bağlı olmayan-DCOM makine bağlantı temsil edebilir. Yerel bağlantı noktası olarak adlandırılan bir özel bağlantı noktasını, yerel makine üzerinde çalışan tüm işlemler içerir.  
  
-   Kendisini ad veya tanımlayıcı tanımlayabilirsiniz.  
  
-   Bağlantı noktası üzerinde çalışan tüm işlemler numaralandırır ve başlatabileceğini ve bu işlemleri sonlandırılacak.  
  
-   Tarafından temsil edilen bir [IDebugPort2](../../extensibility/debugger/reference/idebugport2.md) geçirerek oluşturulan arabirimi bir [IDebugPortRequest2](../../extensibility/debugger/reference/idebugportrequest2.md) bağımsız değişkeni [AddPort](../../extensibility/debugger/reference/idebugportsupplier2-addport.md).  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] tüm Windows tabanlı işlemler, yerel ve yönetilen işleyen varsayılan bir bağlantı noktası sağlar. Özel bir bağlantı noktası bağlantıları için Windows tabanlı olmayan dış cihazları ile uygulanmalıdır. Bu tür özel bağlantı noktaları temin etmek için özel bir bağlantı noktası tedarikçi ayrıca uygulanması gerekir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sunucuları](../../extensibility/debugger/servers-visual-studio-sdk.md)   
 [İşlemler](../../extensibility/debugger/processes.md)   
 [Hata ayıklayıcı kavramları](../../extensibility/debugger/debugger-concepts.md)   
 [IDebugPort2](../../extensibility/debugger/reference/idebugport2.md)   
 [IDebugPortRequest2](../../extensibility/debugger/reference/idebugportrequest2.md)   
 [AddPort](../../extensibility/debugger/reference/idebugportsupplier2-addport.md)