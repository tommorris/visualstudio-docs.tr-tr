---
title: "SccPopulateDirList işlevi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SccPopulateDirList
helpviewer_keywords:
- SccPopulateDirList function
ms.assetid: dfff634b-b155-498b-a356-6eb252ac4fad
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 4be6e63df26d3c4a9b6539276aa97f69e349b83c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="sccpopulatedirlist-function"></a>SccPopulateDirList işlevi
Bu işlev, hangi dizinleri ve (isteğe bağlı) dosyaları incelemek için dizinlerin listesini verilen kaynak denetiminde saklanır belirler.  
  
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
 [in] Kaynak Denetim eklentisi bağlam işaretçi.  
  
 nDirs  
 [in] Dizin yolları sayısı `lpDirPaths` dizi.  
  
 lpDirPaths  
 [in] İncelemek için dizin yolu dizisi.  
  
 pfnPopulate  
 [in] Her dizin yolu ve (isteğe bağlı) dosya çağrısı yapmak için geri çağırma işlevi `lpDirPaths` (bkz [POPDIRLISTFUNC](../extensibility/popdirlistfunc.md) Ayrıntılar için).  
  
 pvCallerData  
 [in] Geri çağırma işlevi değişmeden iletilecek olan değer.  
  
 fOptions  
 [in] Dizinleri nasıl işlendiği denetleyen değerlerini birleşimi ("PopulateDirList bayrakları" bölümüne bakın [bit işaretleri belirli komutları tarafından kullanılan](../extensibility/bitflags-used-by-specific-commands.md) olası değerler için).  
  
## <a name="return-value"></a>Dönüş Değeri  
 Aşağıdaki değerlerden birini döndürmek için bu işlevi kaynak denetimi eklenti uyarlamasını beklenen:  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|SCC_OK|İşlem başarıyla tamamlandı.|  
|SCC_E_UNKNOWNERROR|Bir hata oluşmuştur.|  
  
## <a name="remarks"></a>Açıklamalar  
 Yalnızca bu dizinler ve (isteğe bağlı) kaynak denetimi deposunda olan dosya adları için geri çağırma işlevi geçirilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak Denetim eklentisi API işlevleri](../extensibility/source-control-plug-in-api-functions.md)   
 [Özel komutlar tarafından kullanılan bit işaretleri](../extensibility/bitflags-used-by-specific-commands.md)   
 [POPDIRLISTFUNC](../extensibility/popdirlistfunc.md)   
 [Hata Kodları](../extensibility/error-codes.md)