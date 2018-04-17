---
title: IDebugBreakpointChecksumRequest2::GetChecksum | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- IDebugBreakpointChecksumRequest2::GetChecksum
ms.assetid: ec434882-e5c0-4d76-a58b-22c260d8626e
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 6ecd6d0ed9c69cad1275a399ffacf402529eebf4
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="idebugbreakpointchecksumrequest2getchecksum"></a>IDebugBreakpointChecksumRequest2::GetChecksum
Belge sağlama toplamı kullanmak sağlama toplamı algoritması benzersiz tanıtıcısı verilen bir kesme noktası isteği alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT GetChecksum(   
   REFGUID        guidAlgorithm,  
   CHECKSUM_DATA *pChecksumData  
);  
```  
  
```csharp  
public int GetChecksum(   
   ref Guid               guidAlgorithm,  
   out enum_CHECKSUM_DATA pChecksumData  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `guidAlgorithm`  
 [in] Sağlama toplamı algoritması benzersiz tanımlayıcısı.  
  
 `pChecksumData`  
 [out] Kesme noktası isteği belge sağlama toplamı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek hakkında bağlı olduğundan, bir belgenin sağlama toplamı UI birinden eşleşip eşleşmediğini denetler bir işlev gösterir.  
  
```cpp  
bool CDebugProgram::DoChecksumsMatch(CDebugPendingBreakpoint *pPending, CDebugCodeContext *pContext)  
{  
    bool fRet = false;  
    HRESULT hRes;  
  
    // Get the checksum for the document we are about to bind to from the pdb side  
    GUID guidAlgorithmId;  
    BYTE *pChecksum = NULL;  
    ULONG cNumBytes = 0;  
  
    hRes = pContext->GetDocumentChecksumAndAlgorithmId(&guidAlgorithmId, &pChecksum, &cNumBytes);  
  
    if ( S_OK == hRes )  
    {  
        // Get checksum data for the document from the UI (request) side  
        CComPtr<IDebugBreakpointChecksumRequest2> pChecksumRequest;  
  
        hRes = pPending->GetChecksumRequest(&pChecksumRequest);  
  
        if ( S_OK == hRes )  
        {  
            CHECKSUM_DATA data;  
  
            hRes = pChecksumRequest->GetChecksum(guidAlgorithmId, &data);  
  
            if ( S_OK == hRes )  
            {  
                if ( data.ByteCount == cNumBytes && memcmp(data.pBytes, pChecksum, cNumBytes) == 0 )  
                    fRet = true;  
                else  
                    fRet = false;  
  
                // Free up data allocated for checksum data  
                CoTaskMemFree(data.pBytes);  
            }  
            else  
                fRet = true; // checksums not available - user disabed checksums  
        }  
        else  
            fRet = true; // we couldn't get checksum from UI - default to past behavior  
  
        // free up space allocated for checksum from pdb  
        CoTaskMemFree(pChecksum);  
    }  
    else  
        fRet = true; // we don't have a checksum to compare with.  
  
    return ( fRet );  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugBreakpointChecksumRequest2](../../../extensibility/debugger/reference/idebugbreakpointchecksumrequest2.md)