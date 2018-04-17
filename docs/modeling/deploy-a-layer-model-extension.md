---
title: Katman modeli uzantısı dağıtma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- dependency diagrams, deploying extensions
- layer models, deploying extensions
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 95cfb5fa4764c53c14e5884cf41165f61a063337
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="deploy-a-layer-model-extension"></a>Katman modeli uzantısı dağıtma
Diğer kullanıcılar için Visual Studio, Visual Studio kullanarak oluşturduğunuz uzantıları modelleme katman yükleyebilirsiniz.  
  
## <a name="installing-your-extension"></a>Uzantınızı yükleme  
 Uzantınızı diğer bilgisayarlara yükleyebilirsiniz bir dosyaya VSIX derlenir. Uzantıyı Visual Studio ana örneğinde kullanılabilmesi için geliştirme bilgisayarınızda da yükleyebilirsiniz.  
  
#### <a name="to-install-the-extension"></a>Uzantıyı yüklemek için  
  
1.  İçeren projedeki **source.vsix.manifest**, açık **bin\\ \***  dosya Gezgini'nde.  
  
2.  Kopya  **\*.vsix** uzantıyı yüklemek istediğiniz bilgisayara dosya.  
  
3.  Hedef bilgisayarda *.vsix dosyasına Windows Gezgini'nde çift tıklayın.  
  
     VSIX yükleyici açılır.  
  
#### <a name="to-uninstall-the-extension"></a>Uzantıyı kaldırmak için  
  
1.  Visual Studio'da üzerinde **Araçları** menüsünde tıklatın **Uzantılar ve güncelleştirmeler**.  
  
2.  Uzantı adına tıklayın ve ardından **kaldırma**.  
  
## <a name="installing-an-extension-on-a-team-foundation-build-server"></a>Team Foundation Yapı sunucuda uzantı yükleme  
 [!INCLUDE[esprbuild](../misc/includes/esprbuild_md.md)] Sunucu normal olarak Visual Studio yüklü değil ve çift tıklatarak VSIX şekilde yükleyemezsiniz. Yüklemesini [!INCLUDE[esprbuild](../misc/includes/esprbuild_md.md)] bazı bileşenleri içeren bir VSIX uzantısının çalışması için izin verilir, ancak uzantı el ile yüklemeniz gerekir.  
  
#### <a name="to-install-your-layer-extension-on-a-includeesprbuildmiscincludesesprbuildmdmd-server"></a>Katman uzantınızı yüklemek için bir [!INCLUDE[esprbuild](../misc/includes/esprbuild_md.md)] sunucusu  
  
1.  Kopya **.vsix** geliştirme bilgisayarınıza dosyalarından [!INCLUDE[esprbuild](../misc/includes/esprbuild_md.md)] bilgisayar.  
  
     VSIX dosyasını aşağıdaki konumlardan birinde koyun:  
  
    -   Tüm kullanıcılar ve hizmetlerini yüklemek için:  
  
         %ProgramFiles%\Microsoft visual Studio [sürüm] \Common7\IDE\Extensions\Microsoft  
  
    -   Çalıştıran ağ hizmeti için yüklemek için [!INCLUDE[esprbuild](../misc/includes/esprbuild_md.md)]:  
  
         %WinDir%\ServiceProfiles\NetworkService\AppData\Local\Microsoft\VisualStudio\\[version]\Extensions\Microsoft  
  
    -   Yapılandırdıysanız [!INCLUDE[esprbuild](../misc/includes/esprbuild_md.md)] belirli bir kullanıcı olarak etkileşimli modda çalıştırmak için o kullanıcı için yükleyebilirsiniz:  
  
         %LocalAppData%\Microsoft\VisualStudio\\[sürüm] \Extensions\Microsoft  
  
        > [!NOTE]
        >  % LocalAppData olan genellikle *DriveName*: kullanıcıların*kullanıcıadı*AppDataLocal.  
  
2.  Aynı konumda bir klasöre her VSIX dosyasını genişletin:  
  
    1.  Dosya adı uzantısını değiştirmek **.vsix** için **.zip**.  
  
    2.  .zip dosyasını bir klasöre içeriğini ayıklayın.  
  
    3.  .Zip dosyasını silin  
  
3.  Yeniden [!INCLUDE[esprbuild](../misc/includes/esprbuild_md.md)].
