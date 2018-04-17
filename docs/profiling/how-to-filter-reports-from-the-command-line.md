---
title: 'Nasıl yapılır: komut satırından raporları filtreleme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
ms.assetid: 6e9b140f-b44f-4a5c-bd65-d868ddc94023
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4b95a4c614579f7248d483fc04c00b30f953ff9a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
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