---
title: IDebugBeforeSymbolSearchEvent2 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IDebugBeforeSymbolSearchEvent2 interface
ms.assetid: 679fd7b1-765a-41a8-a046-63240c09a499
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d6ac247054a5048a7e2354f29415e203e03c7aaa
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42629192"
---
# <a name="idebugbeforesymbolsearchevent2"></a>IDebugBeforeSymbolSearchEvent2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugBeforeSymbolSearchEvent2](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugbeforesymbolsearchevent2).  
  
Hata ayıklama altyapısı (DE) Bu arabirim oturum hata ayıklama Yöneticisi (SDM) durumu ayarlamak için Sembol yükleri sırasında iletisi gönderir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDebugBeforeSymbolSearchEvent2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Uygulayanlar için Notlar  
 Durum Çubuğu iletisini sembol yükleri sırasında ayarlamanız gerekir, bu arabirim DE uygular. Bu arabirim, birlikte çalışmak veya bir betik yorumlayıcılarını parçası olan hata ayıklama motoru tarafından uygulanır. [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) arabirim uygulandığında, bu arabirimle aynı nesne üzerinde (SDM kullanan **QueryInterface** erişimi **IDebugEvent2** arabirimi).  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 KODU oluşturur ve Durum Çubuğu iletisini sembol yükleri sırasında ayarlamanız gerekir, bu olay nesneyi gönderir. Olay kullanılarak gönderilen [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) ayıklanan programa eklendiğinde SDM tarafından sağlanan geri çağırma işlevi.  
  
## <a name="methods"></a>Yöntemler  
 Aşağıdaki tabloda yöntemlerini gösterilmektedir `IDebugBeforeSymbolSearchEvent2`.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[GetModuleName](../../../extensibility/debugger/reference/idebugbeforesymbolsearchevent2-getmodulename.md)|Şu anda hata ayıklama gerçekleştirilen modül adını alır.|  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: Msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll

