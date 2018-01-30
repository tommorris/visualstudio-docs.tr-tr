---
title: "Nasıl yapılır: .NET Framework sürümü hedef | Microsoft Docs"
ms.custom: 
ms.date: 12/08/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- targeting .NET Framework version [Visual Studio]
- versions [Visual Studio], targeting .NET Framework version
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- dotnet
ms.openlocfilehash: da2e236c39cce72670a47212aedabb87afa4d217
ms.sourcegitcommit: b18844078a30d59014b48a9c247848dea188b0ee
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/29/2018
---
# <a name="how-to-target-a-version-of-the-net-framework"></a>Nasıl Yapılır: .NET Framework Sürümü Hedefleme

Bu belge, bir proje oluşturduğunuzda, .NET Framework sürümünü hedefleyecek şekilde açıklar ve nasıl bir mevcut Visual Basic, C# veya Visual F # projesinde hedeflenen sürüm değiştirin.

> [!IMPORTANT]
> C++ projeleri için hedef sürüm değiştirme hakkında daha fazla bilgi için bkz: [nasıl yapılır: hedef Framework ve Platform araç kümesini değiştirme](/cpp/build/how-to-modify-the-target-framework-and-platform-toolset).

## <a name="targeting-a-version-when-you-create-a-project"></a>Projenizi oluştururken bir sürümü hedefleme

Bir proje oluştururken, hedeflediğiniz .NET Framework sürümü hangi şablonları kullanabileceğinizi belirler.

### <a name="to-target-a-version-when-you-create-a-project"></a>Projenizi oluştururken bir sürümü hedeflemek için

1.  Menü çubuğunda seçin **dosya**, **yeni**, **proje**.

2.  Listedeki en üstündeki **yeni proje** iletişim kutusunda, .NET Framework sürümünü, hedef projenize istediğinizi seçin.

3.  Yüklü Şablonlar listesinde, oluşturmak, projeyi adlandırın ve ardından istediğiniz proje seçin **Tamam** düğmesi.

    Şablon listesi yalnızca seçtiğiniz .NET Framework sürümünün desteklediği projeleri gösterir.

## <a name="changing-the-target-version"></a>Hedef sürümü değiştirme

Aşağıdaki yordamı kullanarak, hedeflenen bir Visual Basic, C# veya Visual F # projesinde .NET Framework sürümü değiştirebilirsiniz.

C++ projeleri için hedef sürüm değiştirme hakkında daha fazla bilgi için bkz: [nasıl yapılır: hedef Framework ve Platform araç kümesini değiştirme](/cpp/build/how-to-modify-the-target-framework-and-platform-toolset).

### <a name="to-change-the-targeted-version"></a>Hedeflenen sürümü değiştirmek için

1.  İçinde **Çözüm Gezgini**, değiştirin ve ardından istediğiniz proje için kısayol menüsünü açın **özellikleri**.

    ![Visual Studio Çözüm Gezgini özellikleri](../ide/media/vs_slnexplorer_properties.png "vs_slnExplorer_Properties")

2. Özellikler penceresini sol sütunda seçin **uygulama** sekmesi.

    ![Visual Studio uygulama özellikleri uygulama sekmesi](../ide/media/vs_slnexplorer_properties_applicationtab.png "vs_slnExplorer_Properties_ApplicationTab")

    > [!NOTE]
    > Bir UWP uygulaması oluşturduktan sonra hedeflenen bir Windows ya da .NET Framework sürümü değiştirilemiyor.

3.  İçinde **hedef Framework** listesinde, kullanmak istediğiniz sürümü seçin.

4.  Görüntülenen doğrulama iletişim kutusunda seçin **Evet** düğmesi.

    Projenin yüklemesi kaldırılır. Yeniden yüklediğinde, seçtiğiniz .NET Framework sürümünü hedefler.

    > [!NOTE]
    > Kodunuz hedeflediğinizden farklı bir .NET Framework sürümüne başvurular içeriyorsa, kodu derlediğinizde veya çalıştırdığınızda hata iletileri görülebilir. Bu hataları gidermek için başvuruları değiştirmeniz gerekir. Bkz: [.NET Framework hedefleme hatalarının sorunlarını giderme](../msbuild/troubleshooting-dotnet-framework-targeting-errors.md).

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio Çoklu Sürüm Desteğine Genel Bakış](../ide/visual-studio-multi-targeting-overview.md)  
[.NET Framework Hedefleme Hatalarının Sorunlarını Giderme](../msbuild/troubleshooting-dotnet-framework-targeting-errors.md)  
[Uygulama Sayfası, Proje Tasarımcısı (C#)](../ide/reference/application-page-project-designer-csharp.md)  
[Uygulama Sayfası, Proje Tasarımcısı (Visual Basic)](../ide/reference/application-page-project-designer-visual-basic.md)  
[Nasıl yapılır: hedef Framework ve Platform araç takımı (C++) değiştirme](/cpp/build/how-to-modify-the-target-framework-and-platform-toolset)