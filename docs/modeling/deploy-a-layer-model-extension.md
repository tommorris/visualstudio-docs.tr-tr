---
title: "Katman modeli uzantısı dağıtma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- dependency diagrams, deploying extensions
- layer models, deploying extensions
ms.assetid: 00a4675b-d20e-487e-8fd5-be2b1e0ba238
caps.latest.revision: "27"
author: alexhomer1
ms.author: ahomer
manager: douge
ms.openlocfilehash: d019e602c5bf198df03a50034c2ed29519d16e53
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
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
 [!INCLUDE[esprbuild](../misc/includes/esprbuild_md.md)]Sunucu normal olarak Visual Studio yüklü değil ve çift tıklatarak VSIX şekilde yükleyemezsiniz. Yüklemesini [!INCLUDE[esprbuild](../misc/includes/esprbuild_md.md)] bazı bileşenleri içeren bir VSIX uzantısının çalışması için izin verilir, ancak uzantı el ile yüklemeniz gerekir.  
  
#### <a name="to-install-your-layer-extension-on-a-includeesprbuildmiscincludesesprbuildmdmd-server"></a>Katman uzantınızı yüklemek için bir [!INCLUDE[esprbuild](../misc/includes/esprbuild_md.md)] sunucusu  
  
1.  Kopya **.vsix** geliştirme bilgisayarınıza dosyalarından [!INCLUDE[esprbuild](../misc/includes/esprbuild_md.md)] bilgisayar.  
  
     VSIX dosyasını aşağıdaki konumlardan birinde koyun:  
  
    -   Tüm kullanıcılar ve hizmetlerini yüklemek için:  
  
         %ProgramFiles%\Microsoft visual Studio [sürüm] \Common7\IDE\Extensions\Microsoft  
  
    -   Çalıştıran ağ hizmeti için yüklemek için [!INCLUDE[esprbuild](../misc/includes/esprbuild_md.md)]:  
  
         %WinDir%\ServiceProfiles\NetworkService\AppData\Local\Microsoft\VisualStudio\\[sürüm] \Extensions\Microsoft  
  
    -   Yapılandırdıysanız [!INCLUDE[esprbuild](../misc/includes/esprbuild_md.md)] belirli bir kullanıcı olarak etkileşimli modda çalıştırmak için o kullanıcı için yükleyebilirsiniz:  
  
         %LocalAppData%\Microsoft\VisualStudio\\[sürüm] \Extensions\Microsoft  
  
        > [!NOTE]
        >  % LocalAppData olan genellikle *DriveName*: kullanıcıların*kullanıcıadı*AppDataLocal.  
  
2.  Aynı konumda bir klasöre her VSIX dosyasını genişletin:  
  
    1.  Dosya adı uzantısını değiştirmek **.vsix** için **.zip**.  
  
    2.  .zip dosyasını bir klasöre içeriğini ayıklayın.  
  
    3.  .Zip dosyasını silin  
  
3.  Yeniden [!INCLUDE[esprbuild](../misc/includes/esprbuild_md.md)].
