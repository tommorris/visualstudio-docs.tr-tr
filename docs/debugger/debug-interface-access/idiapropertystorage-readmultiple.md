---
title: IDiaPropertyStorage::ReadMultiple | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaPropertyStorage::ReadMultiple
ms.assetid: 6ccc9397-ce41-4f72-b261-72ac252cd4a5
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1747d55de37777a9919f4709a62fbaff4b6d8a2a
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
ms.locfileid: "31461759"
---
# <a name="idiapropertystoragereadmultiple"></a>IDiaPropertyStorage::ReadMultiple
Geçerli özellik kümesi özelliklerinden okuma belirtildi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT ReadMultiple(   
   ULONG          cpspec,  
   PROPSPEC const rgpspec,  
   PROPVARIANT    rgvar  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `cpspec`  
 [in] Belirtilen özellikleri sayısı `rgpspec` dizi. Sıfır ise, yöntem hiçbir özellikleri döndürür ancak döndürmüyor `S_OK` başarı kod olarak.  
  
 `rgpspec`  
 [in] Okunacak özellikleri dizisi. Özelliklerini özellik kimliği veya isteğe bağlı bir dize adı tarafından belirtilebilir. Dizi belirli bir sırada özelliklerini belirtmek gerekli değildir. Dizi basit özellikleri için dönüş yinelenen özellik değerlerini sonuçta yinelenen özellikler içerebilir. İkinci kez açmak için bir denemede erişim reddedildi olmayan basit özellikler döndürmelidir. Dizi özellik kimlikleri ve dize bir karışımını içerebilir. Bu dizi en az olmalıdır `cpspec` özellik değerlerinin sayısı.  
  
 `rgvar`  
 [içinde out] Bir dizi `PROPVARIANT` her bir özellik için değerlerle doldurulacak yapıları (Microsoft.VisualStudio.OLE.Interop ad alanında). Dizi en az olmalıdır `cpspec` öğeleri boyutu. Arayan dizideki başlatma gerekmez.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`. Döndürür `S_FALSE` , bir veya daha fazla özellik bulunamadı. Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir özellik bulunamadı varsa, karşılık gelen bir giriş `rgvar` dizi içeren bir `VARIANT` türüyle `VT_EMPTY`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDiaPropertyStorage](../../debugger/debug-interface-access/idiapropertystorage.md)