---
title: CONNECTION_PROTOCOL | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CONNECTION_PROTOCOL
helpviewer_keywords:
- CONNECTION_PROTOCOL enumeration
ms.assetid: 99df5865-8b36-486d-9f4c-d10ae2bc688a
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: ff7a1f97304dd9ba09dc8f44f3d05a23196fdeb1
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="connectionprotocol"></a>CONNECTION_PROTOCOL
Hata ayıklama sunucu ve hata ayıklama paket (DE) arasında iletişim kurmak için kullanılan protokolü gösterir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
typedef enum tagCONNECTION_PROTOCOL {  
   CONNECTION_NONE    = 0,  
   CONNECTION_UNKNOWN = 1,  
   CONNECTION_LOCAL   = 2,  
   CONNECTION_PIPE    = 3,  
   CONNECTION_TCPIP   = 4,  
   CONNECTION_HTTP    = 5,  
   CONNECTION_OTHER   = 6  
} CONNECTION_PROTOCOL;  
```  
  
```csharp  
public enum CONNECTION_PROTOCOL {  
   CONNECTION_NONE    = 0,  
   CONNECTION_UNKNOWN = 1,  
   CONNECTION_LOCAL   = 2,  
   CONNECTION_PIPE    = 3,  
   CONNECTION_TCPIP   = 4,  
   CONNECTION_HTTP    = 5,  
   CONNECTION_OTHER   = 6  
};  
```  
  
#### <a name="parameters"></a>Parametreler  
 CONNECTION_NONE  
 Bağlantı bir sunucuya yapıldı.  
  
 CONNECTION_UNKNOWN  
 Bir bağlantı oluşturulmasıyla, ancak bilinmeyen bir türüdür.  
  
 CONNECTION_LOCAL  
 Yerel bir sunucuya bağlantısıdır.  
  
 CONNECTION_PIPE  
 Bir adlandırılmış kanal bir bağlantıdır.  
  
 CONNECTION_TCPIP  
 Bağlantı TCP/IP'yi kullanır.  
  
 CONNECTION_HTTP  
 Bağlantı (bir Web sunucusu üzerinden) HTTP kullanır.  
  
 CONNECTION_OTHER  
 Başka türden bir bağlantı kuruldu (Bu değer şu anda kullanılmamaktadır).  
  
## <a name="remarks"></a>Açıklamalar  
 Bu değerleri döndürüldüğü kaynak [GetConnectionProtocol](../../../extensibility/debugger/reference/idebugcoreserver3-getconnectionprotocol.md) yöntemi.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Numaralandırmalar](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [GetConnectionProtocol](../../../extensibility/debugger/reference/idebugcoreserver3-getconnectionprotocol.md)