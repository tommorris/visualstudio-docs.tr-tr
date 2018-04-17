---
title: -(Devenv.exe) yeniden | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- Devenv, /rebuild switch
- rebuild Devenv switch (/rebuild)
- projects [Visual Studio], rebuilding
- /rebuild Devenv switch
- applications [Visual Studio], rebuilding
ms.assetid: c5a8a4bf-0e2b-46eb-a44a-8aeb29b92c32
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0daaba0ddb30b2fe277d2ef1b51ee4c82ff50366
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="rebuild-devenvexe"></a>/Rebuild (devenv.exe)
Temizler ve belirtilen çözüm yapılandırması oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
devenv SolutionName /rebuild SolnConfigName [/project ProjName] [/projectconfig ProjConfigName]  
```  
  
## <a name="arguments"></a>Arguments  
 `SolnConfigName`  
 Gerekli. Adlı çözümü yeniden oluşturmak için kullanılan çözüm yapılandırmasının adı `SolutionName`.  
  
 `SolutionName`  
 Gerekli. Tam yol ve çözüm dosyasının adı.  
  
 / Project `ProjName`  
 İsteğe bağlı. Yol ve çözüm içinde proje dosyasının adı. Gelen göreli bir yol girin `SolutionName` klasörü proje dosyası veya projenin görünen adı veya tam yolunu ve proje dosyasının adı.  
  
 / projectconfig `ProjConfigName`  
 İsteğe bağlı. Bir proje adını derleme yeniden oluştururken kullanılacak yapılandırma `/project` adlı.  
  
## <a name="remarks"></a>Açıklamalar  
  
-   Bu anahtarı ile aynı işlevi gerçekleştirir **çözümü yeniden derle** tümleşik geliştirme ortamı (IDE) içinde menü komutu.  
  
-   Çift tırnak işaretleri boşluk dizeler alın.  
  
-   İlgili özet bilgileri temizler ve hatalar da dahil olmak üzere derlemeleri görüntülenebilir **komutu** penceresinde veya ile belirtilen herhangi bir günlük dosyasını `/out` geçin.  
  
## <a name="example"></a>Örnek  
 Bu örnek temizler ve projeyi yeniden oluşturur `CSharpWinApp`kullanarak `Debug` Proje yapı yapılandırması içinde `Debug` çözüm yapılandırmasını `MySolution`.  
  
```  
devenv "C:\Documents and Settings\someuser\My Documents\Visual Studio\Projects\MySolution\MySolution.sln" /rebuild Debug /project "CSharpWinApp\CSharpWinApp.csproj" /projectconfig Debug   
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Devenv komut satırı anahtarları](../../ide/reference/devenv-command-line-switches.md)   
 [/ Yapı (devenv.exe)](../../ide/reference/build-devenv-exe.md)   
 [/ Clean (devenv.exe)](../../ide/reference/clean-devenv-exe.md)   
 [/ Out (devenv.exe)](../../ide/reference/out-devenv-exe.md)