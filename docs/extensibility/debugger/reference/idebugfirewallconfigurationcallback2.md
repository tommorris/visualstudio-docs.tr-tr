---
title: IDebugFirewallConfigurationCallback2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IDebugFirewallConfigurationCallback2 interface
ms.assetid: 0827361c-b97c-4851-9898-ab6d88c81811
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 02996f28ca502359d9a2d71cfbf11a913f2bf51e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugfirewallconfigurationcallback2"></a>IDebugFirewallConfigurationCallback2
Sorulacak DCOM kullanan bir hata ayıklama altyapısı sağlar [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] güvenlik duvarı uzaktan hata ayıklama engellemez emin olmak için kullanıcı Arabirimi.  
  
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
|[EnsureDCOMUnblocked](../../../extensibility/debugger/reference/idebugfirewallconfigurationcallback2-ensuredcomunblocked.md)|İstekler güvenlik duvarı uzaktan hata ayıklama engellemeniz değil.|  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: Msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll