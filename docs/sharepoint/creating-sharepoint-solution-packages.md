---
title: "SharePoint çözüm paketleri oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, packages
- packages [SharePoint development in Visual Studio]
ms.assetid: 6b1f1fbf-fa9c-453d-80af-36ec9829677a
caps.latest.revision: "25"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: fe7822382443e6c1e9bc1a77eb0cd64844504172
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="creating-sharepoint-solution-packages"></a>SharePoint Çözüm Paketleri Oluşturma
  Paket Tasarımcısını kullanarak oluşturabilir ve dağıtım paketleri özelleştirebilirsiniz. Örneğin, SharePoint Proje öğeleri ve özellikler, IIS sunucusu sıfırlandığında, özelliğini etkinleştirme kapsamlarını ayarlayın ve özellik bağımlılıkları tanımlamak ekleyebilirsiniz. Tasarımcı de bildirim, her paket tanımlayan bir XML dosyası oluşturur.  
  
## <a name="packaging-tools"></a>Paketleme araçları  
 Kullanabileceğiniz **paket tasarımcısını** paket özelleştirmek ve bildirim oluşturmak için. SharePoint Proje öğeleri içerir, Web sunucusu sıfırlamak ve dağıtım sunucusu türü ayarlamak olup olmadığını yapılandırın. Daha fazla bilgi için bkz: [nasıl yapılır: ekleyip özellikler ve öğeler bir paket için paket Tasarımcısını kullanarak](../sharepoint/how-to-add-and-remove-features-and-items-to-a-package-by-using-the-package-designer.md).  
  
 Alternatif olarak, kullanabileceğiniz **paketleme Gezgini'ni** özellikler ve öğeler paket dosyası (.wsp) değiştirmek için. Daha fazla bilgi için bkz: [nasıl yapılır: ekleyip özellikler ve öğeler bir pakete paketleme Gezgini'ni kullanarak](../sharepoint/how-to-add-and-remove-features-and-items-to-a-package-by-using-the-packaging-explorer.md).  
  
 SharePoint çözümünüzü dağıtmak için paket (.wsp) dosyalarını oluşturmak için Visual Studio ve MSBuild kullanabilirsiniz. Bu işlem SharePoint dağıtım için gerekli bildirim dosyası oluşturur. Daha fazla bilgi için bkz [nasıl yapılır: bir SharePoint paketi oluşturmak](http://msdn.microsoft.com/en-us/b24be45c-e91d-49bb-afb0-7b265404214b) ve [nasıl yapılır: MSBuild görevlerini kullanarak tarafından bir SharePoint çözüm paketi oluşturma](../sharepoint/how-to-create-a-sharepoint-solution-package-by-using-msbuild-tasks.md).  
  
## <a name="package-designer-options"></a>Paket Tasarımcı seçenekleri  
 Aşağıdaki tabloda, SharePoint paketlerde özelleştirebilirsiniz özellikleri gösterir **paket tasarımcısını**.  
  
|Paket tasarlayıcı özelliği|Varsayılan ayar açıklaması|  
|-------------------------------|------------------------------------|  
|Ad|Gerekli. Paketin varsayılan adını ayarlamak *ProjectName*.|  
|Web sunucusu Sıfırla|İsteğe bağlı. .Wsp dosyasını SharePoint sunucusuna yüklendikten sonra Web sunucusunu yeniden başlatmak istiyorsanız seçin.|  
|Dağıtım sunucusu türü|Gerekli. Varsayılan olarak, kapsam ApplicationServer için ayarlanır.<br /><br /> ApplicationServer: hizmetlerini barındıran bir sunucu açıklar.<br /><br /> WebFrontEnd: Web sitelerini barındıran bir sunucu açıklar.|  
|Çözüm öğeleri|Tüm SharePoint Proje öğeleri ve pakete eklenen özellikler.|  
|Paket öğeleri|İsteğe bağlı. Tüm SharePoint öğeleri ve paketinizdeki dağıtmak istediğiniz özellikleri.|  
  
## <a name="configuring-the-packaging-process"></a>Paketleme işlemini yapılandırma  
 Visual Studio'da SharePoint çözümleri geliştirmek sonra projeleri nasıl paketlenir özelleştirebilirsiniz.  
  
 Aşağıdaki tabloda .wsp dosyası nasıl oluşturulur özelleştirmek için kullanabileceğiniz iki MSBuild hedefleri gösterir.  
  
|Hedef|Açıklama|  
|------------|-----------------|  
|BeforeLayout|Dosyaları bir ara dizinine hemen kopyalanmadan önce görevleri gerçekleştiren hedefi. Bir paket dosyası (.wsp) oluşturmadan önce dosyalarda değişiklik yapabilir.|  
|AfterLayout|Dosyalar bir ara dizinine hemen kopyalandıktan sonra görevleri gerçekleştiren hedefi.|  
  
 Daha fazla bilgi için [nasıl yapılır: MSBuild hedeflerini kullanarak tarafından bir SharePoint çözüm paketini özelleştirme](../sharepoint/how-to-customize-a-sharepoint-solution-package-by-using-msbuild-targets.md).  
  
## <a name="packaging-architecture"></a>Paketleme mimarisi  
 Visual Studio'da SharePoint paketi (.wsp) oluşturduğunuzda, aşağıdaki adımlar gerçekleşir.  
  
1.  Paketler ve özellikler, paket fiziksel ve anlam yapısını doğru olduğundan emin olmak için doğrulanır.  
  
2.  Özellikler, proje öğeleri ve paket dosyaları paketindeki numaralandırılır. Paketler ve özellikler için bildirim dosyası, dağıtım ve etkinleştirme için gerekli tüm bilgileri içerecek şekilde dönüştürülür. Belirteçleri tam değeriyle değiştirilir.  
  
3.  Özelleştirilebilir BeforeLayout MSBuild hedef gerçekleştirilir. .Wsp dosyası oluşturulmadan önce paketin özel değişiklikler yapmak için bu adımı oluşturabilirsiniz.  
  
4.  Numaralandırılmış dosyalar bir ara dizinine kopyalanır.  
  
5.  Özelleştirilebilir AfterLayout MSBuild hedef gerçekleştirilir. .Wsp dosyası oluşturulmadan önce paketin özel değişiklikler yapmak için bu adımı oluşturabilirsiniz.  
  
6.  Ara dizindeki dosyaların .wsp dosyasına eklenir.  
  
## <a name="package-folder-structure"></a>Paket klasör yapısı  
 SharePoint Proje paketini oluşturduğunuzda .wsp dosyası SolutionFolder\bin oluşturulur\\*BuildConfiguration* klasör. Örneğin, çözümünüz içinde ise *sürücü*: \Visual Studio 2013\Projects\ListDefinition1 ve derleme yapılandırması yayın olarak ayarlanır, .wsp dosya bulunan *sürücü*: \Visual Studio 2013\ Projects\ListDefinition1\bin\Release.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: Bir SharePoint Çözüm Paketini Özelleştirme](../sharepoint/how-to-customize-a-sharepoint-solution-package.md)  
 [Nasıl yapılır: ekleme ve kaldırma özellikler ve öğeler bir paket için paket Tasarımcısını kullanarak](../sharepoint/how-to-add-and-remove-features-and-items-to-a-package-by-using-the-package-designer.md)   
 [Nasıl yapılır: bir SharePoint paketi oluşturma](http://msdn.microsoft.com/en-us/b24be45c-e91d-49bb-afb0-7b265404214b)   
 [Nasıl yapılır: MSBuild görevlerini kullanarak bir SharePoint çözüm paketi oluşturma](../sharepoint/how-to-create-a-sharepoint-solution-package-by-using-msbuild-tasks.md)   
 [Nasıl yapılır: MSBuild Hedeflerini Kullanarak SharePoint Çözüm Paketini Özelleştirme](../sharepoint/how-to-customize-a-sharepoint-solution-package-by-using-msbuild-targets.md)  
  
  