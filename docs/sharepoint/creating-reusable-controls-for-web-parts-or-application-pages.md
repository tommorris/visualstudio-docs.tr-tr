---
title: Web Bölümleri veya uygulama sayfaları için yeniden kullanılabilir denetimler oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- user controls [SharePoint development in Visual Studio], creating
- SharePoint development in Visual Studio, user controls
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: e76a13174a9ac980644f8f9116c6518fc853028c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="creating-reusable-controls-for-web-parts-or-application-pages"></a>Web Bölümleri veya Uygulama Sayfaları için Yeniden Kullanılabilir Denetimler Oluşturma
  Visual Studio'da Uygulama sayfaları ve SharePoint çalıştıran Web bölümleri tarafından kullanılabilecek özel, yeniden kullanılabilir denetimler oluşturabilirsiniz. Bu denetimler, kullanıcı denetimleri denir. Bir kullanıcı denetimi, bir ASP.NET Web sayfası benzer çalışır bileşik denetim türüdür — varolan Web sunucusu denetimleri ve biçimlendirme kullanıcı denetimine ekleyin ve denetim için özellikleri ve yöntemleri tanımlar. Sonra bunları burada bunlar bir birim olarak hareket ASP.NET Web sayfalarında eklenebilir.  
  
## <a name="creating-a-user-control"></a>Bir kullanıcı denetimi oluşturma  
 Bir kullanıcı denetimi oluşturmak için Ekle bir **kullanıcı denetimi** için bir **boş SharePoint proje**. Daha fazla bilgi için bkz: [nasıl yapılır: bir SharePoint uygulama sayfası veya Web Bölümü için bir kullanıcı denetimi oluşturma](../sharepoint/how-to-create-a-user-control-for-a-sharepoint-application-page-or-web-part.md).  
  
 Eklediğinizde bir **kullanıcı denetimi** öğesi, Visual Studio projenizi bir klasör oluşturur ve ardından birkaç dosyaları klasörüne ekler. Aşağıdaki tabloda, her dosya açıklanmaktadır.  
  
|Dosya|Açıklama|  
|----------|-----------------|  
|Kullanıcı denetim dosyası|Kullanıcı denetimi tanımlar. Kullanıcı denetiminin denetimleri ve biçimlendirme bu dosyasına ekleyerek tasarlayın.|  
|Kod dosyası|Kullanıcı denetiminin arka plan kod içerir. Bu dosyaya olayları işlemek için kodu ekleyin.|  
|Tasarımcı kod dosyası|Tasarımcı tarafından oluşturulan kodu içerir ve doğrudan düzenlenmemelidir.|  
  
## <a name="designing-the-user-control"></a>Kullanıcı denetiminin tasarlama  
 Visual Studio'da Visual Web Developer Tasarımcısı'nı kullanarak kullanıcı denetimi tasarlayın. Projenizde kullanıcı Denetim dosyasını açın ve seçmek bu tasarımcıya görünür **tasarım** sekmesi.  

## <a name="consuming-the-user-control"></a>Kullanıcı denetimi kullanma  
 Kullanıcı denetimleri, bunları bir uygulama sayfası veya bir Web Bölümü dahil kadar SharePoint'te görünmez.  
  
 Bir kullanıcı denetimi'nda uygulama sayfası eklemek için ASP.NET kullanıcı denetimini eklemek istediğiniz Web sayfasını açın. Tasarım görünümüne geçiş sonra Çözüm Gezgini'nde, özel kullanıcı Denetim dosyası seçin ve sayfaya sürükleyin. ASP.NET kullanıcı denetimini sayfasına eklenir ve sayfanın kullanıcı denetimi tanımak için gerekli olan @ Register yönergesi Tasarımcısı oluşturur. Şimdi, denetimin genel özellikleri ve yöntemleri ile çalışabilirsiniz.  
  
 Bir kullanıcı denetimi bir Web Bölümü eklemek için Web Bölümü için kullanıcı denetimi Ekle <xref:System.Web.UI.WebControls.WebParts.Part.Controls%2A> Web Bölümü kod dosyasında koleksiyonu. Aşağıdaki örnek, bir kullanıcı denetimi <xref:System.Web.UI.WebControls.WebParts.Part.Controls%2A> bir Web Bölümü topluluğu.  
  
 [!code-vb[SP_VisualWebPart#5](../sharepoint/codesnippet/VisualBasic/sp_visualwebpart.vb/visualwebpart1/visualwebpart1.vb#5)]
 [!code-csharp[SP_VisualWebPart#5](../sharepoint/codesnippet/CSharp/sp_visualwebpart.cs/visualwebpart1/visualwebpart1.cs#5)]  
  
## <a name="debugging-a-user-control"></a>Bir kullanıcı denetimi hata ayıklama  
 Bir kullanıcı denetimi hata ayıklamak için kullanıcı denetimi bir uygulama sayfası veya Web Bölümü SharePoint projenizde bulunduğundan emin olun. Tüm Visual Studio projesi kodda debug gibi kullanıcı denetimi kodda sonra ayıklayabilirsiniz.  
  
 Visual Studio hata ayıklayıcısını başlattığınızda, Visual Studio SharePoint sitesini açar.  
  
 SharePoint içinde kullanıcı denetimini içeren uygulama sayfasını açın. Kullanıcı denetiminin bir Web bölümü varsa, SharePoint Web Bölümü sayfasına Web bölümü ekleyin.  
  
 SharePoint projeleri hata ayıklama hakkında daha fazla bilgi için bkz: [SharePoint çözümlerinde sorun giderme](../sharepoint/troubleshooting-sharepoint-solutions.md).  
  
## <a name="related-topics"></a>İlgili Konular  
  
|Başlık|Açıklama|  
|-----------|-----------------|  
|[Nasıl yapılır: SharePoint Uygulama Sayfası veya Web Bölümü için Kullanıcı Denetimi Oluşturma](../sharepoint/how-to-create-a-user-control-for-a-sharepoint-application-page-or-web-part.md)|Uygulama sayfaları ve SharePoint çalıştıran Web bölümleri tarafından kullanılabilecek özel, yeniden kullanılabilir denetimler oluşturma gösterir.|  
  
  