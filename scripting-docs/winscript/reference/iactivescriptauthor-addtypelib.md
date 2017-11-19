---
title: IActiveScriptAuthor::AddTypeLib | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IActiveScriptAuthor.AddTypeLib
apilocation: scrobj.dll
helpviewer_keywords: IActiveScriptAuthor::AddTypeLib
ms.assetid: d6696547-3eb5-4f31-9c5c-60aa29b6f083
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 150628f1822c721f1e349005de457951e226ef1b
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptauthoraddtypelib"></a>IActiveScriptAuthor::AddTypeLib
Ad alanı komut dosyası için tür kitaplığı ekler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT AddTypeLib(  
   REFGUID   rguidTypeLib,  
   DWORD     dwMajor,  
   DWORD     dwMinor,  
   DWORD     dwFlags  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `rguidTypeLib`  
 [in] Eklenecek CLSID (sınıf tanımlayıcısı) tür kitaplığı.  
  
 `dwMajor`  
 [in] Ana sürüm numarası.  
  
 `dwMinor`  
 [in] İkincil sürüm numarası.  
  
 `dwFlags`  
 [in] Kullanılmıyor.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bir `HRESULT`. Olası değerler aşağıdaki tablodakileri içerir, ancak bunlarla da sınırlı değildir:  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|`S_OK`|Yöntem başarılı oldu.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntemi çağırır `LoadTypeLib` tür kitaplığı yüklenemiyor. Başarılı, bu yöntemi çağırır `IActiveScriptAuthor::AddNamedItem` tür bilgisi eklemek için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Iactivescriptauthor arabirimi](../../winscript/reference/iactivescriptauthor-interface.md)   
 [IActiveScriptAuthor::AddNamedItem](../../winscript/reference/iactivescriptauthor-addnameditem.md)   
 [LoadTypeLib](http://msdn.microsoft.com/en-us/155b48e5-5438-409e-9342-630a6a500f60)