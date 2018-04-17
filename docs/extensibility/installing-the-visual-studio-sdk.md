---
title: Visual Studio SDK yükleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-sdk
ms.topic: conceptual
ms.assetid: c730edb6-5099-4c16-85a8-08def09f1455
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 259646e0dbee4831db83a7098954d1c5144d8ead
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
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
Tüm Visual Studio iş yükü veya bileşeni ile de yükleyebilirsiniz gibi **Visual Studio uzantısı geliştirme** iş yükü (kimlik: Microsoft.VisualStudio.Workload.VisualStudioExtension) komut satırından. Bkz: [Visual Studio'yu yüklemek için komut satırı parametrelerini kullanmak](../install/use-command-line-parameters-to-install-visual-studio.md) genel yönergeler iş yükü ya da bileşen tanımlayıcıları belirleme ve uygun komut satırı anahtarları hakkında ayrıntılı bilgi için.
  
 Yüklü Visual Studio sürümünüzle eşleşen Visual Studio yükleyicisi kullanmanız gerektiğini unutmayın. Örneğin, bilgisayarınızda yüklü Visual Studio Enterprise varsa, Visual Studio Enterprise Yükleyici (vs_enterprise.exe) çalıştırmanız gerekir.