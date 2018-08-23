---
title: IDebugPort2 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugPort2
helpviewer_keywords:
- IDebugPort2 interface
ms.assetid: 8fd87f05-a950-4d14-b925-98be29d4facc
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 74e0bb9b53e955372f33c2e27f280f7bf5b87f2e
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42695993"
---
# <a name="idebugport2"></a>IDebugPort2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugPort2](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugport2).  
  
Bu arabirim, bir makinedeki bir hata ayıklama bağlantı temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDebugPort2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Uygulayanlar için Notlar  
 Özel bağlantı noktası sağlayıcısı bir hata ayıklama bağlantı noktası bir makinede temsil etmek için bu arabirimi uygular.  
  
 Bağlantı noktası gönderme bağlantı noktası olayları destekliyorsa, ayrıca uygulamalıdır <xref:System.Runtime.InteropServices.ComTypes.IConnectionPointContainer> arabirimi desteklemek için bir <xref:System.Runtime.InteropServices.ComTypes.IConnectionPoint> sırayla sağlayan arabirimi [IDebugPortEvents2](../../../extensibility/debugger/reference/idebugportevents2.md) arabirimi.  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 Çağrılar [GetPort](../../../extensibility/debugger/reference/idebugportsupplier2-getport.md) veya [AddPort](../../../extensibility/debugger/reference/idebugportsupplier2-addport.md) istenen bağlantı noktası gösteren bu bir arabirim döndürür.  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 Aşağıdaki tabloda yöntemlerini gösterilmektedir `IDebugPort2`.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[GetPortName](../../../extensibility/debugger/reference/idebugport2-getportname.md)|Bağlantı noktası adı döndürür.|  
|[GetPortId](../../../extensibility/debugger/reference/idebugport2-getportid.md)|Bağlantı noktası tanımlayıcısını döndürür.|  
|[GetPortRequest](../../../extensibility/debugger/reference/idebugport2-getportrequest.md)|Bir bağlantı noktası (varsa) oluşturmak için kullanılan istek döndürür.|  
|[GetPortSupplier](../../../extensibility/debugger/reference/idebugport2-getportsupplier.md)|Bu bağlantı için bağlantı noktası sağlayıcısı döndürür.|  
|[GetProcess](../../../extensibility/debugger/reference/idebugport2-getprocess.md)|İşlem tanımlayıcısı verilen işlem için bir arabirim döndürür.|  
|[EnumProcesses](../../../extensibility/debugger/reference/idebugport2-enumprocesses.md)|Bir bağlantı noktası üzerinde çalışan tüm işlemler numaralandırır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Yerel bağlantı noktası işlemleri ve yerel makine üzerinde çalışan programlar erişim sağlar. Diğer bağlantı noktaları, Windows CE tabanlı bir cihaz için bir seri kablo bağlantısı veya ağ bağlantısı DCOM olmayan bir bilgisayara temsil edebilir. `IDebugPort2` Arabirimi, ad ve tanımlayıcı bir bağlantı noktasının bağlantı noktası üzerinde çalışan tüm işlemler listeleme bulmak ve başlatma ve bağlantı noktası işlemleri sonlandırma olanakları sağlamak için kullanılır.  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Temel arabirimler](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md)   
 [IDebugCoreServer2](../../../extensibility/debugger/reference/idebugcoreserver2.md)

