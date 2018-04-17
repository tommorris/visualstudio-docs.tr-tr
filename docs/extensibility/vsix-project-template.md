---
title: VSIX proje şablonu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- deploy packages
- publish extension
ms.assetid: b6c82167-e2a5-4cff-8c8b-2d72e2a9092c
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: bff05b0b1b05a6b00b7924f0fb5bfc957adba41c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="vsix-project-template"></a>VSIX proje şablonu
Bir veya daha fazla Visual Studio uzantıları VSIX projesinde sarmalamak için VSIX proje şablonu kullanın ve üzerinde paket yayımlama [Visual Studio Galerisi](http://go.microsoft.com/fwlink/?LinkID=123847) Web sitesi.  
  
 VSIX dağıtım VSPackages, derlemeleri, MEF Bileşenleri, proje şablonları, öğe şablonları, araç çubuğu denetimleri ve özel uzantı türlerini destekler.  
  
> [!NOTE]
>  VSIX projeleri kullanmak için Visual Studio SDK'yı yüklemeniz gerekir. Visual Studio SDK'sı hakkında daha fazla bilgi için bkz: [Visual Studio SDK](../extensibility/visual-studio-sdk.md).  
  
## <a name="where-to-find-the-vsix-project-template"></a>VSIX proje şablonu nerede bulacağını  
 VSIX proje şablonu kullanılabilir **yeni proje** iletişim kutusu. Genişletin **Visual Basic** düğümü veya **Visual C#** düğümünü ve ardından **genişletilebilirlik**.  
  
> [!TIP]
>  Bu .NET Framework 4.5 emin olmanız gerekir ya da daha yüksek en üstündeki açılır belirtilen **yeni proje** iletişim kutusu.  
  
## <a name="uses-of-the-vsix-project-template"></a>VSIX proje şablonu kullanımları  
 VSIX proje şablonu iki temel kullanım şekli vardır:  
  
-   Proje şablonları, öğe şablonları ve VSIX desteği bulunmayan diğer uzantılar dağıtmak için.  
  
-   Bir dağıtım paketi birden çok uzantı çıkışları sarmalamak için.  
  
 VSPackages veya diğer tür destek VSIX zaten uzantıları dağıtmak için VSIX proje şablonu kullanmak zorunda değil.  
  
## <a name="packaging-an-extension-in-an-empty-vsix-project"></a>Uzantı boş VSIX projesinde paketleme  
 Varolan bir uzantı veya VSIX desteği, boş VSIX projesinde kaydırma tarafından zaten sahip olmayan bir uzantı paketleyebilirsiniz. Sarmalamak için uzantı tarafından desteklenen bir türde olmalıdır [VSIX şema](../extensibility/vsix-extension-schema-2-0-reference.md).  
  
#### <a name="to-package-an-extension-by-using-a-vsix-project"></a>Paket VSIX proje kullanarak bir uzantısı  
  
1.  Uzantınızı yapmak projeleri oluşturun.  
  
2.  Kullanarak bir VSIX proje oluşturma **VSIX proje** şablonu.  
  
     Source.extension.vsixmanifest açılır **bildirim Tasarımcısı**.  
  
3.  Üzerinde **varlıklar** sekmesinde, seçin **yeni** düğmesi.  
  
     **Ekleme yeni varlık** iletişim kutusu görüntülenir.  
  
4.  İçinde **türü** listesinde, eklemek için uzantı türü seçin.  
  
5.  Geçerli çözümde (örneğin, bir öğe şablonu veya derlenmiş bir bütünleştirilmiş kod) bulunan bir uzantı veya içerik öğesi eklemek için aşağıdaki adımları gerçekleştirin:  
  
    1.  İçinde **kaynak** listesinde, seçin **geçerli çözümdeki bir proje ile**.  
  
    2.  İçinde **proje** listesinde, uzantısının adını seçin.  
  
    3.  İçinde **bu klasördeki Embed** kutusuna, varlık katıştırmak ve daha sonra seçmek bir klasör adı girin **Tamam** düğmesi.  
  
6.  Bir uzantı veya geçerli çözümde bulunup içerik öğesi eklemek için aşağıdaki adımları gerçekleştirin:  
  
    1.  İçinde **kaynak** liste kutusunda, seçin **filesystem dosyada**.  
  
    2.  İçinde **yolu** derlenmiş veya sıkıştırılmış uzantısı dosyanın tam yolunu girin veya kullanmak alanı **Gözat** dosyaya gözatmak için düğmeyi.  
  
    3.  İçinde **bu klasördeki Embed** kutusuna, varlık katıştırmak ve daha sonra seçmek bir klasör adı girin **Tamam** düğmesi.  
  
7.  Paketinizi ek uzantıları dahil etmek istiyorsanız, bunları aynı şekilde ekleyin.  
  
8.  Çözümü oluşturun.  
  
     [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] VSIX bildirim dosyası, [Content_Types] .xml dosyasını ve tüm projeye eklendi ve uzantı varlıkları içeren bir .vsix dosyası oluşturur.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [VSIX uzantısı 2.0 şema başvurusu](../extensibility/vsix-extension-schema-2-0-reference.md)   
 [Visual Studio Uzantıları’nı bulma ve kullanma](../ide/finding-and-using-visual-studio-extensions.md)