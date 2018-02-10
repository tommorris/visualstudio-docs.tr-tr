---
title: "Özel başlangıç sayfasını yükleyin veya Visual Studio başlangıç öğesi değiştirme | Microsoft Docs"
ms.custom: 
ms.date: 02/01/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.ToolsOptionsPages.Startup
helpviewer_keywords:
- Start Page [Visual Studio]
- customizing Start Page [Visual Studio]
- Visual Studio Start Page
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: ecc22bd23b5b245173321ed3a12379c6fe5622af
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="customize-the-start-page-for-visual-studio"></a>Visual Studio için başlangıç sayfasını özelleştirme

Visual Studio için başlangıç deneyimi gösteren gibi birçok farklı şekilde özelleştirebilirsiniz **Proje Aç** iletişim kutusu veya en son yüklenen çözüm açılıyor. Araç penceresinde çalışan ve Visual Studio'ya özel dahili komutları çalıştıran bir Windows Presentation Foundation (WPF) XAML sayfası olarak, özel bir başlangıç sayfası da gösterebilirsiniz.

## <a name="to-change-the-startup-item"></a>Başlangıç öğesini değiştirmek için

1. Menü çubuğunda seçin **Araçları**, **seçenekleri**.

1. Genişletme **ortam**ve ardından **başlangıç**.

1. İçinde **başlangıçta** listesinde, Visual Studio'yu başlattıktan sonra görüntülenmesi için öğeyi seçin.

## <a name="to-show-a-custom-start-page"></a>Özel bir başlangıç sayfası göstermek için

Yapabilecekleriniz [kendi özel başlangıç sayfası oluşturma](../extensibility/creating-a-custom-start-page.md) Visual Studio SDK'sını kullanarak veya bir başkası zaten oluşturduğu kullanın. Örneğin, özel başlangıç sayfalarını konumunda bulabilirsiniz [Visual Studio Market'te](https://marketplace.visualstudio.com/search?target=VS&category=Tools&vsVersion=&subCategory=Start%20Pages&sortBy=Downloads).

Özel bir başlangıç sayfası yüklemek için .vsix dosyasını açın veya kopyalayıp başlangıç sayfası dosyalarıyla **%USERPROFILE%\Documents\Visual Studio 2017\StartPages** bilgisayarınızda klasör.

### <a name="to-select-which-custom-start-page-to-display"></a>Hangi özel başlangıç sayfasını görüntülemek için seçin

1. Menü çubuğunda seçin **Araçları**, **seçenekleri**.

1. Genişletme **ortam**ve ardından **başlangıç**.

1. İçinde **başlangıç sayfasını özelleştirme** listesinde, istediğiniz sayfasını seçin.

> [!NOTE]
> Özel başlangıç sayfasındaki bir hata Visual Studio'nun çökmesine neden olursa, Visual Studio'yu güvenli modda başlatabilir ve varsayılan başlangıç sayfasını kullanacak şekilde ayarlayabilirsiniz. Bkz: [/safemode (devenv.exe)](../ide/reference/safemode-devenv-exe.md).

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio IDE'yi kişiselleştirme](../ide/personalizing-the-visual-studio-ide.md)
