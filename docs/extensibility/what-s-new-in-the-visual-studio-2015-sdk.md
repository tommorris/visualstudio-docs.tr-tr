---
title: '&#39; teki Visual Studio 2015 SDK''deki yenilikler | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c64aac80-a411-463f-b7bd-8b7607a52ece
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: b8b1fa4647cd5b145d19e2264381b186394be814
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="what39s-new-in-the-visual-studio-2015-sdk"></a>&#39; teki Visual Studio 2015 SDK'deki yenilikler
Visual Studio SDK, Visual Studio 2015, güncelleştirilmiş Visual Studio 2015 ve Visual Studio 2017 için aşağıdaki yeni ve güncelleştirilmiş özelliklere sahiptir.  
  
## <a name="vs-2015-sdk-update-1"></a>VS 2015 SDK güncelleştirme 1  
 Güncelleştirme 1 iyi renk temaları ve Visual Studio görüntü hizmet çalışma uzantınızı yardımcı olacak araçlar içerir.  
  
 Bu konularda altındadır [VSSDK yardımcı programları](../extensibility/internals/vssdk-utilities.md) bölümü:  
  
-   [Renk Tema oluşturma araçları](../extensibility/internals/color-theming-tools.md) yardımcı oluşturmak ve Visual Studio için özel renkler düzenleyin.  
  
-   [Görüntüsü hizmeti Araçları](../extensibility/internals/image-service-tools.md) Visual Studio görüntü bildirim dosyalarıyla çalışma izin verir.  
  
