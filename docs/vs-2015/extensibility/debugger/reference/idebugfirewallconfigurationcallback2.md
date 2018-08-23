---
title: IDebugFirewallConfigurationCallback2 | Microsoft Docs
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
- IDebugFirewallConfigurationCallback2 interface
ms.assetid: 0827361c-b97c-4851-9898-ab6d88c81811
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 8d332b7dab143b1fedbbdfc5ac92dc2b123dfe1b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42691088"
---
# <a name="idebugfirewallconfigurationcallback2"></a>IDebugFirewallConfigurationCallback2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugFirewallConfigurationCallback2](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugfirewallconfigurationcallback2).  
  
Sorun için DCOM kullanan bir hata ayıklama altyapısı sağlar [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] güvenlik duvarı uzaktan hata ayıklama engellemez emin olmak için kullanıcı Arabirimi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDebugFirewallConfigurationCallback2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Uygulayanlar için Notlar  
 Oturum hata ayıklama Yöneticisi bağlantı noktası nesnesi tarafından uygulanır.  
  
## <a name="methods"></a>Yöntemler  
 Aşağıdaki tabloda yöntemlerini gösterilmektedir `IDebugFirewallConfigurationCallback2`.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[EnsureDCOMUnblocked](../../../extensibility/debugger/reference/idebugfirewallconfigurationcallback2-ensuredcomunblocked.md)|Güvenlik Duvarı uzaktan hata ayıklama engellemediğinizden emin istekler.|  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: Msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll

