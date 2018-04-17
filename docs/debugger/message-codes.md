---
title: İleti kodları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- message codes
ms.assetid: 9f91f4e2-c1f1-4349-9f11-2fbbf59654be
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 96f980570bcbee7a26bf742556379899c0a88436
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="message-codes"></a>İleti Kodları
Gösterilen her ileti satırı [iletiler görünümü](../debugger/messages-view.md) 'P,' içeren kullanıcının,' ın,' veya 'R' kod. Bu kodları şu anlama gelir:  
  
|Kod|Açıklama|  
|----------|-------------|  
|P|İleti kuyruğa ile deftere **PostMessage** işlevi. İletinin ultimate değerlendirme ilgili hiçbir bilgi kullanılabilir.|  
|S|İleti ile gönderilmiş **SendMessage** işlevi. Başka bir deyişle, alıcı işler ve iletiyi döndürür kadar gönderen denetim gerekse değil. Alıcı bu nedenle, bir dönüş değeri gönderene geçirebilir.|  
|s|İleti gönderildi ancak güvenlik için dönüş değerini erişimi engeller.|  
|R|Her kullanıcının ' iletisi dönüş değeri listeler karşılık gelen bir 'R' (iade) satır bulunur. Bazen, bir ileti işleyicisi başka bir ileti gönderir başka bir deyişle, ileti çağrıları yerleştirilir.|