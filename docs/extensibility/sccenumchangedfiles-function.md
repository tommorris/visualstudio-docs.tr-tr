---
title: SccEnumChangedFiles işlevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- SccEnumChangedFiles
helpviewer_keywords:
- SccEnumChangedFiles function
ms.assetid: 76cac510-107b-4c1a-ba60-9c39b6db2e71
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 5b8fb9c83d8948ca3edc0650e85af6ea8c011abc
ms.sourcegitcommit: 06db1892fff22572f0b0a11994dc547c2b7e2a48
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39639834"
---
# <a name="sccenumchangedfiles-function"></a>SccEnumChangedFiles işlevi
Bu işlev yerel dosyaların listesini göz önünde bulundurulduğunda, hangi dosyaların kaynak kod denetimi veritabanında karşılık gelen sürümlerinden farklı olduğunu belirler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
SCCRTN SccEnumChangedFiles(  
   LPVOID  pContext,  
   HWND    hWnd,  
   LONG    cFiles,  
   LPCSTR* lpFileNames,  
   LONG*   plIsFileDifferent  
);  
```  
  
### <a name="parameters"></a>Parametreler  
 pContext  
 [in] Kaynak Denetimi Eklentisi bağlam işaretçisi.  
  
 hWnd  
 [in] Kaynak Denetimi Eklentisi sağladığı herhangi bir iletişim kutusu için bir üst öğe olarak kullanabileceğiniz IDE penceresi için bir tanıtıcı.  
  
 cFiles  
 [in] Belirtilen dosya adları sayısını `lpFileNames` dizisi. Ayrıca boyutunu belirtir `plIsFileDifferent` dizisi.  
  
 lpFileNames  
 [in] Denetlenecek yerel dosya adları dizisi.  
  
 plIsFileDifferent  
 [out içinde] Her dosya farkı durumunu belirten değerleri dizisi (dizisi en az olmalıdır `cFiles` girişleri). NonZero dosyanın farklı olduğu anlamına gelir.  
  
## <a name="return-value"></a>Dönüş değeri  
 Kaynak Denetimi Eklentisi uygulanması bu işlev, aşağıdaki değerlerden birini döndürmesi beklenir:  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|SCC_OK|İşlem başarıyla tamamlandı.|  
|SCC_UNSPECIFIEDERROR|Genel hata.|  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Kaynak Denetimi Eklentisi API işlevleri](../extensibility/source-control-plug-in-api-functions.md)