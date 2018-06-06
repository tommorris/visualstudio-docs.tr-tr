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
ms.openlocfilehash: 25f2faf1be7f2e8ff5c96eca16ef2de9be2514db
ms.sourcegitcommit: 1b9c1e333c2f096d35cfc77e846116f8e5054557
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/06/2018
ms.locfileid: "34815858"
---
# <a name="create-portable-profiling-data-files-from-the-command-line"></a>Komut satırından taşınabilir profil oluşturma veri dosyaları oluşturma
Profil oluşturma verilerini daha kolay paylaşımı yapmak için kullanabileceğiniz [VSPerfReport](../profiling/vsperfreport.md) profil içine çalıştırmak için simgeleri eklemek için komut satırı aracı. *Vsp* dosya.  
  
 Önceden çözümlenen bir profil verileri de oluşturabilirsiniz (. *vsps*) daha küçük olan ve IDE içinde yüklemek daha hızlı bir şekilde dosyası.  
  
> [!NOTE]
>  Simgenin emin olun (. *pdb*) dosyaları için kullanılabilir **VSPerfReport**. Daha fazla bilgi için bkz: [nasıl yapılır: simge dosyası konumlarını komut satırından belirtme](../profiling/how-to-specify-symbol-file-locations-from-the-command-line.md).  
>   
>  Yolu hakkında bilgi için **VSReport**, bkz: [komut satırı araçları yolunu belirtme](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).  
>   
>  Profil oluşturma verileri bir. *vsps* dosya olamaz filtre.  
  
### <a name="to-embed-the-symbols-for-a-profiling-run-into-a-profiling-data-vsp-file"></a>Bir profil bir profil oluşturma verilerini çalıştırmak için simgeleri eklemek için (. *Vsp*) dosyası  
  
-   Bir komut istemi penceresinde, aşağıdaki komutu yazın:  
  
     \<Yolu >**VSPerfReport \<** VSP Dosya > **/PackSymbols**  
  
     Varsayılan olarak,. *vsps* dosya temel adı ile adlandırılır. *Vsp* dosya. Kullanarak bir diğer ad belirtebilirsiniz **çıkış** seçeneği.  
  
### <a name="to-create-a-summary-profiling-data-file"></a>Özet bir profil oluşturma veri dosyası oluşturmak için  
  
-   Bir komut istemi penceresinde, aşağıdaki komutu yazın:  
  
     \<Yolu >**VSPerfReport \<** VSP Dosya > **/SummaryFile** [**/çıktı:**\<dosya adı >]  
  
     Varsayılan olarak,. *vsps* dosya temel adı ile adlandırılır. *Vsp* dosya. Kullanarak bir diğer ad belirtebilirsiniz **çıkış** seçeneği.