---
title: IDebugPortPicker::DisplayPortPicker | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DisplayPortPicker
- IDebugPortPicker::DisplayPortPicker
ms.assetid: 08511ef5-be64-4069-b169-a569cc94bc64
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: bf6dee7f9c79e82d9e952e481c638c870308e890
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugportpickerdisplayportpicker"></a>IDebugPortPicker::DisplayPortPicker
Bir bağlantı noktası seçmesini sağlayan belirtilen iletişim kutusu görüntüler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT DisplayPortPicker(  
   HWND hwndParentDialog,  
   BSTR* pbstrPortId  
);  
```  
  
```csharp  
public int DisplayPortPicker(  
   int hwndParentDialog,  
   out string pbstrPortId  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `hwndParentDialog`  
 [in] Üst iletişim kutusu için işler.  
  
 `pbstrPortId`  
 [out] Bağlantı noktası tanımlayıcısı dizesi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür. Dönüş değeri `S_FALSE` (veya dönüş değeri `S_OK` ile `BSTR` kümesine `NULL`) kullanıcı tıklattınız gösterir **iptal**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugPortPicker](../../../extensibility/debugger/reference/idebugportpicker.md)