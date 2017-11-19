---
title: "Sıralama, filtreleme ve gruplandırma (XML Şeması Gezgini) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4a914de0-9ffc-4526-9603-92e460e52513
caps.latest.revision: "2"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 84438dac0527b056e05a711866f2884c605a3525
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="sorting-filtering-and-grouping-xml-schema-explorer"></a>Sıralama, filtreleme ve gruplandırma (XML Şeması Gezgini)
Bu konu aracılığıyla kullanılabilir seçenekler açıklanmaktadır **sıralama, filtreleme ve gruplandırma seçeneklerini** XML Şeması Explorer araç çubuğundaki menüsü.  
  
## <a name="filter-options"></a>Filtre Seçenekleri  
 Aşağıdaki filtre seçenekleri kullanılabilir. Varsayılan olarak, **ad alanlarını göster** ve **şema dosyaları göster** seçenekleri seçilidir.  
  
-   **Ad alanlarını göster**.  
  
-   **Şema dosyaları göster**.  
  
-   **(Sıralı/seçim/tümü) Compositors Göster**.  
  
## <a name="sorting-options"></a>Sıralama seçenekleri  
 Aşağıdaki sıralama seçenekleri kullanılabilir. Varsayılan değer **türe göre sırala**. Sıralama ölçütü seçenekleri dosyaları ve ad alanları için geçerli değildir.  
  
-   **Türe Göre Sırala**.  
  
-   **Ada göre sırala**.  
  
-   **Belge sipariş**.  
  
### <a name="sort-by-type"></a>Türe göre sırala  
 Zaman **türe göre sırala** seçeneği seçildiğinde, genel düğümleri aşağıdaki düzende sıralanır. Düğümler, her grup alfabetik olarak sıralanır.  
  
1.  `import`düğümleri.  
  
2.  `include`düğümleri.  
  
3.  `redefine`düğümleri.  
  
4.  `attribute`düğümleri.  
  
5.  `attributeGroup`düğümleri.  
  
6.  `complexType`düğümleri.  
  
7.  `simpleType`düğümleri.  
  
8.  `element`düğümleri.  
  
9. `group`düğümleri.  
  
### <a name="sort-by-name"></a>Ada göre sırala  
 Zaman **ada göre sırala** seçeneği seçildiğinde, genel düğümleri aşağıdaki düzende sıralanır:  
  
1.  `import`düğümler (alfabetik sırada ad alanları).  
  
2.  `include`düğümler (alfabetik sırasına `schemaLocation` öznitelikleri).  
  
3.  `redefine`düğümler (alfabetik sırasına `schemaLocation` öznitelikleri).  
  
4.  Genel diğer düğümlere alfabetik sırada.  
  
### <a name="document-order"></a>Belge Sırası  
 **Belge sipariş** seçenek, kullanılabilir ne zaman **şema dosyaları göster** seçeneği işaretlidir. Zaman **belge sipariş** seçildiğinde, genel düğümleri şema dosyasındaki göründükleri sırada görüntülenir.  
  
## <a name="persisting-sortfilter-options"></a>Kalıcı sıralama/filtre seçenekleri  
 Sıralama, filtreleme ve Gruplama seçenekleri ayarları değişti zaman hangi çözüm ya da dosyaları açık olan her bir kullanıcı için kayıt defterine kaydedilir.