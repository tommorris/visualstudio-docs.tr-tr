---
title: Office ve Visual Studio'da SharePoint geliştirme | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office applications [Office development in Visual Studio], about developing applications
- Office development in Visual Studio
- Office projects
- Visual Studio Tools for Office, see Office development in Visual Studio
- Office applications [Office development in Visual Studio]
- Office Business Applications
- applications [Office development in Visual Studio]
- programming [Office development in Visual Studio]
- VSTO, see Office development in Visual Studio
- Office, development with Visual Studio
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 61d9b988f0e0898f0dfe3843456b711f9f39b7c5
ms.sourcegitcommit: 1466ac0f49ebf7448ea4507ae3f79acb25d51d3e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/22/2018
---
# <a name="office-and-sharepoint-development-in-visual-studio"></a>Visual Studio'da Office ve SharePoint Geliştirme
  Microsoft Office ve SharePoint basit bir uygulama oluşturarak genişletebilir ve kullanıcılar indirir, eklenti [Office deposu](https://store.office.com/) ya da bir kuruluş katalog veya .NET Framework tabanlı bir çözümdür, kullanıcıların oluşturarak yüklemek bir bilgisayar.  
  
 Bu konuda:  
  
-   [Office ve SharePoint için eklentileri oluşturma](#Apps)  
  
-   [Bir VSTO eklentisi oluşturma](#Add-ins)  
  
-   [Bir SharePoint çözüm oluşturma](#Solutions)  
  
##  <a name="Apps"></a> Office ve SharePoint için eklentileri oluşturma  
 Office 2013 ve SharePoint 2013 oluşturmak, dağıtmak ve Office ve SharePoint genişletmek eklentiler paraya çevirme yardımcı olan yeni bir eklenti modeli sunar.  Bu eklenti Office veya SharePoint Online çalıştırabilir ve kullanıcılar bunlarla birçok aygıtlardan etkileşim kurabilirsiniz.  
  
 Yeni nasıl öğrenmek [Office eklenti modeli](https://msdn.microsoft.com/library/office/jj220082.aspx) kullanıcılarınız için Office deneyimi genişletmek için.  
  
 Bu eklentilerin VSTO eklentilerini ve çözümlerle karşılaştırıldığında çok küçük in sahip ve teknoloji HTML5, JavaScript, CSS3 ve XML gibi programlama neredeyse her web kullanarak oluşturabilirsiniz.  Başlamak için Visual Studio'da Office geliştirici araçları veya düzeltme basit web tabanlı bir araç kullanın Napa Office 365 geliştirme projeleri oluşturma, kod yazmanız ve bir tarayıcıda eklentilerinizi çalıştırmanıza olanak sağlayan araçları, kod adıyla.  
  
 ![Office ve SharePoint kavramsal model için uygulamalar](../vsto/media/officeandsharepointapps2015.png "Office ve SharePoint kavramsal model için uygulamalar")  
  

  
### <a name="build-an-office-add-in"></a>Bir Office Eklentisi oluşturma  
 Office işlevselliğini genişletmek için Office Eklentisi oluşturun. Temel olarak, Excel, Word, Outlook ve PowerPoint gibi bir Office uygulamasında barındırılan bir Web sayfasıdır. Uygulamanızı işlevselliği belgelere, çalışma sayfaları, e-posta iletilerini, randevuları, sunuları ve projeleri ekleyebilirsiniz.  
  
 Uygulamanızı Office deposundaki satmak.  [Office deposu](https://store.office.com/) eklentilerinizi paraya çevirme, güncelleştirmeleri yönetmek ve izlemek telemetri daha kolay hale getirir. Ayrıca, bir uygulama Kataloğu SharePoint ya da Exchange Server aracılığıyla kullanıcılara uygulamanızı yayımlayabilirsiniz.  
  
 Office için aşağıdaki uygulama çalışma sayfası verileri bir Bing harita gösterir.  
  
 ![Office için içerik uygulama](../vsto/media/appforoffice.png "Office için içerik uygulama")  
  
 **Daha fazla bilgi edinin**  
  
|Bitiş|Bkz. |  
|--------|---------|  
|Office eklentileri hakkında daha fazla bilgi ve bir yapı.|[Office eklentileri](http://msdn.microsoft.com/office/dn448457)|  
|İçinde Office ve genişletmek için kullanabileceğiniz, bir uygulama veya bir Office Eklentisi kullanıp kullanmayacağınızı karar farklı yolları karşılaştırın.|[Office eklentileri, VSTO ve VBA için yol haritası](http://blogs.msdn.com/b/officeapps/archive/2013/06/18/roadmap-for-apps-for-office-vsto-and-vba.aspx)|  
  
### <a name="build-a-sharepoint-add-in"></a>Bir SharePoint eklentisi oluşturma  
 Kullanıcılarınız için SharePoint genişletmek için bir SharePoint eklentisi oluşturun. Temel olarak, kullanıcılar ya da iş gereksinimini çözdü küçük, kullanımı kolay, tek başına bir uygulama olduğundan.  
  
 SharePoint için uygulamanızı satmak [Office deposu](https://store.office.com/). Ayrıca, eklenti bir eklenti katalog SharePoint aracılığıyla kullanıcılara yayımlayabilirsiniz.  Site sahipleri yüklemek, yükseltmek ve eklentinizi grubu sunucusu veya site koleksiyonu Yöneticisi Yardımı olmadan SharePoint sitelerinde kaldırma.  
  
 Bir uygulama kullanıcıların kişilerden yönetmenize yardımcı olan SharePoint için bir örneği burada verilmiştir.  
  
 ![SharePoint için iş Kişi Yöneticisi uygulama](../vsto/media/appforsharepoint.png "SharePoint için iş Kişi Yöneticisi uygulama")  
  
 **Daha fazla bilgi edinin**  
  
|Bitiş|Bkz. |  
|--------|---------|  
|SharePoint eklentiler hakkında daha fazla bilgi ve bir yapı.|[SharePoint eklentileri](https://msdn.microsoft.com/library/office/fp179930.aspx)|  
|Eklentiler için SharePoint ile geleneksel SharePoint çözümlerini karşılaştırın.|[SharePoint çözümleri ile karşılaştırıldığında SharePoint eklentileri](http://msdn.microsoft.com/library/office/jj163114.aspx)|  
|Bir SharePoint eklentisi veya bir SharePoint çözüm oluşturmak isteyip istemediğinizi seçin.|[SharePoint eklentiler ve SharePoint çözümleri arasında seçim yapma](https://msdn.microsoft.com/library/office/jj163114.aspx)|
  
##  <a name="Add-ins"></a> Bir VSTO eklentisi oluşturma  
 Bir VSTO eklentisinin Office 2007 veya Office 2010'u hedefleyecek şekilde ya da Office 2013 ve Office 2016 ile Office eklentileri olası nedir ötesine genişletmek için oluşturun. VSTO eklentilerini yalnızca masaüstünde çalıştırın. Kullanıcıların VSTO eklentileri, dağıtmak ve Destek genellikle daha zor bulunmaları yüklemeniz gerekir.  Ancak, VSTO eklentinizi daha yakından Office ile tümleştirilebilir. Örneğin, bunu sekmeler ve denetimler için Office Şerit ekleyin ve belgelerin birleştirilmesi veya grafikleri değiştirme gibi gelişmiş bir otomatikleştirme görevleri gerçekleştirin. Office nesnelerle etkileşim kurmak için C# ve Visual Basic kullanın ve .NET Framework yararlanın.  
  
 Burada, hangi bir VSTO eklentisinin yapmak için bir örnek verilmiştir. Bu VSTO eklentisinin PowerPoint'e Şerit denetimleri, özel görev bölmesini ve bir iletişim kutusu ekler.  
  
 ![PowerPoint eklenti çözümü](../vsto/media/powerpointaddin.png "PowerPoint eklenti çözümü")  
  
 **Daha fazla bilgi edinin**  
  
|Bitiş|Oku|  
|--------|----------|  
|İçinde Office ve genişletmek için kullanabileceğiniz, bir VSTO eklentisinin veya bir Office Eklentisi kullanıp kullanmayacağınızı karar farklı yolları karşılaştırın.|[Office eklentileri, VSTO ve VBA için yol haritası](http://blogs.msdn.com/b/officeapps/archive/2013/06/18/roadmap-for-apps-for-office-vsto-and-vba.aspx)|  
|Bir VSTO eklentisinin oluşturun.|[Visual Studio ile VSTO eklentileri oluşturma](https://msdn.microsoft.com/library/jj620922.aspx)|  
  
##  <a name="Solutions"></a> Bir SharePoint çözüm oluşturma  
 Hedef SharePoint Foundation 2010 ve SharePoint Server 2010 veya SharePoint 2013 ve SharePoint 2016 yolla SharePoint eklentisi ile olası olanların ötesine genişletmek için bir SharePoint çözüm oluşturun.  
  
 SharePoint çözümleri şirket içi SharePoint grubunun sunucuları gerektirir. Yöneticiler bunları yüklemeniz ve çözümleri SharePoint'te yürüttüğünden, sunucu performansını etkileyebilir. Ancak, çözümleri daha derin SharePoint nesnelerine erişimi sağlar. Ayrıca, bir SharePoint çözüm oluşturduğunuzda, .NET Framework yararlanır ve SharePoint nesnelerle etkileşim kurmak için C# ve Visual Basic kullanabilirsiniz.  
  
 **Daha fazla bilgi edinin**  
  
|Bitiş|Bkz. |  
|--------|---------|  
|SharePoint çözümlerini SharePoint eklentileri ile karşılaştırın.|[SharePoint çözümleri ile karşılaştırıldığında SharePoint eklentileri](http://msdn.microsoft.com/library/office/jj163114.aspx)|  
|Bir SharePoint çözüm oluşturun.|[SharePoint Çözümleri Oluşturma](../sharepoint/create-sharepoint-solutions.md)|  
  
  
