---
title: IDebugFirewallConfigurationCallback2::EnsureDCOMUnblocked | Microsoft Docs
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
- EnsureDCOMUnblocked
- IDebugFirewallConfigurationCallback2::EnsureDCOMUnblocked
ms.assetid: acf54d27-32a6-47e7-aba6-3cc0004edc7f
caps.latest.revision: 7
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: ddbe6be888e31f98ffe41778bb2661d9e0f6ad01
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42628129"
---
# <a name="idebugfirewallconfigurationcallback2ensuredcomunblocked"></a>IDebugFirewallConfigurationCallback2::EnsureDCOMUnblocked
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugFirewallConfigurationCallback2::EnsureDCOMUnblocked](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugfirewallconfigurationcallback2-ensuredcomunblocked).  
  
Güvenlik Duvarı uzaktan hata ayıklama engellemediğinizden emin istekler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT EnsureDCOMUnblocked(   
    Void  
);  
```  
  
```csharp  
public int EnsureDCOMUnblocked();  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugFirewallConfigurationCallback2](../../../extensibility/debugger/reference/idebugfirewallconfigurationcallback2.md)

