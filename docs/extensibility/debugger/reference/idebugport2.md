---
title: IDebugPort2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugPort2
helpviewer_keywords: IDebugPort2 interface
ms.assetid: 8fd87f05-a950-4d14-b925-98be29d4facc
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 91ee83167c681b713ea7d7a51a38d45b05fba4d2
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugport2"></a>IDebugPort2
Bu arabirimi hata ayıklama bağlantı noktası bir makinede temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDebugPort2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Uygulayanlar için Notlar  
 Özel bir bağlantı noktası tedarikçi hata ayıklama bağlantı noktası bir makinede temsil etmek için bu arabirimi uygular.  
  
 Bağlantı noktası gönderme bağlantı noktası olayları destekliyorsa, aynı zamanda uygulamalıdır <xref:System.Runtime.InteropServices.ComTypes.IConnectionPointContainer> desteklemek için arabirimi bir <xref:System.Runtime.InteropServices.ComTypes.IConnectionPoint> sırayla sağlayan arabirimi [IDebugPortEvents2](../../../extensibility/debugger/reference/idebugportevents2.md) arabirimi.  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 Çağrılar [GetPort](../../../extensibility/debugger/reference/idebugportsupplier2-getport.md) veya [AddPort](../../../extensibility/debugger/reference/idebugportsupplier2-addport.md) istenen bağlantı noktası temsil eden bu arabirimini döndürür.  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 Aşağıdaki tabloda yöntemlerini gösterilmektedir `IDebugPort2`.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[GetPortName](../../../extensibility/debugger/reference/idebugport2-getportname.md)|Bağlantı noktası adını döndürür.|  
|[GetPortId](../../../extensibility/debugger/reference/idebugport2-getportid.md)|Bağlantı noktası tanımlayıcısını döndürür.|  
|[GetPortRequest](../../../extensibility/debugger/reference/idebugport2-getportrequest.md)|Bir bağlantı noktası (varsa) oluşturmak için kullanılan istek döndürür.|  
|[GetPortSupplier](../../../extensibility/debugger/reference/idebugport2-getportsupplier.md)|Bu bağlantı noktası için bağlantı noktası tedarikçi döndürür.|  
|[GetProcess](../../../extensibility/debugger/reference/idebugport2-getprocess.md)|İşlemin tanımlayıcısı verilen işlem için bir arabirim döndürür.|  
|[EnumProcesses](../../../extensibility/debugger/reference/idebugport2-enumprocesses.md)|Bir bağlantı noktası üzerinde çalışan tüm işlemler numaralandırır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Yerel bağlantı noktası tüm işlemleri ve yerel makine üzerinde çalışan programlar erişim sağlar. Diğer bağlantı noktaları, Windows CE tabanlı bir cihaz seri kabloyu bağlantı veya ağ bağlantısı DCOM olmayan bir bilgisayara temsil edebilir. `IDebugPort2` Arabirimi adı ve bir bağlantı noktası tanıtıcısı listeleme bağlantı noktası üzerinde çalışan tüm işlemler bulmak ve başlatma ve bağlantı noktası işlemleri sona erdirmek için özellikleri sağlamak için kullanılır.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çekirdek arabirimleri](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md)   
 [IDebugCoreServer2](../../../extensibility/debugger/reference/idebugcoreserver2.md)