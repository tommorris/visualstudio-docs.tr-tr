---
title: -Out (devenv.exe) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- errors [Visual Studio], builds
- Devenv, /out switch
- builds [Visual Studio], logs
- error logs [Visual Studio], command-line build errors
- error logs [Visual Studio]
- /out Devenv switch
- out Devenv switch
- builds [Visual Studio], errors
- output files, build errors
ms.assetid: 9002d8c2-36d4-451c-b489-8f01932f31f7
caps.latest.revision: "11"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 891204811a0c27471e8ab4be315da14be4b80794
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="out-devenvexe"></a>/Out (devenv.exe)
Depolamak ve çalıştırırken, yapı, yeniden, veya bir çözüm dağıtma hataları görüntülemek için bir dosyayı belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
devenv /out FileName  
```  
  
## <a name="arguments"></a>Arguments  
 `FileName`  
 Gerekli. Yürütülebilir bir dosya derlerken hataları almak için dosyanın adını ve yolunu.  
  
## <a name="remarks"></a>Açıklamalar  
 Dosya var olmayan bir dosya adı belirtilirse, otomatik olarak oluşturulur. Dosya zaten mevcutsa, sonuçları dosyasının mevcut içerikleri eklenir.  
  
 Komut satırı derleme hataları görüntülenir **komutu** penceresini açın ve çözüm Oluşturucusu'nu görüntülemek **çıkış** penceresi. Katılımsız derlemeleri çalıştırıyorsanız ve sonuçları görmek gereken bu kullanışlı bir seçenektir.  
  
## <a name="example"></a>Örnek  
 Bu örnekte çalışan `MySolution` ve hataları dosyaya yazar `MyErrorLog.txt`.  
  
```  
devenv /run "C:\Documents and Settings\someuser\My Documents\Visual Studio\Projects\MySolution\MySolution.sln" /out "C:\MyErrorLog.txt"  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Devenv komut satırı anahtarları](../../ide/reference/devenv-command-line-switches.md)   
 [/ Çalıştır (devenv.exe)](../../ide/reference/run-devenv-exe.md)   
 [/ Yapı (devenv.exe)](../../ide/reference/build-devenv-exe.md)   
 [/ Rebuild (devenv.exe)](../../ide/reference/rebuild-devenv-exe.md)   
 [/ (Devenv.exe) dağıtma](../../ide/reference/deploy-devenv-exe.md)