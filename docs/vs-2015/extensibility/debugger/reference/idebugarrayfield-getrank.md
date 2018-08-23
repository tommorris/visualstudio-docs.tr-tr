---
title: IDebugArrayField::GetRank | Microsoft Docs
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
- IDebugArrayField::GetRank
helpviewer_keywords:
- IDebugArrayField::GetRank method
ms.assetid: 2364b876-5be1-4bab-9b8f-3b6121da35c6
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: f1ddd6ae45342f0efa9312881883adfc63074e73
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42693555"
---
# <a name="idebugarrayfieldgetrank"></a>IDebugArrayField::GetRank
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugArrayField::GetRank](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugarrayfield-getrank).  
  
Derece veya dizinin boyut sayısını alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT GetRank(   
   DWORD* pdwRank  
);  
```  
  
```csharp  
int GetRank(  
   out uint pdwRank  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pdwRank`  
 [out] Derecesini döndürür.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa S_OK döndürür; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Boyut sayısı bir dizi boyut sayısını karşılık gelir. C++ ve C#, çok boyutlu diziler dizilerdir dizilerinin gerçekten ve bu nedenle yalnızca tek boyutlu bir dizi olarak düşünülebilir (ve `GetRank` yöntemi her zaman 1 döndüren). İçinde [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)], diğer taraftan, çok boyutlu diziler farklı şekilde işlenir ve boyut sayısı gibi bir dizi boyut sayısını yansıtır (ve `GetRank` yöntemi her zaman bir boyut sayısını döndürür).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugArrayField](../../../extensibility/debugger/reference/idebugarrayfield.md)

