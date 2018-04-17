---
title: Visual Studio'da .NET Framework sürüm hedef | Microsoft Docs
ms.custom: ''
ms.date: 02/06/2018
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- targeting .NET Framework [Visual Studio]
- .NET Framework version [Visual Studio]
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 73cec2f27bfc2e29b9b9faa34c9c24ca2273210e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-target-a-version-of-the-net-framework"></a>Nasıl yapılır: .NET Framework sürümü hedef

Bu belge, bir proje oluşturduğunuzda, .NET Framework sürümünü hedefleyecek şekilde açıklar ve nasıl bir mevcut Visual Basic, C# veya Visual F # projesinde hedeflenen sürüm değiştirin.

> [!IMPORTANT]
> C++ projeleri için hedef sürüm değiştirme hakkında daha fazla bilgi için bkz: [nasıl yapılır: hedef Framework ve Platform araç kümesini değiştirme](/cpp/build/how-to-modify-the-target-framework-and-platform-toolset).

## <a name="to-target-a-version-when-you-create-a-project"></a>Projenizi oluştururken bir sürümü hedeflemek için

Bir proje oluşturduğunuzda, kullanılabilir .NET Framework sürümlerinin hangi sürümlerinin yüklü olduğundan ve seçilen şablonda bağımlı **yeni proje** iletişim kutusu.

1. Menü çubuğunda seçin **dosya** > **yeni** > **proje...** .

1. Yüklü Şablonlar listesinde, oluşturmak istediğiniz proje türünü seçin ve proje için bir ad girin.

1. Gelen **Framework** altındaki aşağı açılan liste **yeni proje** iletişim kutusunda, .NET Framework sürümünü, hedef projenize istediğinizi seçin.

    Seçtiğiniz şablon için geçerli olan sürümler çerçeveleri listesini gösterir. .NET Core gibi bazı proje türleri, .NET Framework gerektirmez. Böyle durumlarda, **Framework** aşağı açılan liste gizlenir.

    ![Framework açılan yeni proje iletişim kutusuna](media/vside-newproject-framework.png)

1. Seçin **Tamam** düğmesi.

## <a name="to-change-the-targeted-version"></a>Hedeflenen sürümü değiştirmek için

Aşağıdaki yordamı kullanarak, hedeflenen bir Visual Basic, C# veya Visual F # projesinde .NET Framework sürümü değiştirebilirsiniz.

C++ projeleri için hedef sürüm değiştirme hakkında daha fazla bilgi için bkz: [nasıl yapılır: hedef Framework ve Platform araç kümesini değiştirme](/cpp/build/how-to-modify-the-target-framework-and-platform-toolset).

1. İçinde **Çözüm Gezgini**, değiştirin ve ardından istediğiniz proje için kısayol menüsünü açın **özellikleri**.

    ![Visual Studio Çözüm Gezgini özellikleri](../ide/media/vs_slnexplorer_properties.png "vs_slnExplorer_Properties")

1. Özellikler penceresini sol sütunda seçin **uygulama** sekmesi.

    ![Visual Studio uygulama özellikleri uygulama sekmesi](../ide/media/vs_slnexplorer_properties_applicationtab.png "vs_slnExplorer_Properties_ApplicationTab")

    > [!NOTE]
    > Bir UWP uygulaması oluşturduktan sonra hedeflenen bir Windows ya da .NET Framework sürümü değiştirilemiyor.

1. İçinde **hedef Framework** listesinde, kullanmak istediğiniz sürümü seçin.

1. Görüntülenen doğrulama iletişim kutusunda seçin **Evet** düğmesi.

    Projenin yüklemesi kaldırılır. Yeniden yüklediğinde, seçtiğiniz .NET Framework sürümünü hedefler.

    > [!NOTE]
    > Kodunuz hedeflediğinizden farklı bir .NET Framework sürümüne başvurular içeriyorsa, kodu derlediğinizde veya çalıştırdığınızda hata iletileri görülebilir. Bu hataları gidermek için başvuruları değiştirmeniz gerekir. Bkz: [.NET Framework hedefleme hatalarının sorunlarını giderme](../msbuild/troubleshooting-dotnet-framework-targeting-errors.md).

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio Çoklu Sürüm Desteğine Genel Bakış](../ide/visual-studio-multi-targeting-overview.md)  
[.NET Framework Hedefleme Hatalarının Sorunlarını Giderme](../msbuild/troubleshooting-dotnet-framework-targeting-errors.md)  
[Uygulama Sayfası, Proje Tasarımcısı (C#)](../ide/reference/application-page-project-designer-csharp.md)  
[Uygulama Sayfası, Proje Tasarımcısı (Visual Basic)](../ide/reference/application-page-project-designer-visual-basic.md)  
[Nasıl yapılır: hedef Framework ve Platform araç takımı (C++) değiştirme](/cpp/build/how-to-modify-the-target-framework-and-platform-toolset)