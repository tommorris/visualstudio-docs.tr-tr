---
title: -Runexit (devenv.exe) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- runexit Devenv switch
- Devenv, /runexit switch
- /runexit Devenv switch
ms.assetid: bfc94875-5fc0-4110-b961-d59c0b403790
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 7e52d305fd58239b13fe3cc0aaab0fc6a19522c7
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="runexit-devenvexe"></a>/Runexit (devenv.exe)
Derler ve belirtilen proje ve çözüm çalıştırır ve tümleşik geliştirme ortamı (IDE) kapatır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
devenv /runexit {SolutionName|ProjectName}  
```  
  
## <a name="arguments"></a>Arguments  
 `SolutionName`  
 Gerekli. Tam yol ve çözüm dosya adı.  
  
 `ProjectName`  
 Gerekli. Proje dosyası adını ve tam yolu.  
  
## <a name="remarks"></a>Açıklamalar  
 Derler ve belirtilen proje ve çözüm etkin çözüm yapılandırması için belirtilen ayarlara göre çalıştırır. IDE proje sırasında bu anahtarı en aza indirir çözümü çalıştırın ve sonra projeyi IDE kapatır veya çözüm çalışması tamamlandıktan.  
  
-   Çift tırnak işaretleri boşluk dizeler alın.  
  
-   Hatalar dahil olmak üzere Özet bilgileri görüntülenebilir **komutu** penceresinde veya ile belirtilen herhangi bir günlük dosyasını `/out` geçin.  
  
## <a name="example"></a>Örnek  
 Bu örnek çözümü çalıştıran `MySolution` simge durumuna küçültülmüş IDE'de etkin Dağıtım Yapılandırması'nı kullanarak ve IDE kapatır.  
  
```  
devenv /runexit "C:\Documents and Settings\someuser\My Documents\Visual Studio\Projects\MySolution\MySolution.sln"  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Devenv komut satırı anahtarları](../../ide/reference/devenv-command-line-switches.md)   
 [/ Çalıştır (devenv.exe)](../../ide/reference/run-devenv-exe.md)   
 [/ Yapı (devenv.exe)](../../ide/reference/build-devenv-exe.md)   
 [/ Rebuild (devenv.exe)](../../ide/reference/rebuild-devenv-exe.md)   
 [/ Out (devenv.exe)](../../ide/reference/out-devenv-exe.md)