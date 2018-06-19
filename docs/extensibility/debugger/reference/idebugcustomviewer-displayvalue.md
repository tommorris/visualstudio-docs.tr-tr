---
title: IDebugCustomViewer::DisplayValue | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugCustomViewer::DisplayValue
helpviewer_keywords:
- IDebugCustomViewer::DisplayValue
ms.assetid: 7a538248-5ced-450e-97cd-13fabe35fb1c
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 017e1e7a27839dae91559468c62be353bbd43b4e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31107065"
---
# <a name="idebugcustomviewerdisplayvalue"></a>IDebugCustomViewer::DisplayValue
Bu yöntem, belirtilen değeri görüntülemek için çağrılır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT DisplayValue(  
   HWND             hwnd,  
   DWORD            dwID,  
   IUnknown *       pHostServices,  
   IDebugProperty3* pDebugProperty);  
);  
```  
  
```csharp  
int DisplayValue(  
   IntPtr          hwnd,   
   uint            dwID,   
   object          pHostServices,   
   IDebugProperty3 pDebugProperty  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `hwnd`  
 [in] Ana penceresi  
  
 `dwID`  
 [in] Birden fazla türünü destekleyen özel görüntüleyiciler kimliği.  
  
 `pHostServices`  
 [in] Ayrılmış. Her zaman null.  
  
 `pDebugProperty`  
 [in] Görüntülenecek değerini almak için kullanılan arabirim.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde hata kodunu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem gerekli penceresi oluşturun, değerini görüntülemek, giriş için bekleyin ve penceresini tüm çağırana dönmeden önce kapatın görünen "kalıcı" olmamasıdır. Bu yöntem tüm yönlerini özelliğin değerden pencere yok etme için kullanıcı girişi bekleniyor için çıkış için bir pencere için görüntüleme işlemelidir anlamına gelir.  
  
 Değer değiştirme desteklemek için verilen [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md) nesne kullanabilirsiniz [SetValueAsStringWithError](../../../extensibility/debugger/reference/idebugproperty3-setvalueasstringwitherror.md) yöntemi — değeri bir dize olarak ifade edilebilir değilse. Aksi takdirde, özel bir arabirim oluşturmak için gerekli olur — bu uygulama ifade değerlendiricisi özel `DisplayValue` yöntemi — uygular aynı nesne üzerinde `IDebugProperty3` arabirimi. Bu özel arabirim rasgele boyutu veya karmaşıklık verileri değiştirme yöntemlerini sağlamanız.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugCustomViewer](../../../extensibility/debugger/reference/idebugcustomviewer.md)   
 [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md)   
 [SetValueAsStringWithError](../../../extensibility/debugger/reference/idebugproperty3-setvalueasstringwitherror.md)