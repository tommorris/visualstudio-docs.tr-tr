---
title: "VSIX proje şablonu ile çalışmaya başlama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Visual Studio SDK, VSIX project template
ms.assetid: 89fac33e-9380-4723-9b45-048a6e16f0ed
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: c87fd485a0d682dc21de21dfe32b83cfc29b520a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="getting-started-with-the-vsix-project-template"></a>VSIX proje şablonu ile çalışmaya başlama
Uzantı oluşturmak veya var olan uzantı dağıtımı için paketi için VSIX proje şablonu kullanabilirsiniz. VSIX proje şablonu sürümler hem Visual Basic ve Visual C# ve Visual Studio SDK'sı bir parçası olarak yüklenir.  
  
 VSIX proje şablonu yalnızca uzantısı hakkında bilgi içeren bir source.extension.vsixmanifest dosyası ve onu gelir varlıklar oluşur.  
  
 VSIX proje şablonu bulmak için Visual Studio SDK'yı yüklemeniz gerekir. Daha fazla bilgi için bkz: [Visual Studio SDK](../extensibility/visual-studio-sdk.md).  
  
## <a name="deploying-a-custom-project-template-using-the-vsix-project-template"></a>VSIX proje şablonunu kullanarak özel bir proje şablonu dağıtma  
 Aşağıdaki adımlar VSIX proje paketi diğer geliştiricilerle paylaşabilirsiniz ya da Visual Studio Galerisi'ne karşıya bir proje şablonu için nasıl kullanılacağını gösterir.  
  
1.  Bir proje şablonu oluşturun.  
  
    1.  Bir şablonu oluşturulacağı projeyi açın. Bu proje herhangi bir proje türde olabilir.  
  
    2.  Üzerinde **proje** menüsünde tıklatın **şablonu dışarı aktar**. Sihirbazın adımlarını tamamlayın.  
  
         Bir .zip dosyası %USERPROFILE%\My Documents\Visual Studio oluşturulur  *\<sürüm >*\My dışa aktarılan şablonları\\.  
  
2.  Boş bir VSIX projesi oluşturun.  
  
     Üzerinde **dosya** menüsünde tıklatın **yeni** ve ardından **proje**. Şunlardan birini seçin **Visual Basic** veya **Visual C#**. Seçili düğümünde seçin **genişletilebilirlik**ve ardından **VSIX proje**.  
  
3.  .Zip dosyası projeye ekleyin. Ayarlama, **çıktı dizinine Kopyala** özelliğine `Copy Always`.  
  
4.  İçinde **Çözüm Gezgini**, çift `source.extension.vsixmanifest` içinde açmak için dosya **VSIX bildirim Tasarımcısı**ve ardından aşağıdaki değişiklikleri yapın:  
  
    -   Ayarlama **ürün adı** alanı **My proje şablonu**.  
  
    -   Ayarlama **ürün kimliği** alanı **MyProjectTemplate - 1**.  
  
    -   Ayarlama **Yazar** alanı **Fabrikam**.  
  
    -   Ayarlama **açıklama** alanı **proje Şablonum**.  
  
    -   İçinde **varlıklar** bölümünde bir **Microsoft.VisualStudio.ProjectTemplate** yazın ve yolunu .zip dosyası adına ayarlayın.  
  
5.  Source.extension.vsixmanifest dosyasını kaydedip kapatın.  
  
6.  Projeyi oluşturun.  
  
7.  Çıktı dizininde .vsix dosyasına çift tıklayın.  
  
8.  A **VSIX yükleyici** ileti kutusu görünür. Uzantıyı yüklemek için yönergeleri izleyin.  
  
9. Visual Studio'yu kapatın ve yeniden açın.  
  
10. Seçin **Uzantılar ve güncelleştirmeler** (üzerinde **Araçları** menüsü) seçip **şablonları** kategorisi. Kullanılabilir uzantılar birini olmalıdır **My proje şablonu**.  
  
11. Yeni Proje şablonu görünür **yeni proje** özgün proje şablonu ile aynı yerde iletişim. Adlı bir şablon oluşturduysanız, örneğin, **VB konsol** bir Visual Basic konsol uygulamasından **VB konsol** Visual Basic ile aynı bölmesinde görünür **konsol uygulaması**şablonu.  
  
#### <a name="to-specify-the-location-of-the-template-in-the-new-project-dialog-box"></a>Yeni Proje iletişim kutusunda şablon konumunu belirtmek için  
  
1.  Şablon klasörleri içinde bulunur *Visual Studio yükleme yolu*\Common7\IDE\ProjectTemplates ve *Visual Studio yükleme yolu*\Common7\IDE\ItemTemplates dizinleri. Yeni Proje iletişim kutusu üst düzey bölümlerde adları şablon klasörlerin adlarını tam olarak aynı. Bunların farklı yerlerde şablon klasörünün adını kullanın.  
  
     .Vsix dosya uzantısını .zip olarak değiştirin ve dosyayı açın.  
  
2.  Yeni Proje iletişim kutusu bölümünü şablon görüntülenmelidir aynı ada sahip yeni bir klasör oluşturun.  
  
3.  Şablon alt bölümde görünür varsa aynı ada sahip bir alt klasör oluşturun.  
  
4.  Şablon .zip dosyasını yeni bir klasöre taşıyın.  
  
5.  .Zip uzantısı .vsix değiştirin.  
  
6.  VSIX bildirimini açın.  
  
7.  VSIX bildiriminde güncelleştirme **varlık** olan şablon dosyası içeren dizin ağacında kök dizinine işaret şekilde şablonun yolunu. Örneğin, şablonu içinde \CSharp\Windows ise, başvuru için \CSharp işaret etmelidir.