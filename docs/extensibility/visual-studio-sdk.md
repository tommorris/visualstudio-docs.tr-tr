---
title: "Visual Studio SDK'sı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VSSDK.v90.StartPage
helpviewer_keywords:
- Visual Studio SDK
- VS SDK (see Visual Studio SDK)
- Visual Studio, SDK
ms.assetid: 1f7c348a-114c-4243-b392-3531e9c9c6fd
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: bf8c558d01538d477aee3670b3c119d72a83878d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="visual-studio-sdk"></a>Visual Studio SDK
Visual Studio SDK, Visual Studio özellikleri genişletme veya Visual Studio'ya yeni özellikler tümleştirmenize yardımcı olur. Uzantılarınızın diğer kullanıcıların yanı sıra Visual Studio Market'te dağıtabilirsiniz. Visual Studio genişletebilirsiniz yolları bazıları şunlardır:  
  
-   IDE komutlar, düğmeler, menüler ve diğer kullanıcı Arabirimi öğeleri ekleme  
  
-   Araç pencereleri yeni işlevsellik için ekleme  
  
-   Belirli bir dil için IntelliSense genişletme veya yeni programlama dili için IntelliSense sağlar  
  
-   Ampuller ipuçları ve geliştiricilerin yardımcı önerileri daha iyi bir kod yazmak sağlamak için kullanın  
  
-   Yeni bir dil desteğini etkinleştirme  
  
-   Özel proje türü ekleme  
  
-   Geliştiriciler Visual Studio Market'te aracılığıyla milyonlarca ulaşma  
  
 Visual Studio uzantısı önce hiçbir zaman yazdıysanız en ve bu özellikler hakkında daha fazla bilgi bulmalısınız [geliştirmek Visual Studio uzantıları başlangıç](../extensibility/starting-to-develop-visual-studio-extensions.md).  
  
