---
title: Profil oluşturma veri dosyaları komut satırından taşınabilir oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2ceb63a7-b835-4988-b756-2afc3fcc4808
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 314dc97e5881949ee69131576932db1865969b2c
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42695436"
---
# <a name="creating-portable-profiling-data-files-from-the-command-line"></a>Komut Satırından Taşınabilir Profil Oluşturma Veri Dosyaları Oluşturma
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [oluşturma taşınabilir profil oluşturma veri dosyaları komut satırından](https://docs.microsoft.com/visualstudio/profiling/creating-portable-profiling-data-files-from-the-command-line).  
  
Profil oluşturma verilerini daha kolay paylaşım yapmak için kullanabileceğiniz [VSPerfReport](../profiling/vsperfreport.md) bir .vsp dosyasına profil oluşturma için simgeleri eklemek için komut satırı aracı.  
  
 Daha küçüktür ve IDE'de yük daha hızlı bir şekilde önceden çözümlenmiş bir profil oluşturma veri (.vsps) dosyası da oluşturabilirsiniz.  
  
> [!NOTE]
>  Sembol (.pdb) dosyalarının kullanılabilir olduğundan emin olun **VSPerfReport**. Daha fazla bilgi için [nasıl yapılır: komut satırından sembol dosyası konumu belirtin](../profiling/how-to-specify-symbol-file-locations-from-the-command-line.md).  
>   
>  Yolu hakkında bilgi için **VSReport**, bkz: [komut satırı araçları yolunu belirtme](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).  
>   
>  Profil oluşturma verilerinin bir .vsps dosyasında filtrelenemez.  
  
### <a name="to-embed-the-symbols-for-a-profiling-run-into-a-profiling-data-vsp-file"></a>Bir profil oluşturma veri (.vsp) dosyasına bir profil oluşturma için simgeleri eklemek için  
  
-   Bir komut istemi penceresinde, aşağıdaki komutu yazın:  
  
     \<Yolu >**VSPerfReport \<** VSP dosyası > **packsymbols**  
  
     Varsayılan olarak, .vsp dosyasının temel adı ile .vsps dosyası olarak adlandırılır. Kullanarak bir diğer ad belirtebilirsiniz **çıkış** seçeneği.  
  
### <a name="to-create-a-summary-profiling-data-file"></a>Özet bir profil oluşturma veri dosyasını oluşturmak için  
  
-   Bir komut istemi penceresinde, aşağıdaki komutu yazın:  
  
     \<Yolu >**VSPerfReport \<** VSP dosyası > **/summaryfile** [**/Output:**\<dosya adı >]  
  
     Varsayılan olarak, .vsp dosyasının temel adı ile .vsps dosyası olarak adlandırılır. Kullanarak bir diğer ad belirtebilirsiniz **çıkış** seçeneği.



