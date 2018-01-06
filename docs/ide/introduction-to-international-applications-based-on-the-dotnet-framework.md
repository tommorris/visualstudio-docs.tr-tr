---
title: "Uluslararası uygulamalara giriş .NET Framework'e dayalı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- strings [Visual Studio], localizing
- Web applications [.NET Framework], globalization
- Windows Forms, globalization
- localization [Visual Studio], culture setting
- fallback resources
- culture, setting
- globalization [Visual Studio], culture setting
- resources [Visual Studio], localization
- localization [Visual Studio], .NET localization model
- Assembly Resource file template
- resources [Visual Studio], fallback system
- international applications [Visual Studio], about international applications
- globalization [Visual Studio], international applications
- ASP.NET, globalization
- resource files, fallback processes
- user interface, culture setting
ms.assetid: b0788993-e62d-4f68-8235-5f87b1d48525
caps.latest.revision: "11"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: dotnet
ms.openlocfilehash: 9acc8f2e015b6ca2ad26881eeb1f53012d96e56d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="introduction-to-international-applications-based-on-the-net-framework"></a>.NET Framework Tabanlı Uluslararası Uygulamalara Giriş
İçinde [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], dünya çapında kullanılmaya hazır uygulaması oluşturmak için iki bölümden oluşur: genelleştirme, farklı kültürlere uygulamalar tasarlama işlemi ve yerelleştirme, belirli bir kültür için kaynaklar çevirme işlemi. Uluslararası bir izleyici için uygulama tasarlama hakkında genel bilgi için bkz: [dünya çapında kullanılmaya hazır uygulamalar geliştirmek için en iyi uygulamaları](http://msdn.microsoft.com/Library/f08169c7-aad8-4ec3-9a21-9ebd3b89986c).  
  
 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] Yerelleştirme modeli hem uygulama kodunda hem de geri dönüş kaynakları içeren bir ana derlemeden oluşur — dizeler, görüntüler ve diğer nesneler için hangi uygulama ilk olarak geliştirilen dili. Yerelleştirilmiş her uygulama, uydu derlemelerini veya yalnızca yerelleştirilmiş kaynakları içeren derlemeler sahip olur. Ana derleme her zaman bir kaynak yerelleştirilmiş uydu derlemesinde bulunmazsa geri dönüş kaynakları içerdiğinden <xref:System.Resources.ResourceManager> sonunda ana derlemedeki kaynağa geri dönmeden hiyerarşik bir biçimde yüklemeyi deneyecek. Kaynak geri dönüş sistemi daha ayrıntılı olarak anlatılmıştır [yerelleştirme, hiyerarşik kuruluş kaynakları](../ide/hierarchical-organization-of-resources-for-localization.md).  
  
 Tüm Microsoft sözlüğü kullanmaktır dikkate almanız gereken bir yerelleştirme kaynağı ürünleri yerelleştirilmiş. Bu CSV dosyası üzerinde 12.000 İngilizce koşulları koşullarını 59 farklı dilde çevirileri içerir. Sözlük indirmek için kullanılabilir [Microsoft terminoloji çevirileri](http://go.microsoft.com/fwlink/?LinkId=128146) Web sayfası.  
  
 Her istenilen ek UI kültürü ve Windows Forms uygulamalarına ilişkin proje sistemi hem geri dönüş için kaynak dosyaları oluşturabilirsiniz. Geri dönüş kaynak dosyası ana derlemeye oluşturulur ve kültüre özgü kaynak dosyaları, her UI kültürü için bir uydu derlemelerini içinde yerleşik. Proje oluşturma sırasında kaynak dosyaları Visual Studio XML biçimi (.resx) Ara bir ikili biçime (.resources), ardından uydu derlemeleri katıştırılmış derlenir.  
  
 Windows Forms ve Web formları için proje sistemi, bir derleme kaynak dosyası şablonu kullanarak kaynak dosyaları derleme, kaynaklara erişmek ve projenizi derleme olanak sağlar. Uydu derlemeleri yanı sıra ana derleme oluşturulur.  
  
 Yerelleştirilmiş bir uygulama yürütüldüğünde, görünümünü iki kültür değerine göre belirlenir. (A *kültür* kullanıcının dil, ortam ve kültürel kuralları ilişkili kullanıcı tercihi bilgisini kümesidir.) UI kültürü ayarı hangi kaynakların yükleneceğini belirler. UI kültürü olarak ayarlanmış olan `UICulture` Web.config dosyaları ve sayfa yönergelerinde ve <xref:System.Globalization.CultureInfo.CurrentUICulture%2A> Visual Basic veya Visual C# kod. Kültür ayarı tarihler, sayılar, para birimi vb. gibi değerler biçimini belirler. Kültür olarak ayarlanmış olan `Culture` Web.config dosyaları ve sayfa yönergelerinde <xref:System.Globalization.CultureInfo.CurrentCulture%2A> Visual Basic veya Visual C# kod.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Globalization>   
 <xref:System.Resources>   
 [Uygulamaları Genelleştirme ve yerelleştirme](../ide/globalizing-and-localizing-applications.md)   
 [Güvenlik ve Yerelleştirilmiş Yardımcı Derlemeler](../ide/security-and-localized-satellite-assemblies.md)