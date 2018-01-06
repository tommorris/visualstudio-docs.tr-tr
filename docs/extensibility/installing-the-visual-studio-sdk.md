---
title: "Visual Studio SDK yükleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: visual-studio-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c730edb6-5099-4c16-85a8-08def09f1455
caps.latest.revision: "3"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 13ce2a839c09aa65c2bed2d87aec63827ec6583c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="installing-the-visual-studio-sdk"></a>Visual Studio SDK yükleme
Visual Studio SDK, Visual Studio kurulumunda isteğe bağlı bir özelliktir. VS SDK'yı daha sonra da yükleyebilirsiniz.  
  
## <a name="installing-the-visual-studio-sdk-as-part-of-a-visual-studio-installation"></a>Visual Studio yüklemesinin bir parçası Visual Studio SDK yükleme  
 Visual Studio yüklemenizin VSSDK dahil etmek istediğiniz, yüklemeniz **Visual Studio uzantısı geliştirme** iş yükü altında **diğer Toolsets**. Bu, gerekli Önkoşullar yanı sıra, Visual Studio SDK'sını yükler. Daha fazla seçerek yükleme ayarlayabilirsiniz veya Özet unselecting bileşenlerini görüntüleyin. 
  
## <a name="installing-the-visual-studio-sdk-after-installing-visual-studio"></a>Visual Studio yüklendikten sonra Visual Studio SDK yükleme  
 Visual Studio yüklemenizin tamamladıktan sonra Visual Studio SDK'yı yüklemeye karar verirseniz, Visual Studio yükleyicisi yeniden çalıştırmak ve seçmek **Visual Studio uzantısı geliştirme** iş yükü.  
  
## <a name="installing-the-visual-studio-sdk-from-a-solution"></a>Bir çözümü Visual Studio SDK yükleme  
 VSSDK yüklemeden genişletilebilirlik projesi ile bir çözüm açarsanız, Çözüm Gezgini yukarıda vurgulanan bilgi çubuğu tarafından istenir. Aşağıdaki gibi görünmelidir:  
  
 ![SolutionExplorerInstall](../extensibility/media/solutionexplorerinstall.png "SolutionExplorerInstall")  
  
## <a name="installing-the-visual-studio-sdk-from-the-command-line"></a>Visual Studio SDK komut satırından yükleme  
Visual Studio iş yükü ya da bileşen gibi öğenin komut satırından da yükleyebilirsiniz. Bkz: [Visual Studio'yu yüklemek için komut satırı parametrelerini kullanmak](../install/use-command-line-parameters-to-install-visual-studio.md) uygun komut satırı anahtarları ve iş yükü ya da bileşen tanımlayıcıları belirleme hakkında ayrıntılar için.
  
 Yüklü Visual Studio sürümünüzle eşleşen Visual Studio yükleyicisi kullanmanız gerektiğini unutmayın. Örneğin, bilgisayarınızda yüklü Visual Studio Enterprise varsa, Visual Studio Enterprise Yükleyici (vs_enterprise.exe) çalıştırmanız gerekir.