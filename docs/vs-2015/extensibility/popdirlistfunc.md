---
title: POPDIRLISTFUNC | Microsoft Docs
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
- POPLISTFUNC
helpviewer_keywords:
- POPDIRLISTFUNC callback function
ms.assetid: 0ee90fd2-5467-4154-ab4c-7eb02ac3a14c
caps.latest.revision: 15
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: ed4cb154b1b1f74a6b0b6e64063a826b80364dd3
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42695104"
---
# <a name="popdirlistfunc"></a>POPDIRLISTFUNC
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [POPDIRLISTFUNC](https://docs.microsoft.com/visualstudio/extensibility/popdirlistfunc).  
  
Bu, verilen bir geri çağırma işlevini [SccPopulateDirList](../extensibility/sccpopulatedirlist-function.md) işleviyle dizinleri ve (isteğe bağlı olarak), kaynak denetimi altında olduğunu öğrenmek için dosya adları topluluğu.  
  
 `POPDIRLISTFUNC` Yalnızca dizin ve dosya adları için geri çağırma'nin çağrılabilir (verilen listedeki `SccPopulateDirList` işlevi) olan gerçekten kaynak denetimi altında.  
  
## <a name="signature"></a>İmza  
  
```cpp#  
typedef BOOL (*POPDIRLISTFUNC)(  
   LPVOID pvCallerData,  
   BOOL bFolder,  
   LPCSTR lpDirectoryOrFileName  
);  
```  
  
## <a name="parameters"></a>Parametreler  
 pvCallerData  
 [in] Verilen kullanıcı değeri [SccPopulateDirList](../extensibility/sccpopulatedirlist-function.md).  
  
 bKlasör  
 [in] `TRUE` varsa adın `lpDirectoryOrFileName` bir dizin; Aksi takdirde adı bir dosya adıdır.  
  
 lpDirectoryOrFileName  
 [in] Kaynak kodu denetimi altında dizin veya dosya adı tam yerel yolu.  
  
## <a name="return-value"></a>Dönüş Değeri  
 IDE uygun hata kodu döndürür:  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|SCC_OK|İşleme devam edin.|  
|SCC_I_OPERATIONCANCELED|İşlemeyi durdur.|  
|SCC_E_xxx|Herhangi bir uygun kaynak denetimi hata işleme durdurmanız gerekir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Varsa `fOptions` parametresinin `SccPopulateDirList` işlevi içeren `SCC_PDL_INCLUDEFILES` liste büyük bir olasılıkla dosya adları ve bunun yanı sıra dizin adları içerir bayrağı.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDE tarafından uygulanan geri çağırma işlevleri](../extensibility/callback-functions-implemented-by-the-ide.md)   
 [SccPopulateDirList](../extensibility/sccpopulatedirlist-function.md)   
 [Hata Kodları](../extensibility/error-codes.md)

