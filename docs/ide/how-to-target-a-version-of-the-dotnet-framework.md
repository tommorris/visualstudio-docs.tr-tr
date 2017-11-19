---
title: "Nasıl yapılır: .NET Framework sürümü hedef | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- targeting .NET Framework version [Visual Studio]
- versions [Visual Studio], targeting .NET Framework version
ms.assetid: dea62d25-3d1b-492e-a6cc-b5154489800a
caps.latest.revision: "50"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 67145a9aaaf4c01b02bc1cc6db89e375639b4fcd
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-target-a-version-of-the-net-framework"></a>Nasıl Yapılır: .NET Framework Sürümü Hedefleme
Bu belge, proje oluştururken bir .NET Framework sürümünü hedefleyen bir projenin nasıl oluşturulacağını ve varolan bir Visual Basic, Visual C# veya Visual F# projesinde hedeflenen sürümün nasıl değiştirileceğini belirtir.  
  
> [!IMPORTANT]
>  C++ projeleri için hedef sürüm değiştirme hakkında daha fazla bilgi için bkz: [nasıl yapılır: hedef Framework ve Platform araç kümesini değiştirme](/cpp/build/how-to-modify-the-target-framework-and-platform-toolset).  
  
 **Bu konudaki**  
  
-   [Bir proje oluşturduğunuzda bir sürümünü hedefleme](../ide/how-to-target-a-version-of-the-dotnet-framework.md#bkmk_new)  
  
-   [Hedef sürümünü değiştirme](../ide/how-to-target-a-version-of-the-dotnet-framework.md#bkmk_existing)  
  
##  <a name="bkmk_new"></a>Bir proje oluşturduğunuzda bir sürümünü hedefleme  
 Bir proje oluştururken, hedeflediğiniz .NET Framework sürümü hangi şablonları kullanabileceğinizi belirler.  
  
> [!NOTE]
>  Visual Studio Express sürümlerinde proje önce oluşturmanız gerekir ve sonra hedef olarak değiştirebilirsiniz [hedef sürümünü değiştirme](../ide/how-to-target-a-version-of-the-dotnet-framework.md#bkmk_existing) bu konunun ilerleyen bölümlerinde anlatılmaktadır.  
  
#### <a name="to-target-a-version-when-you-create-a-project"></a>Projenizi oluştururken bir sürümü hedeflemek için  
  
1.  Menü çubuğunda seçin **dosya**, **yeni**, **proje**.  
  
2.  Listedeki en üstündeki **yeni proje** iletişim kutusunda, .NET Framework sürümünü, hedef projenize istediğinizi seçin.  
  
    > [!NOTE]
    >  Normalde, yalnızca bir .NET Framework sürümü Visual Studio ile birlikte yüklenir. Başka bir sürümü hedeflemek istiyorsanız, önce bu sürümün yüklü olduğundan emin olmalısınız. Bkz: [Visual Studio çoklu sürüm desteğine genel bakış](../ide/visual-studio-multi-targeting-overview.md).  
  
3.  Yüklü Şablonlar listesinde, oluşturmak, projeyi adlandırın ve ardından istediğiniz proje seçin **Tamam** düğmesi.  
  
     Şablon listesi yalnızca seçtiğiniz .NET Framework sürümünün desteklediği projeleri gösterir.  
  
##  <a name="bkmk_existing"></a>Hedef sürümünü değiştirme  
 Aşağıdaki yordamı kullanarak, hedeflenen bir Visual Basic, Visual C# veya Visual F # projesinde .NET Framework sürümü değiştirebilirsiniz.  
  
#### <a name="to-change-the-targeted-version"></a>Hedeflenen sürümü değiştirmek için  
  
1.  İçinde **Çözüm Gezgini**, değiştirin ve ardından istediğiniz proje için kısayol menüsünü açın **özellikleri**.  
  
     ![Visual Studio Çözüm Gezgini özellikleri](../ide/media/vs_slnexplorer_properties.png "vs_slnExplorer_Properties")  
  
    > [!IMPORTANT]
    >  C++ projeleri için hedef sürüm değiştirme hakkında daha fazla bilgi için bkz: [nasıl yapılır: hedef Framework ve Platform araç kümesini değiştirme](/cpp/build/how-to-modify-the-target-framework-and-platform-toolset).  
  
2.  Özellikler penceresini sol sütunda seçin **uygulama** sekmesi.  
  
     ![Visual Studio uygulama özellikleri uygulama sekmesi](../ide/media/vs_slnexplorer_properties_applicationtab.png "vs_slnExplorer_Properties_ApplicationTab")  
  
    > [!NOTE]
    >  Bir UWP uygulaması oluşturduktan sonra hedeflenen bir Windows ya da .NET Framework sürümü değiştirilemiyor.  
  
3.  İçinde **hedef Framework** listesinde, kullanmak istediğiniz sürümü seçin.  
  
4.  Görüntülenen doğrulama iletişim kutusunda seçin **Evet** düğmesi.  
  
     Projenin yüklemesi kaldırılır. Yeniden yüklediğinde, seçtiğiniz .NET Framework sürümünü hedefler.  
  
    > [!NOTE]
    >  Kodunuz hedeflediğinizden farklı bir .NET Framework sürümüne başvurular içeriyorsa, kodu derlediğinizde veya çalıştırdığınızda hata iletileri görülebilir. Bu hataları gidermek için başvuruları değiştirmeniz gerekir. Bkz: [.NET Framework hedefleme hatalarının sorunlarını giderme](../msbuild/troubleshooting-dotnet-framework-targeting-errors.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio çoklu sürüm desteğine genel bakış](../ide/visual-studio-multi-targeting-overview.md)   
 [.NET framework çoklu sürüm desteği için ASP.NET Web projeleri](http://msdn.microsoft.com/Library/8b8145a9-62f6-4fc4-8a83-47b0487cbe76)   
 [.NET Framework hedefleme hatalarının sorunlarını giderme](../msbuild/troubleshooting-dotnet-framework-targeting-errors.md)   
 [Uygulama sayfası, Proje Tasarımcısı (C#)](../ide/reference/application-page-project-designer-csharp.md)   
 [Uygulama sayfası, Proje Tasarımcısı (Visual Basic)](../ide/reference/application-page-project-designer-visual-basic.md)   
 [Projeleri yapılandırma](http://msdn.microsoft.com/Library/a1489abb-6294-4f8f-b71f-2cb126393526)   
 [Nasıl yapılır: hedef Framework ve Platform araç kümesini değiştirme](/cpp/build/how-to-modify-the-target-framework-and-platform-toolset)