---
title: OPTNAMECHANGEPFN | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- OPTNAMECHANGEPFN
helpviewer_keywords:
- OPTNAMECHANGEPFN callback function
ms.assetid: 147303f3-c7f1-438a-81b7-db891ea3d076
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 083b91dd44101f387c89e2313dba3ffb9a9ee737
ms.sourcegitcommit: 06db1892fff22572f0b0a11994dc547c2b7e2a48
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39636522"
---
# <a name="optnamechangepfn"></a>OPTNAMECHANGEPFN
Bu, bir geri çağırma işlevi çağrısında belirtilen [SccSetOption](../extensibility/sccsetoption-function.md) (seçeneği kullanılarak `SCC_OPT_NAMECHANGEPFN`) ve IDE eklenti kaynak denetimi tarafından yapılan ad değişiklikleri iletişim kurmak için kullanılır.  
  
## <a name="signature"></a>İmza  
  
```cpp  
typedef void (*OPTNAMECHANGEPFN)(  
   LPVOID pvCallerData,  
   LPCSTR pszOldName,  
   LPCSTR pszNewName  
);  
```  
  
## <a name="parameters"></a>Parametreler  
 pvCallerData  
 [in] Önceki çağrıda belirtilen kullanıcı değeri [SccSetOption](../extensibility/sccsetoption-function.md) (seçeneği kullanılarak `SCC_OPT_USERDATA`).  
  
 pszOldName  
 [in] Özgün dosya adı.  
  
 pszNewName  
 [in] Dosya adı olarak değiştirildi.  
  
## <a name="return-value"></a>Dönüş değeri  
 Yok.  
  
## <a name="remarks"></a>Açıklamalar  
 Kaynak Denetimi Eklentisi, bir dosya kaynak denetimi işlemi sırasında yeniden adlandırılırsa, IDE bu geri çağırma aracılığıyla ad değişikliği hakkında bildirimde bulunabilir.  
  
 IDE bu geri çağırma desteklemiyorsa değil çağırır [SccSetOption](../extensibility/sccsetoption-function.md) belirlemek için. Eklenti bu geri çağırma desteklemiyor ise, onu döndürür `SCC_E_OPNOTSUPPORTED` gelen `SccSetOption` işlev IDE geri çağırmayı ayarlama girişiminde bulunduğunda.  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [IDE tarafından uygulanan geri çağırma işlevleri](../extensibility/callback-functions-implemented-by-the-ide.md)   
 [SccSetOption](../extensibility/sccsetoption-function.md)