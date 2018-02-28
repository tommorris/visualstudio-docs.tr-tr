---
title: OPTNAMECHANGEPFN | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- OPTNAMECHANGEPFN
helpviewer_keywords:
- OPTNAMECHANGEPFN callback function
ms.assetid: 147303f3-c7f1-438a-81b7-db891ea3d076
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 2d067d5dd150dd026a2bd29a8933e8d9f72222b0
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="optnamechangepfn"></a>OPTNAMECHANGEPFN
Bu bir çağrıda belirtilen bir geri çağırma işlevidir [SccSetOption](../extensibility/sccsetoption-function.md) (seçeneği kullanılarak `SCC_OPT_NAMECHANGEPFN`) ve kaynak denetimi tarafından IDE eklenti adı değişikliklerinin iletişim kurmak için kullanılır.  
  
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
 [in] Önceki bir çağrıda belirtilen kullanıcı değeri [SccSetOption](../extensibility/sccsetoption-function.md) (seçeneği kullanılarak `SCC_OPT_USERDATA`).  
  
 pszOldName  
 [in] Dosyayı özgün adı.  
  
 pszNewName  
 [in] Dosya adı yeniden adlandırıldı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Yok.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir kaynak denetimi işlemi sırasında bir dosya adlandırdıysanız, eklenti kaynak denetimi bu geri çağırma aracılığıyla ad değişikliği hakkında IDE bildirebilir.  
  
 IDE bu geri çağırma desteklemiyorsa değil çağıracak [SccSetOption](../extensibility/sccsetoption-function.md) belirlemek için. Eklenti bu geri çağırma desteklemiyor varsa, onu döndürür `SCC_E_OPNOTSUPPORTED` gelen `SccSetOption` işlev IDE geri aramasını ayarlamasını girişiminde bulunduğunda.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDE tarafından uygulanan geri arama işlevleri](../extensibility/callback-functions-implemented-by-the-ide.md)   
 [SccSetOption](../extensibility/sccsetoption-function.md)