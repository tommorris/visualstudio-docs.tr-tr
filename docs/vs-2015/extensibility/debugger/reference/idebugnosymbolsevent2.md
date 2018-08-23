---
title: IDebugNoSymbolsEvent2 | Microsoft Docs
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
- IDebugNoSymbolsEvent2 interface
ms.assetid: f6fb6388-47f6-4385-9ad5-95d62f9a7592
caps.latest.revision: 7
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: e1dec7ef8a17a078bc94f41e3270f17ae2cb438a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42691781"
---
# <a name="idebugnosymbolsevent2"></a>IDebugNoSymbolsEvent2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugNoSymbolsEvent2](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugnosymbolsevent2).  
  
Sinyaller [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] hata ayıklayıcı semboller için başlatılan yürütülebilir dosya bulunamadı, kullanıcıyı uyarmak için kullanıcı Arabirimi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDebugNoSymbolsEvent2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Uygulayanlar için Notlar  
 Hata ayıklama motoru tarafından uygulanan ve tarafından tüketilen [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] hata ayıklayıcı, kullanıcı Arabirimi.  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: Msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll

