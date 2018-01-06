---
title: "Nasıl yapılır: bir komut isteminden profil oluşturucu Karşılaştırma raporu oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 00548d16-eb5b-46f7-8a65-862f98a43831
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: b3eb863a53b1e03ca71db9c18a1d8188ef47b392
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-profiler-comparison-report-from-a-command-prompt"></a>Nasıl yapılır: Komut İsteminden Profil Oluşturucu Karşılaştırma Raporu Oluşturma
Oluşturabileceğiniz bir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] profil oluşturma araçları rapor iki profil oluşturma veri performans verilerini karşılaştırır (. VSP ya. VSPS) dosyaları. Rapor farklar, performans gerileme ve diğer bir profil oluşturma oturumu oluştu iyileştirmeleri gösterir. Rapordaki değerler delta ya da değişiklik, belirttiğiniz dosyanın ilk taban çizgisiyle sunar. Bu delta yeni analiz temel değerdir, eski değer sonuç değeri arasındaki fark belirleyerek hesaplanır. Profil Oluşturucu veri karşılaştırmaları temel işlevleri kodda, uygulama, satırları, yönerge işaretçileri (IP) ve türleri modülleri alabilir.  
  
 Tanımlayıcıları karşılaştırma kategorileri ve alanların listesi için aşağıdaki komutu yazın:  
  
 **VSPerfReport /querydifftables***VspFileName1* *VspFileName2*   
  
 Karşılaştırma raporu oluşturmak için aşağıdaki sözdizimini kullanın:  
  
 **VSPerfReport /diff** `VspFileName1` *VspFileName2* [**/**`Options`]  
  
 Aşağıdaki tablodaki seçenekleri ekleyebilirsiniz **VSPerfReport /diff** komut satırı.  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|**DiffThreshold:**[*değeri*]|Bu yüzdesi Eşik değerin altına ise farkı dikkate. Ayrıca, bu eşiğin altında olan değerleri yeni verilerle görünmez.|  
|**DiffTable:** *TableName*|Dosyaları karşılaştırmak için bu tabloyu kullanın. Varsayılan olarak, İşlevler tablosuna kullanılır. Listede bir tanımlayıcı belirtin **VSPerfReport /querydifftables**.|  
|**DiffColumn:** *ColumnName*|Bu sütun değerleri karşılaştırmak için kullanın. Varsayılan olarak, özel örnekler Yüzde sütunu kullanılır. Listede bir tanımlayıcı belirtin **VSPerfReport /querydifftables**.|