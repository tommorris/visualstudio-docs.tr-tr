---
title: Taşınabilir profil oluşturma veri dosyalarıyla komut satırından oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 2ceb63a7-b835-4988-b756-2afc3fcc4808
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: dd329df74c88f5edadef27444bf3b3c89ee1b30d
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="creating-portable-profiling-data-files-from-the-command-line"></a>Komut Satırından Taşınabilir Profil Oluşturma Veri Dosyaları Oluşturma
Profil oluşturma verilerini daha kolay paylaşımı yapmak için kullanabileceğiniz [VSPerfReport](../profiling/vsperfreport.md) profil .vsp dosyasına çalıştırmak için simgeleri eklemek için komut satırı aracı.  
  
 Daha küçüktür ve IDE içinde yüklemek daha hızlı bir şekilde önceden çözümlenen bir profil oluşturma veri (.vsps) dosyası da oluşturabilirsiniz.  
  
> [!NOTE]
>  Simge (.pdb) dosyaları için kullanılabilir olduğundan emin olun **VSPerfReport**. Daha fazla bilgi için bkz: [nasıl yapılır: simge dosyası konumlarını komut satırından belirtme](../profiling/how-to-specify-symbol-file-locations-from-the-command-line.md).  
>   
>  Yolu hakkında bilgi için **VSReport**, bkz: [komut satırı araçları yolunu belirtme](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).  
>   
>  Profil oluşturma verileri .vsps dosyasında filtrelenemez.  
  
### <a name="to-embed-the-symbols-for-a-profiling-run-into-a-profiling-data-vsp-file"></a>Bir profil bir profil oluşturma veri (.vsp) dosyasına çalıştırmak için simgeleri eklemek için  
  
-   Bir komut istemi penceresinde, aşağıdaki komutu yazın:  
  
     \<Yolu >**VSPerfReport \<** VSP Dosya > **/PackSymbols**  
  
     Varsayılan olarak, .vsps dosya .vsp dosyasının temel adı ile adlandırılır. Kullanarak bir diğer ad belirtebilirsiniz **çıkış** seçeneği.  
  
### <a name="to-create-a-summary-profiling-data-file"></a>Özet bir profil oluşturma veri dosyası oluşturmak için  
  
-   Bir komut istemi penceresinde, aşağıdaki komutu yazın:  
  
     \<Yolu >**VSPerfReport \<** VSP Dosya > **/SummaryFile** [**/çıktı:**\<dosya adı >]  
  
     Varsayılan olarak, .vsps dosya .vsp dosyasının temel adı ile adlandırılır. Kullanarak bir diğer ad belirtebilirsiniz **çıkış** seçeneği.