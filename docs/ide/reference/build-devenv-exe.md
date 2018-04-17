---
title: -Yapı (devenv.exe) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- builds [Team System], command-line
- /build Devenv switch
- Devenv, /build switch
- build Devenv switch
ms.assetid: ced21627-7653-455b-8821-3e31c6a448cf
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1cc01dac34723f2a587e76461d41a60361a72091
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="build-devenvexe"></a>/Build (devenv.exe)
Belirtilen çözüm yapılandırma dosyası kullanarak bir çözüm oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Devenv SolutionName /build SolnConfigName [/project ProjName [/projectconfig ProjConfigName]]  
```  
  
## <a name="arguments"></a>Arguments  
 `SolutionName`  
 Gerekli. Tam yol ve çözüm dosyasının adı.  
  
 `SolnConfigName`  
 Gerekli. Adlı çözümü oluşturmak için kullanılan çözüm yapılandırmasının adı `SolutionName`.  
  
 / Project `ProjName`  
 İsteğe bağlı. Yol ve çözüm içinde proje dosyasının adı. Gelen göreli bir yol girin `SolutionName` klasörü proje dosyası veya projenin görünen adı veya tam yolunu ve proje dosyasının adı.  
  
 / projectconfig `ProjConfigName`  
 İsteğe bağlı. Bir proje adını derleme oluştururken kullanılacak yapılandırma `/project` adlı.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu anahtarı ile aynı işlevi gerçekleştirir **yapı çözümü** tümleşik geliştirme ortamı (IDE) içinde menü komutu.  
  
 Çift tırnak işaretleri boşluk dizeler alın.  
  
 Derlemeleri hatalar dahil olmak üzere, ilgili özet bilgileri görüntülenebilir **komutu** penceresinde veya ile belirtilen herhangi bir günlük dosyasını `/out` geçin.  
  
 Bu komut, yalnızca son derlemeden bu yana değişmiş projeleri oluşturur. Bir çözümdeki tüm projeleri oluşturmak üzere kullanmak [/Rebuild (devenv.exe)](../../ide/reference/rebuild-devenv-exe.md).  
  
## <a name="example"></a>Örnek  
 Bu örnek proje derlemeler `CSharpConsoleApp`kullanarak `Debug` Proje yapı yapılandırması içinde `Debug` çözüm yapılandırmasını `MySolution`.  
  
```  
devenv "C:\Documents and Settings\someuser\My Documents\Visual Studio\Projects\MySolution\MySolution.sln" /build Debug /project "CSharpWinApp\CSharpWinApp.csproj" /projectconfig Debug   
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Projeler ve çözümler Visual Studio'da oluşturma ve temizleme](../../ide/building-and-cleaning-projects-and-solutions-in-visual-studio.md)   
 [Devenv komut satırı anahtarları](../../ide/reference/devenv-command-line-switches.md)   
 [/ Rebuild (devenv.exe)](../../ide/reference/rebuild-devenv-exe.md)   
 [/ Clean (devenv.exe)](../../ide/reference/clean-devenv-exe.md)   
 [/ Out (devenv.exe)](../../ide/reference/out-devenv-exe.md)