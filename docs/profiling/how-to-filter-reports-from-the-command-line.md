---
title: "Nasıl yapılır: komut satırından raporları filtreleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6e9b140f-b44f-4a5c-bd65-d868ddc94023
caps.latest.revision: "6"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ff4bae4f3071755149acdea49d312f8a9efcf31d
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-filter-reports-from-the-command-line"></a>Nasıl yapılır: Komut Satırından Raporları Filtreleme
Seçeneklerini kullanarak **VSPerfReport** komut, filtre belirli zaman diliminin profil oluşturma veri dosyası, raporları veya verileri bir veya daha fazla işlemler veya iş parçacığı kısıtlamak. Bu komut hakkında daha fazla bilgi için bkz: [VSPerfReport](../profiling/vsperfreport.md).  
  
|Seçenekler|Açıklama|  
|-------------|-----------------|  
|**StartTime:**[*değeri*]|Yalnızca değerden (milisaniye cinsinden.) toplanan verileri göster|  
|**EndTime:**[*değeri*]|Yalnızca değeri (milisaniye cinsinden.) önce toplanan verileri göster|  
|**FilterFile:**`VSPFFile`|Öğesinden oluşturulan bir filtre dosyasının konumunu belirtir **Visual Studio performans raporu** penceresi.|  
|**MsFilter:**[*StartTime, süre*]|Yalnızca verileri gösterir `StartTime` uzunluğu kadar `Duration` (milisaniye cinsinden.)|  
|**İşlem:**[*PID*]|Yalnızca belirtilen işlem verilerini gösterir.|  
|**İş parçacığı:**[*ThreadID*]|Yalnızca belirtilen iş parçacığı verileri gösterir.|  
|**İş parçacığı:**[*ThreadID, ProcessId*]|Yalnızca belirtilen işlemle ilişkili belirtilen iş parçacığı verileri gösterir.|