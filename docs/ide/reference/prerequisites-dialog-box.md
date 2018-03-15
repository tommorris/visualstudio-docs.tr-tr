---
title: "Önkoşullar iletişim kutusu | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Microsoft.VisualStudio.Publish.BaseProvider.Dialog.Bootstrapper
helpviewer_keywords:
- Prerequisites dialog box
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 2ea735e5e300d2b2cde301a4cf52424cabbba934
ms.sourcegitcommit: e01ccb5ca4504a327d54f33589911f5d8be9c35c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/15/2018
---
# <a name="prerequisites-dialog-box"></a>Önkoşullar İletişim Kutusu

Bu iletişim kutusu, hangi önkoşul bileşenlerinin yüklü olduğu, nasıl yükleneceğini ve paketleri yüklü olan sıra belirtir.

Bu iletişim kutusunu erişmek için bir proje düğümünde seçin **Çözüm Gezgini**ve ardından **proje** menüsünde tıklatın **özellikleri**. Zaman **Proje Tasarımcısı** görünen tıklatın **Yayımla** sekmesi. Üzerinde **Yayımla** sayfasında, **Önkoşullar**. Kurulum projeleri için üzerinde **proje** menüsünde tıklatın **özellikleri**. Zaman **özellik sayfaları** iletişim kutusu görüntülenirse, tıklatın **Önkoşullar**.

## <a name="uielement-list"></a>UIElement Listesi

