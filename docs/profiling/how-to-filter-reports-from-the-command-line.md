---
title: 'Nasıl yapılır: komut satırından raporları filtreleme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 6e9b140f-b44f-4a5c-bd65-d868ddc94023
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0591b646c8311004d9c08b2fb1a9fcdf2ab1908a
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="how-to-filter-reports-from-the-command-line"></a>Nasıl yapılır: Komut Satırından Raporları Filtreleme
Seçeneklerini kullanarak **VSPerfReport** komut, filtre belirli zaman diliminin profil oluşturma veri dosyası, raporları veya verileri bir veya daha fazla işlemler veya iş parçacığı kısıtlamak. Bu komut hakkında daha fazla bilgi için bkz: [VSPerfReport](../profiling/vsperfreport.md).  
  
|Seçenekler|Açıklama|  
|-------------|-----------------|  
|**StartTime:**[*değeri*]|Yalnızca değerden (milisaniye cinsinden.) toplanan verileri göster|  
|**EndTime:**[*değeri*]|Yalnızca değeri (milisaniye cinsinden.) önce toplanan verileri göster|  
|**FilterFile:** `VSPFFile`|Öğesinden oluşturulan bir filtre dosyasının konumunu belirtir **Visual Studio performans raporu** penceresi.|  
|**MsFilter:**[*StartTime, süre*]|Yalnızca verileri gösterir `StartTime` uzunluğu kadar `Duration` (milisaniye cinsinden.)|  
|**İşlem:**[*PID*]|Yalnızca belirtilen işlem verilerini gösterir.|  
|**İş parçacığı:**[*ThreadID*]|Yalnızca belirtilen iş parçacığı verileri gösterir.|  
|**İş parçacığı:**[*ThreadID, ProcessId*]|Yalnızca belirtilen işlemle ilişkili belirtilen iş parçacığı verileri gösterir.|