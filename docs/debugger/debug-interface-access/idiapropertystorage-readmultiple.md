---
title: IDiaPropertyStorage::ReadMultiple | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaPropertyStorage::ReadMultiple
ms.assetid: 6ccc9397-ce41-4f72-b261-72ac252cd4a5
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 77ead9e28f86067c08aa610fc902f2a0847bfb25
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
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
 [Idiapropertystorage](../../debugger/debug-interface-access/idiapropertystorage.md)