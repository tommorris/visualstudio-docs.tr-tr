---
title: "Yalıtılmış Kabuk genişletme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Visual Studio shell, isolated mode
ms.assetid: 9a641d8f-211e-4486-a1b1-4a89fafe7ee8
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 04257a6ea4bfb3dbe788ba48ee3077b1847b000d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="extending-the-isolated-shell"></a>Yalıtılmış Kabuk genişletme
Yalıtılmış kabuk uygulamanıza bir VSPackage, Yönetilen Genişletilebilirlik Çerçevesi (MEF) bileşeni bölümü ya da bir genel VSIX proje ekleyerek yalıtılmış Visual Studio Kabuğu'nu genişletebilirsiniz.  
  
> [!NOTE]
>  Aşağıdaki adımlar temel yalıtılmış Kabuk uygulama Visual Studio Shell yalıtılmış proje şablonunu kullanarak oluşturduğunuz presuppose. Bu proje şablonu hakkında daha fazla bilgi için bkz: [izlenecek yol: temel bir yalıtılmış Kabuk uygulama oluşturma](walkthrough-creating-a-basic-isolated-shell-application.md).  
  
## <a name="locations-for-the-visual-studio-package-project-template"></a>Visual Studio Paketi proje şablonu için konumları  
 Visual Studio Paketi proje şablonu üç farklı konumlarda bulunabilir **yeni proje** iletişim:  
  
1.  Altında **Visual Basic**, **genişletilebilirlik**. Visual Basic projesinin varsayılan dildir.  
  
2.  Altında **Visual C#**, **genişletilebilirlik**. Varsayılan proje C# dilidir.  
  
3.  Altında **diğer proje türleri**, **genişletilebilirlik**. C++ projesinin varsayılan dildir.  
  
## <a name="adding-a-vspackage"></a>Bir VSPackage ekleme  
 Yalıtılmış kabuk uygulamanıza bir VSPackage ekleyebilirsiniz. Aşağıdaki adımlar menü komutlarını ekler oluşturmak nasıl gösterir.  
  
#### <a name="to-add-a-new-vspackage"></a>Yeni bir VSPackage eklemek için  
  
1.  Adlı bir Visual Studio Paketi projesi eklemek `MenuCommandsPackage`.  
  
2.  Üzerinde **Temel VSPackage Bilgileri** sihirbazın ayarlamak **şirket adı** için `Fabrikam` ve **VSPackage adı** için `FabrikamMenuCommands`. Seçin **sonraki** düğmesi.  
  
3.  Sonraki sayfada seçin **menü komutu** ve ardından **sonraki**.  
  
4.  Sonraki sayfada ayarlamak **komut adı** için `Fabrikam Command` ve **komut kimliği** için `cmdidFabrikamCommand`ve ardından **sonraki**.  
  
5.  Üzerinde **proje seçenekleri Test** sayfasında, test seçeneklerini temizleyin ve ardından **son** düğmesi.  
  
6.  ShellExtensionsVSIX projesinde source.extension.vsixmanifest dosyasını açın.  
  
     **Varlıklar** bölüm VSShellStub.AboutBoxPackage proje için bir giriş içermelidir.  
  
7.  Seçin **yeni** düğmesi.  
  
8.  İçinde **ekleme yeni varlık** penceresi, **türü** listesinde **Microsoft.VisualStudio.VsPackage**.  
  
9. İçinde **kaynak** listesinde, olduğundan emin olun **geçerli çözümdeki bir proje ile** seçilir. İçinde **proje** liste kutusunda **MenuCommandsPackage**.  
  
10. Dosyayı kaydedin ve kapatın.  
  
11. Çözümü yeniden derleyin ve yalıtılmış Kabuk hata ayıklamayı Başlat.  
  
12. Menü çubuğunda seçin **Araçları** menüsü, ardından **Fabrikam komutu**.  
  
     Bir ileti kutusu görünmesi gerekir.  
  
13. Uygulama hata ayıklamayı durdurun.  
  
## <a name="adding-a-mef-component-part"></a>Bir MEF Bileşeni bölümü ekleme  
 Aşağıdaki adımlar bir MEF Bileşeni bölümü yalıtılmış kabuk uygulamanıza eklemek nasıl gösterir.  
  
#### <a name="to-add-a-mef-component"></a>Bir MEF bileşeni eklemek için  
  
1.  İçinde **Yeni Proje Ekle** iletişim kutusunda **Visual C#**, **genişletilebilirlik**, kullanın **Düzenleyicisi kenar boşluğu** bir proje eklemek için şablonu. Bu ad `ShellEditorMargin`.  
  
2.  ShellExtensionsVSIX projesinde tasarım görünümünde, kod görünümü Source.extension.vsixmanifest dosyasını açın.  
  
3.  İçinde `Asset` bölümünde, seçin **İçerik Ekle**.  
  
4.  İçinde **ekleme yeni varlık** penceresi, **türü** listesinde **Microsoft.VisualStudio.MefComponent**.  
  
5.  İçinde **kaynak** listesinde, olduğundan emin olun **geçerli çözümdeki bir proje ile** seçilir. İçinde **proje** liste kutusunda **ShellEditorMargin**.  
  
6.  Dosyayı kaydedin ve kapatın.  
  
7.  Çözümü yeniden derleyin ve yalıtılmış Kabuk hata ayıklamayı Başlat.  
  
8.  Bir metin dosyasını açın.  
  
     "Hello world!" sözcükler içeriyor yeşil bir kenar boşlukları metin dosyası penceresinin alt kısmında görüntülenmesi gerekir.  
  
9. Uygulama hata ayıklamayı durdurun.  
  
## <a name="adding-a-generic-vsix-project"></a>Bir genel VSIX proje ekleme  
  
#### <a name="to-add-a-generic-vsix-project"></a>Genel VSIX proje eklemek için  
  
1.  İçinde **Yeni Proje Ekle** iletişim kutusunda **Visual C#**, **genişletilebilirlik**, kullanın **VSIXProject** bir proje eklemek için şablonu. Bu ad `EmptyVSIX`.  
  
2.  ShellExtensionsVSIX projesinde tasarım görünümünde, kod görünümü Source.extensions.vsixmanifest dosyasını açın.  
  
3.  İçinde `Assets` bölümünde, seçin **yeni**.  
  
4.  İçinde **ekleme yeni varlık** penceresi, **türü** listesinde, eklemek istediğiniz içerik türü seçin.  
  
5.  İçinde **kaynak**, olduğundan emin olun **geçerli çözümdeki bir proje ile** seçeneği işaretlidir. Liste kutusunda VSIX projenizin adını seçin.  
  
6.  Dosyayı kaydedin ve kapatın.  
  
7.  Bu proje derlenmiş kodu içeriyorsa, böylece derlemenin çıktısında proje düzenlemeniz gerekir.  
  
    1.  VSIX proje kaldırma ve proje dosyasını açın.  
  
    2.  İlk `<PropertyGroup>` engellemek, değerini değiştirme `<CopyBuildOutputToOutputDirectory>` için `true`.  
  
    3.  Kaydet ve projeyi yeniden yükleyin.  
  
8.  Derleme ve çözümü çalıştırın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İzlenecek yol: Temel Yalıtılmış Kabuk Uygulaması Oluşturma](walkthrough-creating-a-basic-isolated-shell-application.md)