## <a name="installing-the-visual-studio-sdk"></a>Visual Studio SDK yükleme  
 Visual Studio SDK, Visual Studio kurulumunda isteğe bağlı bir özelliktir. VS SDK'yı daha sonra da yükleyebilirsiniz. Daha fazla bilgi için bkz: [Visual Studio SDK'sını yükleme](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="whats-new-in-the-visual-studio-2017-sdk"></a>Visual Studio 2017 SDK'da yenilikler nelerdir?  
 Visual Studio SDK içinde VSIX v3 biçimini yanı sıra yeni uzantınızı güncelleştirmenizi gerektiren değişiklikler gibi bazı yeni özellikler vardır. Daha fazla bilgi için bkz: [Visual Studio 2017 SDK yenilikler](../extensibility/what-s-new-in-the-visual-studio-2017-sdk.md).  
  
## <a name="visual-studio-user-experience-guidelines"></a>Visual Studio kullanıcı deneyimi yönergeleri  
 Uzantı için kullanıcı Arabirimi tasarlamak için harika ipuçları alın [Visual Studio kullanıcı deneyimi yönergeleri](../extensibility/ux-guidelines/visual-studio-user-experience-guidelines.md).  
  
 Ayrıca uzantınız ile yüksek DPI cihazlarda harika Ara nasıl öğrenebilirsiniz bizim [adresleme DPI sorunları](../extensibility/addressing-dpi-issues2.md) konu.  
  
 Yararlanmak [Görüntü hizmeti ve Katalog](../extensibility/image-service-and-catalog.md) mükemmel görüntü yönetimi ve yüksek DPI ve tema için destek.  
  
## <a name="finding-and-installing-existing-visual-studio-extensions"></a>Bulma ve mevcut Visual Studio uzantıları yükleme  
 Visual Studio uzantıları bulabilirsiniz **Uzantılar ve güncelleştirmeler** iletişim kutusunda **Araçları** menüsü. Daha fazla bilgi için bkz: [bulma ve Visual Studio uzantılarını kullanarak](../ide/finding-and-using-visual-studio-extensions.md). Uzantıları bulabileceğiniz [Visual Studio Market'te](https://marketplace.visualstudio.com/)  
  
## <a name="visual-studio-sdk-reference"></a>Visual Studio SDK'sı başvurusu  
 Visual Studio SDK API Başvurusu, bulabilirsiniz [Visual Studio SDK'sı başvurusu](../extensibility/visual-studio-sdk-reference.md).  
  
## <a name="visual-studio-sdk-samples"></a>Visual Studio SDK örnekleri  
 VS SDK uzantıları açık kaynak örnekleri GitHub üzerinde bulabilirsiniz [Visual Studio örnekleri](https://aka.ms/vs2015sdksamples). Bu GitHub deposuna Visual Studio çeşitli Genişletilebilir özellikleri göstermek örnekleri içerir.  
  
## <a name="other-visual-studio-sdk-resources"></a>Diğer Visual Studio SDK kaynakları  
 VSSDK hakkında sorularınız varsa veya uzantıları geliştirme deneyimlerinizi paylaşmak istiyorsanız kullanabileceğiniz [Visual Studio genişletilebilirlik Forumu](https://social.msdn.microsoft.com/Forums/vstudio/home?forum=vsx) veya [ExtendVS Gitter Chatroom](https://gitter.im/Microsoft/extendvs).  
  
 Daha fazla bilgi bulabilirsiniz [VSX Arcana blog](http://blogs.msdn.com/b/vsx/) ve Microsoft MVPs tarafından yazılan bloglar sayısı:  
  
-   [Sık kullanılan Visual Studio uzantıları](http://geekswithblogs.net/sdorman/archive/2014/10/05/favorite-visual-studio-extensions.aspx)  
  
-   [Visual Studio genişletilebilirlik](http://www.visualstudioextensibility.com/overview/vs/)  
  
-   [Visual Studio genişletme](http://blog.slaks.net/2013-10-18/extending-visual-studio-part-1-getting-started/)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Menü komutu ile bir uzantısı oluşturma](../extensibility/creating-an-extension-with-a-menu-command.md)   
 [Nasıl yapılır: Visual Studio 2017 genişletilebilirlik projeleri geçirme](../extensibility/how-to-migrate-extensibility-projects-to-visual-studio-2017.md)   
 [Sık sorulan sorular: Eklentiler VSPackage Uzantıları dönüştürme](../extensibility/faq-converting-add-ins-to-vspackage-extensions.md)   
 [Yönetilen kod birden çok iş parçacığı yönetme](../extensibility/managing-multiple-threads-in-managed-code.md)   
 [Genişletme menüleri ve komutları](../extensibility/extending-menus-and-commands.md)   
 [Araç çubukları komut ekleme](../extensibility/adding-commands-to-toolbars.md)   
 [Genişletme ve aracı Windows özelleştirme](../extensibility/extending-and-customizing-tool-windows.md)   
 [Düzenleyici ve dil hizmeti uzantıları](../extensibility/editor-and-language-service-extensions.md)   
 [Projeleri genişletme](../extensibility/extending-projects.md)   
 [Genişletme kullanıcı ayarları ve seçenekleri](../extensibility/extending-user-settings-and-options.md)   
 [Özel proje ve öğe şablonları oluşturma](../extensibility/creating-custom-project-and-item-templates.md)   
 [Özellikler ve özellik penceresi genişletme](../extensibility/extending-properties-and-the-property-window.md)   
 [Visual Studio diğer bölümleri genişletme](../extensibility/extending-other-parts-of-visual-studio.md)   
 [Kullanarak ve hizmetleri sağlar](../extensibility/using-and-providing-services.md)   
 [VSPackages yönetme](../extensibility/managing-vspackages.md)   
 [Visual Studio yalıtılmış Kabuk](../extensibility/visual-studio-isolated-shell.md)   
 [Visual Studio uzantıları aktarma](../extensibility/shipping-visual-studio-extensions.md)   
 [Visual Studio SDK içinde](../extensibility/internals/inside-the-visual-studio-sdk.md)   
 [Visual Studio SDK'sı için destek](../extensibility/support-for-the-visual-studio-sdk.md)   
 [Arşiv](../extensibility/archive.md)   
 [Visual Studio SDK Başvurusu](../extensibility/visual-studio-sdk-reference.md)
