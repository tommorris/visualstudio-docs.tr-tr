---
title: IDebugProcessSecurity | Microsoft Docs
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
- IDebugProcessSecurity interface
ms.assetid: 8a52ddca-bd99-49c0-9778-469dce7abd44
caps.latest.revision: 5
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 5c3cfa0d8ef0f43b21ec2057b71b688b2d3ecb66
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42631018"
---
# <a name="idebugprocesssecurity"></a>IDebugProcessSecurity
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugProcessSecurity](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugprocesssecurity).  
  
`IDebugProcessSecurity` işleme iliştirdikten güvenli olduğunu kullanıcıyı uyarmak için bağlantı noktası sağlayıcısı tarafından uygulanır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDebugProcessSecurity : IUnknown  
```  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 Aşağıdaki tabloda yöntemlerini gösterilmektedir `IDebugProcessSecurity`.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[GetUserName](../../../extensibility/debugger/reference/idebugprocesssecurity-getusername.md)|Kullanıcı adı bağlantı noktası tedarikçiden alır.|  
|[QueryCanSafelyAttach](../../../extensibility/debugger/reference/idebugprocesssecurity-querycansafelyattach.md)|Hata ayıklama işlemine iliştirme'güvenli olmayan bir kullanıcıyı uyarır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir uyarı gösterir ve kullanıcının olduğu iliştirmekte olduğunuz işlemin güvensiz kabul edilebilir iptal izin vermek için bu arabirimi uygulayın.  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlantı noktaları](../../../extensibility/debugger/ports.md)   
 [Bağlantı noktası sağlayıcıları](../../../extensibility/debugger/port-suppliers.md)   
 [Temel arabirimler](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)

