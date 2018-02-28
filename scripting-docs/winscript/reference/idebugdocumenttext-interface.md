---
title: Idebugdocumenttext arabirimi | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- IDebugDocumentText interface
ms.assetid: 242bad79-9c0a-4a30-879a-9f43db4e022b
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9522d1075cd796fb69f6abbc42adc2706a817fed
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="idebugdocumenttext-interface"></a>IDebugDocumentText Arabirimi
Hata ayıklama belge salt metin sürümü erişim sağlar. Bu arabirim aşağıdaki kuralları kullanır:  
  
-   Karakter konumlarını ve satır numaralarını sıfır tabanlı var.  
  
-   Karakter konumlarını karakter uzaklıkları gösterir; değil bayt veya gösterirler uzaklıkları word. Win32 için bir karakterin bir Unicode uzaklığı.  
  
 Kaynağından devralındı yöntemleri yanı sıra `IDebugDocument`, `IDebugDocumentText` arabirimi aşağıdaki yöntemleri sunar.  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[IDebugDocumentText::GetDocumentAttributes](../../winscript/reference/idebugdocumenttext-getdocumentattributes.md)|Belge özniteliklerini döndürür.|  
|[IDebugDocumentText::GetSize](../../winscript/reference/idebugdocumenttext-getsize.md)|Belgede satır sayısı ve karakter sayısını döndürür.|  
|[IDebugDocumentText::GetPositionOfLine](../../winscript/reference/idebugdocumenttext-getpositionofline.md)|Karakterin satırının ilk karakterine karşılık gelen döndürür.|  
|[IDebugDocumentText::GetLineOfPosition](../../winscript/reference/idebugdocumenttext-getlineofposition.md)|Verilen karakterin konumu için satır numarası ve isteğe bağlı olarak, karşılık gelen satır karakteri uzaklığını döndürür.|  
|[IDebugDocumentText::GetText](../../winscript/reference/idebugdocumenttext-gettext.md)|Karakter ve/veya bir karakterin aralığı ile ilişkili karakter özniteliklerini alır.|  
|[IDebugDocumentText::GetPositionOfContext](../../winscript/reference/idebugdocumenttext-getpositionofcontext.md)|Bir belge bağlamına karşılık gelen karakterin aralığını döndürür.|  
|[IDebugDocumentText::GetContextOfPosition](../../winscript/reference/idebugdocumenttext-getcontextofposition.md)|Sağlanan karakter konumu aralığına karşılık gelen bir belge bağlam nesnesi oluşturur.|