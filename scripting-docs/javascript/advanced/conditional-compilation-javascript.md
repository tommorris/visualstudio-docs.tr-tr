---
title: "Koşullu derleme (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: ConditionalComp_JavaScript
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- conditional compilation, overview
- conditional compilation
ms.assetid: a843de4e-3aae-43cd-ad64-477dd00814a2
caps.latest.revision: "16"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6d6a5987b21afcab8c62a609dfba33f963d544de
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="conditional-compilation-javascript"></a>Koşullu Derleme (JavaScript)
Koşullu derleme sağlayan kullanımını yeni [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] özellikleri desteklemeyen önceki sürümlerle uyumluluk ödün olmadan dil özellikleri.  
  
> [!WARNING]
>  Koşullu derleme Internet Explorer'ın Internet Explorer 11'den önceki tüm sürümlerinde desteklenir. Internet Explorer 11 standartları modu ve buna başlangıç [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] uygulamaları, koşullu derleme desteklenmiyor.  
  
## <a name="statements"></a>Deyimler  
 Koşullu derleme kullanarak etkinleştirilirse `@cc_on` deyimi veya kullanarak bir `@if` veya `@set` deyimi. Yeni özellikleri kullanarak koşullu derleme bazı tipik kullanımları dahil [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)], bir komut dosyası hata ayıklama desteği katıştırma ve kod yürütmeyi izleme.  
  
 Koşullu derleme kodlarını her zaman açıklamalara ekleyin ki koşullu derlemeyi desteklemeyen ana bilgisayarlar (Netscape Navigator gibi) bunları görmezden gelsin. Aşağıda bir örnek vardır.  
  
```JavaScript  
/*@cc_on @*/  
/*@if (@_jscript_version >= 4)  
    alert("JavaScript version 4 or better");  
    @else @*/  
    alert("Conditional compilation not supported by this scripting engine.");  
/*@end @*/  
```  
  
 Bu örnek yalnızca koşullu derleme tarafından etkinleştirilmişse, kullanılan özel yorum ayırıcıları kullanır `@cc_on` deyimi. Koşullu derleme desteği olmayan komut dosyası altyapıları yalnızca koşullu derlemenin desteklenmediğini söyleyen bir ileti görürler.