## <a name="new-way-to-add-the-visual-studio-sdk-to-visual-studio"></a>Visual Studio için Visual Studio SDK eklemek için yeni yol  
 Visual Studio 2015'ten başlayarak, ayrı olarak Visual Studio SDK'sını indirin gerekmez. Bunun yerine, normal yükleme işleminin bir parçası olarak yüklemek veya daha sonra yüklemeyi seçebilirsiniz. Açtığınızda ya da bir VSIX çözümü oluşturun Visual Studio için Visual Studio genişletilebilirlik araçları yüklemeniz istenir. Daha fazla bilgi için bkz: [Visual Studio SDK'sını yükleme](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="new-ways-of-creating-extensions"></a>Uzantılar oluşturma yeni yolları  
 Visual Studio 2015 SDK'ın başlayarak, programlama dili bağlı olarak, kullanmakta olduğunuz uzantıları oluşturmak için farklı seçeneğiniz vardır.  
  
### <a name="visual-c-and-visual-basic"></a>Visual C# ve Visual Basic  
 C# ve Visual Basic için eksiksiz bir VSPackages, menü komutlarını, aracı windows, düzenleyici sınıflandırıcı, Düzenleyicisi adornments ve düzenleyici kenar boşluğu uzantıları oluşturmanıza izin proje öğesi şablonları yoktur. Bu standart VSIX proje için bir bölümünü veya tamamını ekleyebilirsiniz. Daha fazla bilgi için bkz.:  
  
-   [Menü komutu ile bir uzantısı oluşturma](../extensibility/creating-an-extension-with-a-menu-command.md)  
  
-   [Bir uzantısı bir araç penceresi oluşturma](../extensibility/creating-an-extension-with-a-tool-window.md)  
  
-   [Bir düzenleyici öğesi şablonuyla bir uzantısı oluşturma](../extensibility/creating-an-extension-with-an-editor-item-template.md)  
  
-   [Uzantı VSPackage ile oluşturma](../extensibility/creating-an-extension-with-a-vspackage.md)  
  
     VSPackage Sihirbazı'nı uzantıları C# veya Visual Basic uygulamasında artık oluşturur.  
  
### <a name="c"></a>C++  
 C++ için VSPackage Sihirbazı'nı menü komutlarını, aracı windows ve özel düzenleyiciler destekler. İçinde arayın **yeni proje** iletişim kutusunda **Visual C++ / genişletilebilirlik**.  
  
## <a name="vs-sdk-reference-assemblies-via-nuget"></a>NuGet aracılığıyla VS SDK başvuru derlemeleri  
 Taşınabilirliği artırmak ve genişletilebilirlik projelerin paylaşımı için VS SDK başvuru derlemeleri NuGet sürümlerini kullanabilirsiniz.  Bunlar üzerinde kullanılabilir [nuget.org](http://www.nuget.org) tarafından yayımlanan [VisualStudioExtensibility](http://www.nuget.org/profiles/VisualStudioExtensibility) ve projeye ya da çözümü Visual Studio aracılığıyla kolayca eklenebilen **başvuruyor / yönetme NuGet Paketleri** iletişim. Belirli genişletilebilirlik derlemelerine tek tek başvurular ekleyin ya da tüm VS SDK başvuran aynı anda VS SDK'sını kullanarak derlemeler ekleme [Meta paket](http://www.nuget.org/packages/VSSDK_Reference_Assemblies). NuGet hakkında daha fazla bilgi için bkz: [NuGet belgelerine](http://docs.microsoft.com/NuGet) ve [Paket Yöneticisi kullanıcı Arabirimi](http://docs.microsoft.com/NuGet/Tools/Package-Manager-UI) Konular.  
  
 VS SDK başvuru derlemeleri NuGet sürümlerini kullandığınızda, başka bir kullanıcı açmak ve projenizi derleme için VS SDK'yı yükleme gerekmez.  NuGet başvuru derlemeleri ve VS SDK derleme araçlarını, bu proje için kendi bilgisayarında otomatik olarak yüklenir.  
  
 VS SDK öğe şablonları NuGet avantajları varsayılan sürdürmenizi oluşturma araçlarını ve NuGet başvurularını için kullanın.  
  
> [!NOTE]
>  VS SDK'sı başvuru derlemeleri projelerinizi kullanmaya devam edebilirsiniz (altında bulunan \<Visual Studio yükleme konumu > \ VSSDK\VisualStudioIntegration\Common\Assemblies) ve mevcut genişletilebilirlik projeleri olması gerekmez NuGet paketlerini kullanmak için yükseltilmiştir.  Proje **başvuruyor / Başvurusu Ekle** VS SDK'sı başvurusu derlemeleri kullanma iletişim devam eder.  
>   
>  NuGet kullanmak için bkz: varolan projelerinizi değiştirmek istiyorsanız [nasıl yapılır: geçirmek VSPackages Visual Studio 2015 için](../extensibility/how-to-migrate-extensibility-projects-to-visual-studio-2015.md) genişletilebilirlik projeleri için NuGet paketlerini güncelleştirme bölümü vardır.  
  
## <a name="light-bulbs"></a>Ampuller  
 Uzantı kodu yazmaya en heyecan verici yeni yollarından biri Roslyn projesi tarafından sağlanır. Daha fazla bilgi için bkz: [Roslyn](https://github.com/dotnet/Roslyn).  
  
 Ampuller VSSDK ile birlikte gelen yeni bir özelliktir. Kodu yeniden düzenleme eylemleri ya da yerleşik kod çözümleyicileri tarafından tanımlanan sorunlara yönelik düzeltmelerin kümesini görüntülemek için'nı genişletin Visual Studio düzenleyicisinde kullanılan simgeler oldukları. Daha fazla bilgi için bkz: [izlenecek yol: görüntüleme ampul önerileri](../extensibility/walkthrough-displaying-light-bulb-suggestions.md).  
  
## <a name="updated-user-experience-guidelines"></a>Güncelleştirilmiş kullanıcı deneyimi yönergeleri  
 Yeni uzantılar ya da özellikler için Visual Studio tasarlama? Güncelleştirilmiş ve genişletilmiş kontrol [Visual Studio kullanıcı deneyimi yönergeleri](../extensibility/ux-guidelines/visual-studio-user-experience-guidelines.md).  Bulabilirsiniz [renk belirteçleri](../extensibility/ux-guidelines/shared-colors-for-visual-studio.md), [yazı tipi boyutlarını](../extensibility/ux-guidelines/fonts-and-formatting-for-visual-studio.md), [iletişim düzeni belirtimleri](../extensibility/ux-guidelines/layout-for-visual-studio.md)ve diğer yönergeler sorunsuz bir şekilde yeni UI Visual Studio ile tümleştirmeniz gerekir.