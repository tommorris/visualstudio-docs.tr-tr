---
title: IDebugModule3::GetSymbolInfo | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugModule3::GetSymbolInfo
helpviewer_keywords:
- GetSymbolInfo method
- IDebugModule3::GetSymbolInfo method
ms.assetid: dda5e8e1-6878-4aa9-9ee4-e7d0dcc11210
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 53d84b9ef6cdabc12c88e30fc65d506cad673a26
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31121033"
---
# <a name="idebugmodule3getsymbolinfo"></a>IDebugModule3::GetSymbolInfo
Her yol arama sonuçlarını yanı sıra simgeleri aranır yolların listesini alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT GetSymbolInfo(  
   SYMBOL_SEARCH_INFO_FIELDS  dwFields,  
   MODULE_SYMBOL_SEARCH_INFO* pInfo  
);  
```  
  
```csharp  
int GetSymbolInfo(  
   enum_SYMBOL_SEARCH_INFO_FIELDS dwFields,   
   MODULE_SYMBOL_SEARCH_INFO[]    pinfo  
);  
  
```  
  
#### <a name="parameters"></a>Parametreler  
 `dwFields`  
 [in] Bayraklarını bileşimini [SYMBOL_SEARCH_INFO_FIELDS](../../../extensibility/debugger/reference/symbol-search-info-fields.md) hangi alanlarının belirten numaralandırma `pInfo` doldurulması üzeresiniz.  
  
 `pInfo`  
 [out] A [MODULE_SYMBOL_SEARCH_INFO](../../../extensibility/debugger/reference/module-symbol-search-info.md) üyeleri olan oturum belirtilen bilgileri doldurulacak yapısı. Bu bir null değeri ise, bu yöntem `E_INVALIDARG`.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
> [!NOTE]
>  Döndürülen dize (içinde `MODULE_SYMBOL_SEARCH_INFO` yapısı) boş olabilir olsa bile `S_OK` döndürülür. Bu durumda, geri dönmek için hiçbir Ara bilgi yoktu.  
  
## <a name="remarks"></a>Açıklamalar  
 Varsa `bstrVerboseSearchInfo` alanını `MODULE_SYMBOL_SEARCH_INFO` yapısı boş değil ve ardından arama yolları ve arama sonuçlarını listesini içerir. Listenin sonucu tarafından izlenen bir üç nokta ("..."), ve ardından bir yolu biçimlendirilir. Birden fazla yol sonuç çifti varsa, her bir çifti "\r\n" (satır-return/satır besleme) çifti tarafından ayrılır. Desen şöyle görünür:  
  
 \<yolu >... \<sonuç > \r\n\<yolu >... \<sonuç > \r\n\<yolu >... \<sonuç >  
  
 Son girişi \r\n sırası yok unutmayın.  
  
## <a name="example"></a>Örnek  
 Bu örnekte, üç farklı Arama sonuçlarıyla üç yolu bu yöntemi döndürür. Her satır bir satır başı-return/satır besleme çifti ile sonlandırıldı. Örnek çıktı yalnızca tek bir dize arama sonuçlarını yazdırır.  
  
> [!NOTE]
>  Bir durum hemen ardından "..." satırın sonuna kadar her şeyi sonucudur.  
  
```cpp  
void ShowSymbolSearchResults(IDebugModule3 *pIDebugModule3)  
{  
    MODULE_SYMBOL_SEARCH_INFO ssi = { 0 };  
    HRESULT hr;  
    hr = pIDebugModule3->GetSymbolInfo(SSIF_VERBOSE_SEARCH_INFO,&ssi);  
    if (SUCCEEDED(hr)) {  
        CComBSTR searchInfo = ssi.bstrVerboseSearchInfo;  
        if (searchInfo.Length() != 0) {  
            std::wcout << (wchar_t *)(BSTR)searchInfo;  
            std::wcout << std::endl;  
        }  
    }  
}  
```  
  
 **c:\symbols\user32.pdb... Dosyası bulunamadı.**  
**c:\winnt\symbols\user32.pdb... Sürüm eşleşmiyor.**  
**\\\symbols\symbols\user32.dll\0a8sd0ad8ad\user32.pdb... Yüklenen simgeler.**   
## <a name="see-also"></a>Ayrıca Bkz.  
 [SYMBOL_SEARCH_INFO_FIELDS](../../../extensibility/debugger/reference/symbol-search-info-fields.md)   
 [MODULE_SYMBOL_SEARCH_INFO](../../../extensibility/debugger/reference/module-symbol-search-info.md)   
 [IDebugModule3](../../../extensibility/debugger/reference/idebugmodule3.md)