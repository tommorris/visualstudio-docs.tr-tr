---
title: 'Nasıl yapılır: projeleri hedef platformlar için yapılandırma'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-compile
ms.topic: conceptual
helpviewer_keywords:
- project settings [Visual Studio], targeting platforms
- platforms, targeting specific CPUs
- project properties [Visual Studio], targeting platforms
- projects [Visual Studio], targeting platforms
- 64-bit [Visual Studio]
- 64-bit programming [Visual Studio]
- CPUs, targeting specific
- 64-bit applications [Visual Studio]
ms.assetid: 845302fc-273d-4f81-820a-7296ce91bd76
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8f5f5552cb87f1c8b4501930f23765143a9e9399
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31946695"
---
# <a name="how-to-configure-projects-to-target-platforms"></a>Nasıl yapılır: projeleri hedef platformlar için yapılandırma

Visual Studio uygulamalarınızı 64-bit platformları da dahil olmak üzere, farklı platformları hedeflemesi için ayarlamanıza olanak tanır. Visual Studio'da 64 bit platform desteği hakkında daha fazla bilgi için bkz: [64-bit uygulamalar](http://msdn.microsoft.com/Library/fd4026bc-2c3d-4b27-86dc-ec5e96018181).

## <a name="target-platforms-with-the-configuration-manager"></a>Configuration Manager ile hedef platformlar

**Configuration Manager** hızla yeni bir platformu projenizle hedef eklemek bir yol sağlar. Visual Studio ile dahil platformları birini seçerseniz, seçilen platform için projeyi derlemek için projeniz için özellikleri değiştirilmiştir.

### <a name="to-configure-a-project-to-target-a-64-bit-platform"></a>Bir 64-bit platformu hedeflemek için bir proje yapılandırma

1.  Menü çubuğunda seçin **yapı** > **Configuration Manager**.

2.  İçinde **etkin çözüm platformu** listesinde, hedef çözüme 64-bit platformu seçin ve ardından **Kapat** düğmesi.

    1.  İstediğiniz platform görünmüyorsa **etkin çözüm platformu** listesinde, seçin **yeni**.

         **Yeni çözüm platformu** iletişim kutusu görüntülenir.

    2.  İçinde **yazın veya seçin yeni platformu** listesinde, seçin **x64**.

        > [!NOTE]
        >  Yapılandırmanızı yeni bir ad verin, ayarları değiştirmek zorunda kalabilirsiniz **Proje Tasarımcısı** doğru platform hedeflemek için.

    3.  Geçerli bir platform yapılandırmasından ayarları kopyalamak istiyorsanız, o bağlantıyı seçin ve ardından **Tamam** düğmesi.

64-bit platformu hedefleyen tüm projelerde özelliklerini güncelleştirilir ve sonraki derleme projesinin 64-bit platformları için iyileştirilir.

## <a name="target-platforms-in-the-project-designer"></a>Proje Tasarımcısı'nda Hedef platformlar

**Proje Tasarımcısı** de projenizle farklı platformları hedeflemesi için bir yol sağlar. Listede bulunan platformları birini seçerek, **yeni çözüm platformu** iletişim kutusu, çözümünüz için çalışmaz, özel yapılandırma adı oluşturun ve ayarlarında değişiklik **Proje Tasarımcısı**  doğru platform hedeflemek için.

Bu görevi gerçekleştirme kullandığınız programlama diline göre değişir. Daha fazla bilgi için aşağıdaki bağlantılara bakın:

-   İçin [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] projeleri, bkz: [/Platform (Visual Basic)](/dotnet/visual-basic/reference/command-line-compiler/platform).

-   İçin [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] projeleri, bkz: [derleme sayfası, Proje Tasarımcısı (C#)](../ide/reference/build-page-project-designer-csharp.md).

-   İçin [!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)] projeleri, bkz: [/CLR (ortak dil çalışma zamanı derlemesi)](/cpp/build/reference/clr-common-language-runtime-compilation).

## <a name="see-also"></a>Ayrıca bkz.

- [Derleme platformlarını anlama](../ide/understanding-build-platforms.md)
- [/ Platform (C# Derleyici Seçenekleri)](/dotnet/csharp/language-reference/compiler-options/platform-compiler-option)
- [64-bit uygulamalar](http://msdn.microsoft.com/Library/fd4026bc-2c3d-4b27-86dc-ec5e96018181)
- [Visual Studio IDE 64-Bit desteği](../ide/visual-studio-ide-64-bit-support.md)
