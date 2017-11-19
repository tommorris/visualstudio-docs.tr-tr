---
title: "Bağlantı noktaları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ports
- debugging [Debugging SDK], ports
ms.assetid: 1d7f3aa7-7eff-4cab-bc53-0a566b1a9363
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 926f5e9a80a91da57d843c11175865f78775e38c
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="ports"></a>Bağlantı noktaları
Hata ayıklayıcı mimarisi bakımından bir **bağlantı noktası**:  
  
-   İşlemler kümesi için bir kapsayıcı, bir sunucu üzerinde çalışıyor. Örneğin, bir bağlantı noktası, Windows CE tabanlı bir cihaz seri kabloyu tarafından veya bir ağa bağlı olmayan-DCOM makine bağlantı temsil edebilir. Yerel bağlantı noktası olarak adlandırılan bir özel bağlantı noktasını, yerel makine üzerinde çalışan tüm işlemler içerir.  
  
-   Kendisini ad veya tanımlayıcı tanımlayabilirsiniz.  
  
-   Bağlantı noktası üzerinde çalışan tüm işlemler numaralandırır ve başlatabileceğini ve bu işlemleri sonlandırılacak.  
  
-   Tarafından temsil edilen bir [IDebugPort2](../../extensibility/debugger/reference/idebugport2.md) geçirerek oluşturulan arabirimi bir [IDebugPortRequest2](../../extensibility/debugger/reference/idebugportrequest2.md) bağımsız değişkeni [AddPort](../../extensibility/debugger/reference/idebugportsupplier2-addport.md).  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]tüm Windows tabanlı işlemler, yerel ve yönetilen işleyen varsayılan bir bağlantı noktası sağlar. Özel bir bağlantı noktası bağlantıları için Windows tabanlı olmayan dış cihazları ile uygulanmalıdır. Bu tür özel bağlantı noktaları temin etmek için özel bir bağlantı noktası tedarikçi ayrıca uygulanması gerekir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sunucuları](../../extensibility/debugger/servers-visual-studio-sdk.md)   
 [İşlemler](../../extensibility/debugger/processes.md)   
 [Hata ayıklayıcı kavramları](../../extensibility/debugger/debugger-concepts.md)   
 [IDebugPort2](../../extensibility/debugger/reference/idebugport2.md)   
 [IDebugPortRequest2](../../extensibility/debugger/reference/idebugportrequest2.md)   
 [AddPort](../../extensibility/debugger/reference/idebugportsupplier2-addport.md)