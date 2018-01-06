---
title: "Nasıl yapılır: projeleri hedef platformlar için yapılandırma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "13"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 0ccca87721c39daa7e613d7426c9d5fed6a144cf
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-configure-projects-to-target-platforms"></a>Nasıl Yapılır: Projeleri Hedef Platformlar İçin Yapılandırma
[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]uygulamalarınızı 64-bit platformları da dahil olmak üzere, farklı platformları hedeflemesi için ayarlamanıza olanak tanır. 64-bit platformu hakkında daha fazla bilgi için destek [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], bkz: [64-bit uygulamalar](http://msdn.microsoft.com/Library/fd4026bc-2c3d-4b27-86dc-ec5e96018181).  
  
## <a name="targeting-platforms-with-the-configuration-manager"></a>Configuration Manager ile platformları hedefleme  
 **Configuration Manager** hızla yeni bir platformu projenizle hedef eklemek bir yol sağlar. İle birlikte gelen platformları birini seçerseniz [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], seçilen platform için projeyi derlemek için projenizi özelliklerini değiştirdi.  
  
#### <a name="to-configure-a-project-to-target-a-64-bit-platform"></a>Bir 64-bit platformu hedeflemek için bir proje yapılandırma  
  
1.  Menü çubuğunda seçin **yapı**, **Configuration Manager**.  
  
2.  İçinde **etkin çözüm platformu** listesinde, hedef çözüme 64-bit platformu seçin ve ardından **Kapat** düğmesi.  
  
    1.  İstediğiniz platform görünmüyorsa **etkin çözüm platformu** listesinde, seçin **yeni**.  
  
         **Yeni çözüm platformu** iletişim kutusu görüntülenir.  
  
    2.  İçinde **yazın veya seçin yeni platformu** listesinde, seçin **x64**.  
  
        > [!NOTE]
        >  Yapılandırmanızı yeni bir ad verin, ayarları değiştirmek zorunda kalabilirsiniz **Proje Tasarımcısı** doğru platform hedeflemek için.  
  
    3.  Geçerli bir platform yapılandırmasından ayarları kopyalamak istiyorsanız, o bağlantıyı seçin ve ardından **Tamam** düğmesi.  
  
 64-bit platformu hedefleyen tüm projelerde özelliklerini güncelleştirilir ve sonraki derleme projesinin 64-bit platformları için iyileştirilir.  
  
## <a name="targeting-platforms-in-the-project-designer"></a>Proje Tasarımcısı'nda platformları hedefleme  
 Proje Tasarımcısı da projenizle farklı platformları hedeflemesi için bir yol sağlar. Listede bulunan platformları birini seçerek, **yeni çözüm platformu** iletişim kutusu, çözümünüz için çalışmaz, özel yapılandırma adı oluşturun ve ayarlarında değişiklik **Proje Tasarımcısı**  doğru platform hedeflemek için.  
  
 Bu görevi gerçekleştirme kullandığınız programlama diline göre değişir. Daha fazla bilgi için aşağıdaki bağlantılara bakın:  
  
-   İçin [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] projeleri, bkz: [/Platform (Visual Basic)](/dotnet/visual-basic/reference/command-line-compiler/platform).  
  
-   İçin [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] projeleri, bkz: [derleme sayfası, Proje Tasarımcısı (C#)](../ide/reference/build-page-project-designer-csharp.md).  
  
-   İçin [!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)] projeleri, bkz: [/CLR (ortak dil çalışma zamanı derlemesi)](/cpp/build/reference/clr-common-language-runtime-compilation).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapı platformlarını anlama](../ide/understanding-build-platforms.md)   
 [/ Platform (C# Derleyici Seçenekleri)](/dotnet/csharp/language-reference/compiler-options/platform-compiler-option)   
 [64-bit uygulamalar](http://msdn.microsoft.com/Library/fd4026bc-2c3d-4b27-86dc-ec5e96018181)   
 [Visual Studio IDE 64 Bit Desteği](../ide/visual-studio-ide-64-bit-support.md)