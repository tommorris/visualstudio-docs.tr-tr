---
title: IDebugEngine3::SetSymbolPath | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugEngine3::SetSymbolPath
helpviewer_keywords:
- IDebugEngine3::SetSymbolPath
ms.assetid: 47b48f84-8a96-401f-84df-0baa8a96d26e
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 8cc60a266a238ee8d3635637b907ce88933b29a0
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugengine3setsymbolpath"></a>IDebugEngine3::SetSymbolPath
Yol ya da hata ayıklama simgeleri aranır yollarını ayarlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT SetSymbolPath (  
   LPOLESTR            szSymbolSearchPath,  
   LPOLESTR            szSymbolCachePath,  
   LOAD_SYMBOLS_FLAGS  Flags  
);  
```  
  
```csharp  
int SetSymbolPath(  
   string                    szSymbolSearchPath,   
   string                    szSymbolCachePath,   
   enum_LOAD_SYMBOLS_FLAGS   Flags  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`szSymbolSearchPath`|[in] Sembol arama yolu veya yolları içeren dize. "Açıklamalar" ayrıntılı bilgi için bkz. Null olamaz.|  
|`szSymbolCachePath`|[in] Burada simgeleri önbelleğe alınabilir yerel yolu içeren dize. Null olamaz.|  
|`Flags`|[in] Kullanılmayan; her zaman 0 olarak ayarlayın.|  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, S_OK verir; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Dize `szSymbolSearchPath` simgelerini aramak için noktalı virgül ile ayrılmış bir veya daha fazla yolları listesidir. Bu yollar, yerel bir yol, UNC stili yolu veya bir URL olabilir. Bu yolları farklı türlerinin bir karışımını da olabilir. Yol UNC ise (örneğin, \\\Symserver\Symbols), hata ayıklama altyapısı yolu bir simge sunucuya ve bunları tarafından belirtilen yoldaki önbelleğe alma, o sunucudan simgeleri yük gerekir belirlemelisiniz sonra `szSymbolCachePath`.  
  
 Simge yolu, bir veya daha fazla önbellek konumu olarak de içerebilir. Önbellekleri en yüksek öncelik önbelleğiyle öncelik sırasına ilk listelenen ve ayrılmış * simgeler. Örneğin:  
  
```  
\\symbols\symbols;\\someotherserver\symbols;c:\symbols\httpsymbols*http://msdl.microsoft.com  
```  
  
 [LoadSymbols](../../../extensibility/debugger/reference/idebugengine3-loadsymbols.md) yöntemi simgelerin gerçek yükleme gerçekleştirir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [LoadSymbols](../../../extensibility/debugger/reference/idebugengine3-loadsymbols.md)   
 [IDebugEngine3](../../../extensibility/debugger/reference/idebugengine3.md)