---
title: Arama ifadelerindeki mantıksal işleçler | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Help Viewer 2.0, logical operators in search
- logical operators in search [Help Viewer 2.0]
ms.assetid: 0c38ae7d-3e20-4d47-a020-9677cd285916
caps.latest.revision: 11
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 0cf55bbdc025b4aabd13f7ded72c2ea69386a61b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42634111"
---
# <a name="logical-operators-in-search-expressions"></a>Arama İfadelerindeki Mantıksal İşleçler
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [arama ifadelerindeki mantıksal işleçler](https://docs.microsoft.com/visualstudio/ide/logical-operators-in-search-expressions).  
  
Mantıksal işleçleri kullanarak aramanızı içerik için daha basit olanlardan daha karmaşık arama ifadeler oluşturarak iyileştirebilirsiniz. Aşağıdaki tabloda gösterildiği gibi arama sorgusu birden çok arama terimlerini birleştirilmelidir mantıksal işleçler belirtin.  
  
> [!IMPORTANT]
>  Mantıksal işleçler tanıması arama motoru için tüm büyük harfler girmeniz gerekir.  
  
|Aramak için|Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında|Örnek|Sonuç|  
|-------------------|---------|-------------|------------|  
|Her iki terim aynı konuda|AND|DIB ve paleti|Hem "DIB" ve "palet" içeren konulardır.|  
|Her iki terim bir konu başlığı|VEYA|Izgara veya vektör|"Tarama" veya "vektör" içeren konulardır.|  
|İkinci terimi aynı konuda olmadan ilk terimi|DEĞİL|"işletim sistemi" DOS değil|"İşletim sistemi" ancak değil "DOS" içeren konulardır.|  
|Birbirine yakın bir konu başlığı her iki terim|YAKIN|Kullanıcı yakın çekirdek|Yakınlık "çekirdek" içinde "kullanıcı" içeren konuların kapatın.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Tam metin arama ipuçları](../ide/full-text-search-tips.md)   
 [Bilgi bulun](../ide/locate-information.md)



