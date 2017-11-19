---
title: "Setwefprocessıd yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
ms.assetid: 404eec23-a67e-4f5b-b27d-86651f08be03
caps.latest.revision: "8"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 0821c799a4d6385997704724c00a2aff4669eb17
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="setwefprocessid-method"></a>SetWefProcessId Yöntemi
  Web uzantılarının Framework (WEF) içerik çalışacak işlem tanımlayıcısını sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT SetWefProcessId(  
    [in] DWORD dwProcessId  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|*dwProcessId*|WEF içeriğini çalıştırmak için kullanılan işlem tanımlayıcısı.|  
  
## <a name="return-value"></a>Dönüş Değeri  
 Yöntemi başarıyla tamamlanmış olup olmadığını belirten bir HRESULT değer.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem, WEF içerik işlem oluşturulduktan sonra ancak herhangi bir WEF içerik çalışmadan önce çağrılmalıdır.  
  
 Bir hata ayıklayıcısı WEF içerik işleme iliştirilemiyor geliştirme ortamı isterseniz, ortama bu yöntem uygulamanızda bu işlemi gerçekleştirmeniz gerekir.  
  
  