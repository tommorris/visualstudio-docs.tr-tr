---
title: "İleti kodları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: message codes
ms.assetid: 9f91f4e2-c1f1-4349-9f11-2fbbf59654be
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7a1e724c5c328c86398c43263b19980b5f464a39
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="message-codes"></a>İleti Kodları
Gösterilen her ileti satırı [iletiler görünümü](../debugger/messages-view.md) 'P,' içeren kullanıcının,' ın,' veya 'R' kod. Bu kodları şu anlama gelir:  
  
|Kod|Açıklama|  
|----------|-------------|  
|P|İleti kuyruğa ile deftere **PostMessage** işlevi. İletinin ultimate değerlendirme ilgili hiçbir bilgi kullanılabilir.|  
|S|İleti ile gönderilmiş **SendMessage** işlevi. Başka bir deyişle, alıcı işler ve iletiyi döndürür kadar gönderen denetim gerekse değil. Alıcı bu nedenle, bir dönüş değeri gönderene geçirebilir.|  
|s|İleti gönderildi ancak güvenlik için dönüş değerini erişimi engeller.|  
|R|Her kullanıcının ' iletisi dönüş değeri listeler karşılık gelen bir 'R' (iade) satır bulunur. Bazen, bir ileti işleyicisi başka bir ileti gönderir başka bir deyişle, ileti çağrıları yerleştirilir.|