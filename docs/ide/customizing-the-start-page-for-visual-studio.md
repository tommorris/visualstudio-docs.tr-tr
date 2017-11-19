---
title: "Visual Studio için başlangıç sayfasını özelleştirme | Microsoft Docs"
ms.custom: 
ms.date: 02/01/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.startpage
- VS.StartPage.HowDoI
- vs.ToolsOptionsPages.Startup
helpviewer_keywords:
- Start Page [Visual Studio]
- customizing Start Page [Visual Studio]
- Visual Studio Start page
ms.assetid: 925d42eb-ec34-426e-ad81-19db8630e536
caps.latest.revision: "45"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 178c20c9c4c3af8f5252e70ca603cdf8f8335e52
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="customize-the-start-page-for-visual-studio"></a>Visual Studio için başlangıç sayfasını özelleştirme
Gösterildiği gibi birkaç varsayılan yolla Visual Studio için başlangıç sayfasını özelleştirebilirsiniz **Proje Aç** iletişim kutusu veya en son yüklenen çözüm açılıyor. Araç penceresinde çalışan ve Visual Studio'ya özel dahili komutları çalıştıran bir Windows Presentation Foundation (WPF) XAML sayfası olarak, özel bir başlangıç sayfası da gösterebilirsiniz.  

## <a name="customize-the-default-start-page"></a>Varsayılan başlangıç sayfasını özelleştirme  

1.  Menü çubuğunda seçin **Araçları**, **seçenekleri**.  

2.  Genişletme **ortam**ve ardından **başlangıç**.  

3.  İçinde **başlangıçta** listesinde, kullanmak istediğiniz özelleştirme için öğeyi seçin.  

## <a name="show-a-custom-start-page"></a>Özel başlangıç sayfası gösterme  

1.  Özel bir başlangıç sayfası yüklemek için aşağıdaki yöntemlerden birini kullanın:  

    -   Şuradan yükleyin [Visual Studio Galerisi](http://visualstudiogallery.msdn.microsoft.com/site/search?f%5B0%5D.Type=SearchText&f%5B0%5D.Value=start%20page), başka bir Web sitesi veya yerel intranetinizde sayfası.  

        Özel başlangıç sayfasını içeren bir .vsix dosyasını açın veya kopyalayıp başlangıç sayfası dosyalarıyla **% USERPROFILE % \My Documents\Visual Studio 2017\StartPages** bilgisayarınızda klasör.  

    -   Visual Studio SDK yüklediyseniz kendi başlangıç sayfanızı oluşturun.  

         Bkz: [özel oluşturma başlangıç sayfasının](../extensibility/creating-a-custom-start-page.md).  

2.  Menü çubuğunda seçin **Araçları**, **seçenekleri**.  

3.  Genişletme **ortam**ve ardından **başlangıç**.  

4.  İçinde **başlangıç sayfasını özelleştirme** listesinde, istediğiniz sayfasını seçin.  

> [!NOTE]
>  Özel başlangıç sayfasındaki bir hata Visual Studio'nun çökmesine neden olursa, Visual Studio'yu güvenli modda başlatabilir ve varsayılan başlangıç sayfasını kullanacak şekilde ayarlayabilirsiniz. Bkz: [/safemode (devenv.exe)](../ide/reference/safemode-devenv-exe.md).  

## <a name="see-also"></a>Ayrıca bkz.  
 [Visual Studio IDE'yi kişiselleştirme](../ide/personalizing-the-visual-studio-ide.md)   
