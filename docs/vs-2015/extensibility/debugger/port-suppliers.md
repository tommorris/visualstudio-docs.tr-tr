---
title: Bağlantı sağlayıcıları | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- port suppliers
- debugging [Debugging SDK], port suppliers
ms.assetid: a8f3db96-1a13-4e93-9ef6-0861880369e0
caps.latest.revision: 16
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 3be95dfdb84f373730d087e9d6da1096891770af
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42688370"
---
# <a name="port-suppliers"></a>Bağlantı Noktası Sağlayıcıları
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [bağlantı noktası sağlayıcıları](https://docs.microsoft.com/visualstudio/extensibility/debugger/port-suppliers).  
  
Hata ayıklayıcı mimarisi bakımından bir **bağlantı noktası sağlayıcısı**:  
  
-   Sunucu tarafından bulunur ve bu sunucuya gönderilen istek bağlantı noktaları sağlar.  
  
-   Ekleyebilir ve bağlantı noktalarını içeren sunucudan kaldırın.  
  
-   Sunucuya yayımlamış tüm bağlantı noktaları sıralayabilirsiniz.  
  
-   Tarafından temsil edilen bir [IDebugPortSupplier2](../../extensibility/debugger/reference/idebugportsupplier2.md) kayıt defteri aracılığıyla Visual Studio ile kayıtlı arabirim. Bu arabirim, çağrılarak alınabilir [GetPortSupplier](../../extensibility/debugger/reference/idebugcoreserver2-getportsupplier.md).  
  
 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Varsayılan bağlantı noktası sağlayıcısı ve varsayılan bir bağlantı noktası sağlar. Özel bir bağlantı noktası uygulanması gerekiyorsa, özel bağlantı noktası sağlayıcısı Ayrıca bu özel bağlantı sağlamak için uygulanması gerekir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sunucuları](../../extensibility/debugger/servers-visual-studio-sdk.md)   
 [Bağlantı noktaları](../../extensibility/debugger/ports.md)   
 [Hata ayıklayıcı kavramları](../../extensibility/debugger/debugger-concepts.md)   
 [IDebugPortSupplier2](../../extensibility/debugger/reference/idebugportsupplier2.md)   
 [GetPortSupplier](../../extensibility/debugger/reference/idebugcoreserver2-getportsupplier.md)