|Öğe|Açıklama|
|-------------|-----------------|
|**Önkoşul bileşenlerini yüklemek için Kurulum programını oluşturun**|Böylece, uygulamanızda bağımlılık sırasını önce yüklenecek önkoşul bileşenleri uygulamanızın Kurulum programını (Setup.exe) içerir. Varsayılan olarak, bu seçenek seçilidir. Seçilmezse, hiçbir Setup.exe oluşturulur.|
|**Yüklemek için hangi Önkoşullar seçin**|Bileşenleri gibi yüklenip yüklenmeyeceğini belirtir [!INCLUDE[dnprdnshort](../../code-quality/includes/dnprdnshort_md.md)], Crystal Reports ve benzeri.<br /><br /> Örneğin, onay kutusunu seçerek yanına **SQL Server 2005 Express Edition SP2**, Kurulum programı bu bileşen hedef bilgisayar üzerinde yüklü olduğundan ve zaten yüklü değilse yükleyin olup olmadığını doğrulayın belirtin.<br /><br /> Önkoşul her paket hakkında ayrıntılı bilgi için bu konunun ilerleyen bölümlerinde önkoşul bilgilerini tabloya bakın.|
|**Microsoft Update için daha yeniden dağıtılabilir bileşenleri seçin**|Bu bağlantıya tıkladıklarında, alan için [bileşenleri yeniden dağıtmak için önyükleyici paketleri](http://go.microsoft.com/fwlink/?LinkId=208835) güncelleştirmeleri denetlemek için Web sitesi.|
|**Bileşen satıcısının web sitesinden önkoşulları**|Önkoşul bileşenlerinin satıcısının Web sitesinden yüklenmesini belirtir. Varsayılan seçenek budur.|
|**Önkoşulları Uygulamamla aynı konumdan indir**|Önkoşul bileşenlerinin uygulamayla aynı konumda yüklenmesini belirtir. Bu, tüm önkoşul yayımlama konumuna kopyalar. Bu seçeneğin çalışması için önkoşul paketleri geliştirme bilgisayarında olmalıdır.|
|**Önkoşulları aşağıdaki konumdan indir**|Ön koşul bileşenleri seçtiğiniz konumdan yüklenmesi belirtir. Kullanabileceğiniz **Gözat** düğmesine tıklayarak bir konum seçin.|

## <a name="prerequisites-information"></a>Önkoşul bilgileri

Görünür önkoşul bileşenleri **Önkoşullar** iletişim kutusu aşağıdaki listede arasından farklı. Listelenen önkoşul **Önkoşullar iletişim kutusu** ilk kez iletişim kutusunu açtığınızda otomatik olarak ayarlanır. Projenin hedef çerçevesi daha sonra değiştirirseniz, yeni hedef Framework'ü el ile eşleşecek şekilde önkoşulları gerekecektir.

|Öğe|Açıklama|
|-------------|-----------------|
|**.NET Framework 3.5 SP1**|Bu paket aşağıdaki yükler:<br /><br /> -.NET framework sürüm 2.0, 3.0 ve 3.5.<br />-(X86) ve 64-bit (x64) 32-bit işletim sistemlerinde tüm .NET Framework sürümleri için destek.<br />-Dil paketleri paket ile yüklenen her bir .NET Framework sürümü için.<br />-Hizmet paketleri .NET Framework 2.0 ve 3.0 için.<br /><br /> .NET framework 3.0, Windows Vista ile eklenir ve .NET Framework 3.5 ile birlikte [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. 32-bit işletim sistemleri ve hedef Framework'ü kümesi için derlenmiş tüm Visual Basic ve C# projeleri için .NET framework 3.5 gereklidir **.NET Framework 3.5**ve 64 bit için derlenmiş Visual Basic ve C# projeleri işletim sistemleri. (IA64 desteklenmiyor.) Varsayılan olarak tüm CPU mimarisi için Visual Basic ve Visual C# projeleri derlenmiş unutmayın. Daha fazla bilgi için bkz: [Visual Studio çoklu sürüm desteğine genel bakış](../../ide/visual-studio-multi-targeting-overview.md) ve [64-bit uygulamalar için önkoşulları dağıtma](../../deployment/deploying-prerequisites-for-64-bit-applications.md).<br /><br /> Varsayılan olarak, bu öğe seçilir.|
|**Microsoft .NET Framework 4.x**|Bu paketi yükler .NET Framework 4.x x86 hem x64 platformlar için.|
|**SQL Server 2014 (x64 ve x86) için Microsoft System CLR Types**|Bu paket, x64 veya x86 için SQL Server 2014 için Microsoft System CLR Types yükler.|
|**SQL Server 2008 R2 Express**|Bu paket, Microsoft SQL Server 2008 R2 Express, Microsoft SQL Server 2008 R2, küçük bir web, sunucu veya Masaüstü uygulamaları için ideal bir veritabanı boş bir sürümünü yükler. Ücretsiz geliştirme ve üretim için kullanılabilir.|
|**SQL Server 2012 Express**|Bu paket, Microsoft SQL Server 2012 Express'i yükler.|
|**SQL Server 2012 Express LocalDB**|Bu paket Microsoft SQL Server 2012 Express LocalDB yükler.|
|**Visual C++ "14" çalışma zamanı kitaplıkları (ARM)**|Microsoft Windows işletim sistemi için programlama için yordamlar sağlayan Visual C++ çalışma zamanı kitaplıkları Itanium mimarisi için bu paketi yükler. Bu yordamlar C ve C++ dilleri tarafından sağlanmayan birçok genel programlama görevleri otomatik hale getirme.<br /><br /> Daha fazla bilgi için bkz: [C çalışma zamanı kitaplığı başvurusu](/cpp/c-runtime-library/c-run-time-library-reference).|
|**Visual C++ "14" çalışma zamanı kitaplıkları (x64)**|Bu paket Microsoft Windows işletim sistemi için programlama için yordamlar sağlar sistemleri işletim x64 için Visual C++ çalışma zamanı kitaplıkları yükler. Bu yordamlar C ve C++ dilleri tarafından sağlanmayan birçok genel programlama görevleri otomatik hale getirme.<br /><br /> Daha fazla bilgi için bkz: [C çalışma zamanı kitaplığı başvurusu](/cpp/c-runtime-library/c-run-time-library-reference).|
|**Visual C++ "14" çalışma zamanı kitaplıkları (x86)**|Bu paket Microsoft Windows işletim sistemi için programlama için yordamlar sağlar sistemleri işletim x86 için Visual C++ çalışma zamanı kitaplıkları yükler. Bu yordamlar C ve C++ dilleri tarafından sağlanmayan birçok genel programlama görevleri otomatik hale getirme.<br /><br /> Daha fazla bilgi için bkz: [C çalışma zamanı kitaplığı başvurusu](/cpp/c-runtime-library/c-run-time-library-reference).|

## <a name="see-also"></a>Ayrıca bkz.

- [Yayın Sayfası, Proje Tasarımcısı](../../ide/reference/publish-page-project-designer.md)
- [Uygulama Dağıtımının Önkoşulları](../../deployment/application-deployment-prerequisites.md)
- [64 bit Uygulamalar için Dağıtım Önkoşulları](../../deployment/deploying-prerequisites-for-64-bit-applications.md)
- [Visual Studio Çoklu Sürüm Desteğine Genel Bakış](../../ide/visual-studio-multi-targeting-overview.md)
