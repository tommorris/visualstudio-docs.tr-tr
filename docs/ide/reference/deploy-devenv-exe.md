---
title: -Dağıtma (devenv.exe) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- Devenv, /deploy switch
- deploy Devenv switch
- deploying applications [Visual Studio], after build
- /deploy Devenv switch
ms.assetid: e47c8723-df08-4645-aa2d-0c956e7ccca2
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: dee247f9c948ae5a5d0ac6926679b7849c4c1fbc
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="deploy-devenvexe"></a>/Deploy (devenv.exe)
Bir çözüm oluşturma veya yeniden oluşturma sonra dağıtır. Yalnızca yönetilen kod projeler için geçerlidir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
devenv SolutionName /deploy SolnConfigName [/project ProjName] [/projectconfig ProjConfigName] [/out LogFileName]  
```  
  
## <a name="arguments"></a>Arguments  
 `SolnConfigName`  
 Gerekli. Adlı çözümü oluşturmak için kullanılan çözüm yapılandırmasının adı `SolutionName`.  
  
 `SolutionName`  
 Gerekli. Tam yol ve çözüm dosyasının adı.  
  
 / Project `ProjName`  
 İsteğe bağlı. Yol ve çözüm içinde proje dosyasının adı. Gelen göreli bir yol girin `SolutionName` klasörü proje dosyası veya projenin görünen adı veya tam yolunu ve proje dosyasının adı.  
  
 / projectconfig `ProjConfigName`  
 İsteğe bağlı. Bir proje adını derleme oluştururken kullanılacak yapılandırma `/project` adlı.  
  
## <a name="remarks"></a>Açıklamalar  
 Belirtilen proje dağıtım projesi olması gerekir. Dağıtılacak oluşturulduğunu proje geçirildiğinde belirtilen proje bir dağıtım projesi değilse, bir hata ile başarısız olur.  
  
 Çift tırnak işaretleri boşluk dizeler alın.  
  
 Derlemeleri hatalar dahil olmak üzere, ilgili özet bilgileri görüntülenebilir **komutu** penceresinde veya ile belirtilen herhangi bir günlük dosyasını `/out` geçin.  
  
## <a name="example"></a>Örnek  
 Bu örnek projesini dağıtır `CSharpConsoleApp`kullanarak `Release` Proje yapı yapılandırması içinde `Release` çözüm yapılandırmasını `MySolution`.  
  
```  
devenv "C:\Documents and Settings\someuser\My Documents\Visual Studio\Projects\MySolution\MySolution.sln" /deploy Release /project "CSharpWinApp\CSharpWinApp.csproj" /projectconfig Release   
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Devenv komut satırı anahtarları](../../ide/reference/devenv-command-line-switches.md)   
 [/ Project (devenv.exe)](../../ide/reference/project-devenv-exe.md)   
 [/ Yapı (devenv.exe)](../../ide/reference/build-devenv-exe.md)   
 [/ Clean (devenv.exe)](../../ide/reference/clean-devenv-exe.md)   
 [/ Rebuild (devenv.exe)](../../ide/reference/rebuild-devenv-exe.md)   
 [/ Out (devenv.exe)](../../ide/reference/out-devenv-exe.md)