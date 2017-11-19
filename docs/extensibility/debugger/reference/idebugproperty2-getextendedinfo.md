---
title: IDebugProperty2::GetExtendedInfo | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugProperty2::GetExtendedInfo
helpviewer_keywords: IDebugProperty2::GetExtendedInfo
ms.assetid: 0c9c0b2b-7540-4424-adb5-fce7aa37a026
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 7456ebe1e28618270bd90f09186ec49814c62b66
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugproperty2getextendedinfo"></a>IDebugProperty2::GetExtendedInfo
Genişletilmiş özellik bilgilerini.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT GetExtendedInfo (   
   REFGUID* guidExtendedInfo,  
   VARIANT* pExtendedInfo  
);  
```  
  
```csharp  
int GetExtendedInfo (   
   ref Guid guidExtendedInfo,  
   out object pExtendedInfo  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `guidExtendedInfo`  
 [in] Alınacak genişletilmiş bilgi türünü belirler GUID. Açıklamalar için bkz.  
  
 `pExtendedInfo`  
 [out] Döndürür bir `VARIANT` (C++) veya genişletilmiş özellik bilgilerini almak için kullanılan nesne (C#). Örneğin, bu parametre döndürebilir bir `IUnknown` için sorgulanabilir arabirimi bir [IDebugDocumentText2](../../../extensibility/debugger/reference/idebugdocumenttext2.md) arabirimi. Açıklamalar için bkz.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde hata kodunu döndürür. Döndürür `S_GETEXTENDEDINFO_NO_EXTENDEDINFO` almak için genişletilmiş bilgileri yoksa.  
  
## <a name="remarks"></a>Açıklamalar  
 Kendisini çağıran alınan için ödünç değil bilgileri alma amacıyla bu yöntemi yok [GetPropertyInfo](../../../extensibility/debugger/reference/idebugproperty2-getpropertyinfo.md) yöntemi.  
  
 Aşağıdaki GUID, genellikle bu yöntemi (adı hiçbir derleme kullanılamadığından GUID değerler C# için belirtilir) tarafından tanınır. Ek GUID'ler iç kullanım için oluşturulabilir.  
  
|Ad|GUID|Açıklama|  
|----------|----------|-----------------|  
|guidDocument|{3f98de84-fee9-11d0-b47f-00a0244a1dd2}|Döndürür bir `IUnknown` belgeye arabirimi. Genellikle, [IDebugDocumentText2](../../../extensibility/debugger/reference/idebugdocumenttext2.md) arabirimi elde edilebilir öğesinden `IUnknown` arabirimi.|  
|guidCodeContext|{e2fc65e-56ce - 11d 1-b528-00aax004a8797}|Döndürür bir `IUnknown` belge bağlamı için arabirim. Genellikle, [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md) arabirimi elde edilebilir öğesinden `IUnknown` arabirimi.|  
|guidCustomViewerSupported|{d9c9da31-ffbe-4eeb-9186-23121e3c088c}|Genellikle bir ifade değerlendiricisi tarafından uygulanan özel bir Görüntüleyici CLSID içeren bir dize döndürür.|  
|guidExtendedInfoSlot|{6df235ad-82c6-4292-9c97-7389770bc42f}|Bu özellik bir yönetilen kod yerel adresi temsil ediyorsa istenen Yuva sayısını temsil eden 32 bitlik bir sayı döndürür.|  
|guidExtendedInfoSignature|{b5fb6d46-f805-417f-96a3-8ba737073ffd}|İmza özelliği nesneyle ilişkili değişkenin içeren bir dize döndürür.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)   
 [IDebugDocumentText2](../../../extensibility/debugger/reference/idebugdocumenttext2.md)   
 [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md)