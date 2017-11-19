---
title: "Sayfa dosyası sekmesi, işlem özellikleri iletişim kutusu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Process properties for Windows NT
ms.assetid: daf41a06-8a55-48f6-95f5-49a8416bd308
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0bf5215e7a6d4c4a4a0dac37a9bde2b15fb8f19a
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="page-file-tab-process-properties-dialog-box"></a>Sayfa Dosyası Sekmesi, İşlem Özellikleri İletişim Kutusu
Kullanım **sayfa dosyası** sekmesinde bir işlemin disk belleği dosyasını inceleyin. Görüntülenecek [işlem özellikleri iletişim kutusu](../debugger/process-properties-dialog-box.md), odağı taşımak bir [işlemler görünümü](../debugger/processes-view.md) penceresi. Ağaçta herhangi bir işlem düğümü seçin ve ardından **özellikleri** gelen **Görünüm** menüsü.  
  
 Aşağıdaki ayarlar kullanılabilir **sayfa dosyası** sekmesi:  
  
|Giriş|Açıklama|  
|-----------|-----------------|  
|**Disk belleği bayt**|Bu işlem disk belleği dosyasındaki kullanarak sayfa geçerli sayısı. Disk belleği dosyası sayfa işlem tarafından kullanılan ancak diğer dosyalar bulunmayan veri depolar. Disk belleği dosyası tüm işlemler tarafından kullanılan ve diğer işlemler çalışırken disk belleği dosyası alanı yetersizliği hatalara neden olabilir.|  
|**En yüksek disk belleği dosyası bayt**|Bu işlem disk belleği dosyasında kullanılan sayfa maksimum sayısı.|  
|**Sayfa hataları**|Bu işlemde çalışan iş parçacıkları tarafından sayfa hatalarının sayısı. Bir iş parçacığı çalışma ana bellekte kümesinde olmayan bir sanal bellek sayfasına başvurduğunda bir sayfa hatası oluşur. Bekleme listede ise, bu nedenle, sayfanın diskten alınmayacak ve bu nedenle ana bellek içinde zaten veya bunu bir başkası tarafından kullanılıp kullanılmadığını işlem sayfası paylaşılan ile.|