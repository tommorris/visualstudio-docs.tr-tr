---
title: IEEVisualizerService::GetCustomViewerList | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IEEVisualizerService::GetCustomViewerList
helpviewer_keywords: IEEVisualizerService::GetCustomViewerList method
ms.assetid: 249d26ca-914f-43af-a400-8162477223f4
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 733c4886fb1bc714526b655e5b4c3b395254e310
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="ieevisualizerservicegetcustomviewerlist"></a>IEEVisualizerService::GetCustomViewerList
Bu yöntem, bu hizmet bildiği türü görselleştiriciler listesini döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT GetCustomViewerList(  
   ULONG                celtSkip,  
   ULONG                celtRequested,  
   DEBUG_CUSTOM_VIEWER* rgViewers,  
   ULONG*               pceltFetched  
);  
```  
  
```csharp  
int GetCustomViewerList(  
   uint                  celtSkip,  
   uint                  celtRequested,  
   DEBUG_CUSTOM_VIEWER[] rgViewers,  
   out uint              pceltFetched  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `celtSkip`  
 [in] Görselleştiriciler atlamayı sayısı.  
  
 `celRequested`  
 [in] Alınacak görselleştiriciler sayısı (aynı zamanda boyutunu belirtir `rgViewers` array).  
  
 `rgViewers`  
 [içinde out] Dizi [DEBUG_CUSTOM_VIEWER](../../../extensibility/debugger/reference/debug-custom-viewer.md) doldurulacak yapıları.  
  
 `pceltFetched`  
 [out] Gerçekte alınan görselleştiriciler sayısı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 [GetCustomViewerList](../../../extensibility/debugger/reference/idebugproperty3-getcustomviewerlist.md) isteği bu yönteme desteğini bir parçası olarak türü görselleştiriciler geçirir. İfade değerlendirici Ayrıca aynı türde için özel görüntüleyiciler sağlarsa, uygun şekilde doldurulmuş genişletme ekleyebilirsiniz [DEBUG_CUSTOM_VIEWER](../../../extensibility/debugger/reference/debug-custom-viewer.md) bu özel görüntüleyiciler listesine yapılarında. Olduğundan emin olun [GetCustomViewerCount](../../../extensibility/debugger/reference/idebugproperty3-getcustomviewercount.md) bu ek görüntüleyiciler yansıtır.  
  
 Bkz: [türü Görselleştirici ve özel Görüntüleyicisi](../../../extensibility/debugger/type-visualizer-and-custom-viewer.md) görselleştiriciler ve görüntüleyicileri arasındaki farklar hakkında ayrıntılı bilgi için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IEEVisualizerService](../../../extensibility/debugger/reference/ieevisualizerservice.md)   
 [DEBUG_CUSTOM_VIEWER](../../../extensibility/debugger/reference/debug-custom-viewer.md)   
 [GetCustomViewerList](../../../extensibility/debugger/reference/idebugproperty3-getcustomviewerlist.md)   
 [GetCustomViewerCount](../../../extensibility/debugger/reference/idebugproperty3-getcustomviewercount.md)   
 [Türü Görselleştirici ve özel Görüntüleyicisi](../../../extensibility/debugger/type-visualizer-and-custom-viewer.md)