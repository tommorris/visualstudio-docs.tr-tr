---
title: İşareti | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1d72cef3-bb09-4bbb-8864-6ea0ab623ff9
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fb1b5d35e11cd3317db473330d908e0f7300d576
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42696054"
---
# <a name="mark"></a>İşaret
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [işareti](https://docs.microsoft.com/visualstudio/profiling/mark).  
  
VSPerfCmd.exe **işareti** seçeneği, profil oluşturma veri dosyası içinde belirtilen bilgileri ekler. Mark, profil oluşturucunun UI işareti rapor görünümü veya ayrı bir VSPerfReport raporlarında listelenebilir. **İşareti** başlangıç ve bitiş noktalarını rapor ve görünümü filtreleri belirtmek için kullanılabilir.  
  
 **İşareti** seçeneği, komut satırında belirtilen tek seçenek olması gerekir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
VSPerfCmd.exe /Mark:MarkID,[MarkName]  
```  
  
#### <a name="parameters"></a>Parametreler  
 `MarkID`  
 Profil Oluşturucu görünümleri ve raporları işaret kimliği olarak listelenen bir kullanıcı tanımlı bir tamsayı. `MarkID` benzersiz olması gerekmez.  
  
 `MarkName`  
 (İsteğe bağlı) Profil Oluşturucu görünümleri ve raporları işareti adı olarak listelenen bir kullanıcı tanımlı bir dize. Varsa `MarkName` belirtilmezse, işareti listenin işareti adı alanı boş değil. Boşluk veya tırnak işaretleri ("/") eğik iletme dizeleri alın.  
  
## <a name="example"></a>Örnek  
 Bu örnek, işareti 123 kimliği ve "TestMark" işareti adını ekler.  
  
```  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp  
VSPerfCmd.exe /Launch:TestApp.exe  
VSPerfCmd.exe /Mark:123,TestMark  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [Bağımsız uygulamaların profilini oluşturma](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [ASP.NET Web uygulamalarında profil oluşturma](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profil oluşturma hizmetleri](../profiling/command-line-profiling-of-services.md)



