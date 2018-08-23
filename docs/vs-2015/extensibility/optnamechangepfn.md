---
title: OPTNAMECHANGEPFN | Microsoft Docs
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
- OPTNAMECHANGEPFN
helpviewer_keywords:
- OPTNAMECHANGEPFN callback function
ms.assetid: 147303f3-c7f1-438a-81b7-db891ea3d076
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: f729e00805fa1c73fe1e64197788dd31f2a2a41d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42629553"
---
# <a name="optnamechangepfn"></a>OPTNAMECHANGEPFN
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [OPTNAMECHANGEPFN](https://docs.microsoft.com/visualstudio/extensibility/optnamechangepfn).  
  
Bu, bir geri çağırma işlevi çağrısında belirtilen [SccSetOption](../extensibility/sccsetoption-function.md) (seçeneği kullanılarak `SCC_OPT_NAMECHANGEPFN`) ve IDE eklenti kaynak denetimi tarafından yapılan ad değişiklikleri iletişim kurmak için kullanılır.  
  
## <a name="signature"></a>İmza  
  
```cpp#  
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
  
## <a name="return-value"></a>Dönüş Değeri  
 Yok.  
  
## <a name="remarks"></a>Açıklamalar  
 Kaynak Denetimi Eklentisi, bir dosya kaynak denetimi işlemi sırasında yeniden adlandırılırsa, IDE bu geri çağırma aracılığıyla ad değişikliği hakkında bildirimde bulunabilir.  
  
 IDE bu geri çağırma desteklemiyorsa değil çağırır [SccSetOption](../extensibility/sccsetoption-function.md) belirlemek için. Eklenti bu geri çağırma desteklemiyor ise, onu döndürür `SCC_E_OPNOTSUPPORTED` gelen `SccSetOption` işlev IDE geri çağırmayı ayarlama girişiminde bulunduğunda.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDE tarafından uygulanan geri çağırma işlevleri](../extensibility/callback-functions-implemented-by-the-ide.md)   
 [SccSetOption](../extensibility/sccsetoption-function.md)

