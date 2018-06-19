---
title: IDebugPortPicker::DisplayPortPicker | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- DisplayPortPicker
- IDebugPortPicker::DisplayPortPicker
ms.assetid: 08511ef5-be64-4069-b169-a569cc94bc64
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: bb43ac1bdf173de8e7224f154ecb57cca53abd8c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31113240"
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