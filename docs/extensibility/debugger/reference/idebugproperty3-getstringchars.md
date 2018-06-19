---
title: IDebugProperty3::GetStringChars | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugProperty3::GetStringChars
helpviewer_keywords:
- IDebugProperty3::GetStringChars
ms.assetid: 832c37f3-85cb-4227-8ab2-f27a80eafe90
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: d2f7d5430326f57acf686b90f911445cc36dbf02
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31118251"
---
# <a name="idebugproperty3getstringchars"></a>IDebugProperty3::GetStringChars
Bu özellik ile ilişkili dizeyi alır ve bir kullanıcı tarafından sağlanan arabellek depolar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT GetStringChars(  
   ULONG  buflen,  
   WCHAR* rgString,  
   ULONG* pceltFetched  
);  
```  
  
```csharp  
int GetStringChars(  
   uint       buflen,   
   out string rgString,   
   out uint   pceltFetched  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `buflen`  
 [in] En fazla karakter sayısı, kullanıcı tarafından sağlanan arabellek basılı tutabilirsiniz.  
  
 `rgString`  
 [out] Bir dize döndürür.  
  
 [C++ yalnızca] `rgString` Unicode karakter dizesi alan arabellek bir işaretçidir. Bu arabelleğin en az olmalıdır `buflen` boyutu (bayt değil) karakter.  
  
 `pceltFetched`  
 [out] Burada gerçekten arabellekte depolanan karakter sayısını döndürülür. (Olabilir `NULL` c++.)  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 C++'da, arabellek en az olduğunu güvence altına almaya dikkatli olunması gerekir `buflen` Unicode karakter uzunluğunda. Unicode karakter 2 bayt uzun olduğunu unutmayın.  
  
> [!NOTE]
>  C++'da, döndürülen dize sonlandırma bir null karakter içermez. Verilen `pceltFetched` dizesinde karakter sayısını belirtir.  
  
## <a name="example"></a>Örnek  
 
```cpp  
CStringW RetrievePropertyString(IDebugProperty2 *pPropInfo)  
{  
    CStringW returnString = L"";  
    CComQIPtr<IDebugProperty3> pProp3 = pPropInfo->pProperty;  
    If (pProp3 != NULL) {  
        ULONG dwStrLen = 0;  
        HRESULT hr;  
        hr = pProp3->GetStringCharLength(&dwStrLen);  
        if (SUCCEEDED(hr) && dwStrLen > 0) {  
            ULONG dwRead;  
            CStrBufW buf(returnString,dwStrLen,CStrBuf::SET_LENGTH);  
            hr = pProp3->GetStringChars(dwStrLen,  
                                        reinterpret_cast<WCHAR*>(static_cast<CStringW::PXSTR>(buf)),  
                                        &dwRead);  
        }  
    }  
    return(returnString);
}
```    
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [GetStringCharLength](../../../extensibility/debugger/reference/idebugproperty3-getstringcharlength.md)   
 [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md)   
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)