---
title: SccPopulateDirList işlevi | Microsoft Docs
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
- SccPopulateDirList
helpviewer_keywords:
- SccPopulateDirList function
ms.assetid: dfff634b-b155-498b-a356-6eb252ac4fad
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 358512c94f46971cc91ef3ed065c83ba56e5ad16
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42673358"
---
# <a name="sccpopulatedirlist-function"></a>SccPopulateDirList İşlevi
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [SccPopulateDirList işlevi](https://docs.microsoft.com/visualstudio/extensibility/sccpopulatedirlist-function).  
  
Bu işlev, hangi dizinleri ve (isteğe bağlı olarak) dosyaları incelemek için dizinler listesini verilen kaynak denetiminde depolanmış belirler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
SCCRTN SccPopulateDirList(  
   LPVOID        pContext,  
   LONG          nDirs,  
   LPCSTR*       lpDirPaths,  
   POPDIRLISTFUNCpfnPopulate,  
   LPVOID        pvCallerData,  
   LONG          fOptions  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 pContext  
 [in] Kaynak Denetimi Eklentisi bağlam işaretçisi.  
  
 nDirs  
 [in] Dizin yolları sayısı `lpDirPaths` dizisi.  
  
 lpDirPaths  
 [in] İncelemek için dizin yolları dizisi.  
  
 pfnPopulate  
 [in] Her dizin yolu ve (isteğe bağlı) dosya için çağrılacak bir geri çağırma işlevi `lpDirPaths` (bkz [POPDIRLISTFUNC](../extensibility/popdirlistfunc.md) Ayrıntılar için).  
  
 pvCallerData  
 [in] Geri çağırma işlevine geçirilecek değer değişmedi.  
  
 fOptions  
 [in] Dizinleri nasıl işleneceğini denetleyen değerlerinin bir birleşimini ("PopulateDirList bayraklar" bölümüne bakın [kullanılan bit bayrakları tarafından belirli komutları](../extensibility/bitflags-used-by-specific-commands.md) olası değerler için).  
  
## <a name="return-value"></a>Dönüş Değeri  
 Kaynak Denetimi Eklentisi uygulanması bu işlev, aşağıdaki değerlerden birini döndürmesi beklenir:  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|SCC_OK|İşlem başarıyla tamamlandı.|  
|SCC_E_UNKNOWNERROR|Bir hata oluşmuştur.|  
  
## <a name="remarks"></a>Açıklamalar  
 Yalnızca bu dizinleri ve (isteğe bağlı olarak) kaynak denetim deposunda olan dosya adlarını geri çağırma işlevine geçirilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak Denetimi Eklentisi API işlevleri](../extensibility/source-control-plug-in-api-functions.md)   
 [Özel komutlar tarafından kullanılan bit bayrakları](../extensibility/bitflags-used-by-specific-commands.md)   
 [POPDIRLISTFUNC](../extensibility/popdirlistfunc.md)   
 [Hata Kodları](../extensibility/error-codes.md)

