---
title: SccPopulateDirList işlevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- SccPopulateDirList
helpviewer_keywords:
- SccPopulateDirList function
ms.assetid: dfff634b-b155-498b-a356-6eb252ac4fad
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 5315f3156f71310c92069ec3743232e98818b9a5
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31137150"
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