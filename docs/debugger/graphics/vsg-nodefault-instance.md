---
title: VSG_NODEFAULT_INSTANCE | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
ms.assetid: 19c95b0d-9a4d-441f-9ed7-3acb39e67521
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3200aa01390ce8933e6897ab063cacc3e03a8acc
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="vsgnodefaultinstance"></a>VSG_NODEFAULT_INSTANCE
Kendi varlığı varsayılan örneği olup olmadığını tanımlar [VsgDbg sınıfı](vsgdbg-class.md) sınıfı — programlı yakalama arabirim sunar — sağlanır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
#define VSG_NODEFAULT_INSTANCE  
```  
  
## <a name="value"></a>Değer  
 Bir önişlemci sembol, kendi varlığı veya yokluğuna varsayılan örneği olup olmadığını belirler `VsgDbg` sınıfı sağlanır. Bu simgenin tanımlanırsa, ardından varsayılan örneği `VsgDbg` sınıfı sağlanır; Aksi takdirde, varsayılan bir örnek sağlanan ve programınızı çalışmadan önce başlatıldı.  
  
 Genel kapsama sahip bir işaretçi programlı yakalama arabirimi sağlanır `g_pVsgDbg`.  
  
```  
VsgDbg *g_pVsgDbg;  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Varsayılan örnek genellikle yeterli olur, ancak D3D aygıtı dışında bu DLL oluşturduğunuzda programlı yakalama arabirim DLL içinde kullanmak için oluşturabilir ve kendi örneğini yönetme `VsgDbg` sınıfı. Bu şekilde programlı yakalama API kendi arabirimine yönetiyorsanız, varsayılan örnek tanımlayarak devre dışı bırakma `VSG_NODEFAULT_INSTANCE` yükünü önlemek için.  
  
 Varsayılan örneği devre dışı değil, program çalışmadan önce otomatik olarak başlatılır ve programınızı bittiğinde otomatik olarak yok. Başlatması veya bu örnek açıkça uninitialize gerekmez.  
  
 Varsayılan örneği devre dışı bırakmak için tanımlamalısınız `VSG_NODEFAULT_INSTANCE` dahil önce `vsgcapture.h` programınızdaki.  
  
## <a name="example"></a>Örnek  
 Bu örnek varsayılan örnek devre dışı bırakma gösterir:  
  
```  
// Define VSG_NODEFAULT_INSTANCE before including vsgcapture.h  
#define VSG_NODEFAULT_INSTANCE  
  
#include <vsgcapture.h>  
```