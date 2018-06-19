---
title: IActiveScriptAuthor::GetInfoFromContext | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptAuthor.GetInfoFromContext
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptAuthor::GetInfoFromContext
ms.assetid: 9891b095-6eb5-4473-87c0-c2e5cd2afc1a
caps.latest.revision: 15
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 27c13dbe51bb1150554275b5fbeacd00be2e445f
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24793334"
---
# <a name="iactivescriptauthorgetinfofromcontext"></a>IActiveScriptAuthor::GetInfoFromContext
Döndürür kod bloğunda bilgi ve belirli bir karakter için bağlantı konumlarını yazın. IntelliSense, genel listeleri ve parametre ipuçları bu üye için bilgi sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT GetInfoFromContext(  
   LPCOLESTR  pszCode,  
   ULONG      cchCode,  
   ULONG      ichCurrentPosition,  
   DWORD      dwListTypesRequested,  
   DWORD      *pdwListTypesProvided,  
   ULONG      *pichListAnchorPosition,  
   ULONG      *pichFuncAnchorPosition,  
   MEMBERID   *pmemid,  
   LONG       *piCurrentParameter,  
   IUnknown   **ppunk  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pszCode`  
 [in] Bilgi sonuçları oluşturmak için kullanılan kod bloğu dizesi adresi.  
  
 `cchCode`  
 [in] Kod bloğu uzunluğu.  
  
 `ichCurrentPosition`  
 [in] Bloğun başlangıç göreli karakterin konumu.  
  
 `dwListTypesRequested`  
 [in] İstenen liste türleri. Aşağıdaki değerlerden bir bileşimi olabilir:  
  
|Sabit|Değer|Açıklama|  
|--------------|-----------|-----------------|  
|SCRIPT_CMPL_NOLIST|0x0000|Listesi yok.|  
|SCRIPT_CMPL_MEMBERLIST|0X0001|Üye listesi.|  
|SCRIPT_CMPL_ENUMLIST|0X0002|Enum listesi.|  
|SCRIPT_CMPL_PARAMLIST|0X0004|Arama yöntemi parametre listesi.|  
|SCRIPT_CMPL_GLOBALLIST|0X0008|Genel listesi.|  
  
 SCRIPT_CMPL_GLOBALLIST türü diğer tamamlama öğeleriyle veya işlecini kullanarak birleştirilebilir varsayılan bir tamamlanma öğesi olarak kabul edilir. Diğer tamamlanma listesi öğeleri için tür bilgisi doldurmak komut dosyası altyapısı ilk yazma çalışır. Başarısız olursa, altyapı için SCRIPT_CMPL_GLOBALLIST doldurur.  
  
 `pdwListTypesProvided`  
 [out] Verilen liste türü.  
  
 `pichListAnchorPosition`  
 [out] Geçerli konumunu içeren bağlam başlangıç dizini. Başlangıç blok başlangıç göre dizindir.  
  
 Bu doldurulur yalnızca `dwListTypesRequested` SCRIPT_CMPL_MEMBERLIST, SCRIPT_CMPL_ENUMLIST veya SCRIPT_CMPL_GLOBALLIST içerir. Diğer istenen liste türleri için sonuç tanımlanmamıştır.  
  
 `pichFuncAnchorPosition`  
 [out] Geçerli konumunu içeren işlev çağrısı başlangıç dizini. Başlangıç blok başlangıç göre dizindir.  
  
 Bu yalnızca geçerli konumunu içeren bir işlev çağrısı bağlamdır ne ve ne zaman doldurulur `dwListTypesRequested` SCRIPT_CMPL_PARAMLIST içerir. Aksi takdirde, sonuç tanımlanmamıştır.  
  
 `pmemid`  
 [out] Bir türe göre tanımlanan işlevinin MEMBERID `IProvideMultipleClassInfo``ppunk` çıkış parametresi.  
  
 Bu doldurulur yalnızca `dwListTypesRequested` SCRIPT_CMPL_PARAMLIST içerir.  
  
 `piCurrentParameter`  
 [out] Geçerli konumunu içeren parametre dizini. Geçerli konumu işlevi adına, -1 döndürülür.  
  
 `piCurrentParameter` Değeri doldurulur yalnızca `dwListTypesRequested` SCRIPT_CMPL_PARAMLIST içerir.  
  
 `ppunk`  
 Biçiminde sağlanan türü bilgileri bir `IProvideMultipleClassInfo` nesnesi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bir `HRESULT`. Olası değerler aşağıdaki tablodakileri içerir, ancak bunlarla da sınırlı değildir:  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|`S_OK`|Yöntem başarılı oldu.|  
  
## <a name="remarks"></a>Açıklamalar  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IProvideMultipleClassInfo arabirimi](https://msdn.microsoft.com/library/microsoft.visualstudio.ole.interop.iprovidemultipleclassinfo.aspx)   
 [Iactivescriptauthor arabirimi](../../winscript/reference/iactivescriptauthor-interface.md)