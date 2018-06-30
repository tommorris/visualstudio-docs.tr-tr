---
title: Önkoşullar İletişim Kutusu
ms.date: 06/29/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- Microsoft.VisualStudio.Publish.BaseProvider.Dialog.Bootstrapper
helpviewer_keywords:
- Prerequisites dialog box
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a1360b63eb1469efe4948f2859e28a567b00ad1a
ms.sourcegitcommit: d9e4ea95d0ea70827de281754067309a517205a1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37117270"
---
# <a name="prerequisites-dialog-box"></a>Önkoşullar iletişim kutusu

**Önkoşullar** iletişim kutusu, hangi önkoşul bileşenlerinin yüklü olduğu, nasıl yükleneceğini ve paketleri yüklü sıra belirtir.

![Visual Studio'da Önkoşullar iletişim kutusu](media/prerequisites-dialog-box.png)

İletişim kutusuna erişmek için bir proje düğümünde seçin **Çözüm Gezgini**ve ardından **proje** > **özellikleri**. Zaman **Proje Tasarımcısı** görünen seçin **Yayımla** sekmesini tıklatın ve ardından **Önkoşullar**. Kurulum projeleri için üzerinde **proje** menüsünde tıklatın **özellikleri**. Zaman **özellik sayfaları** iletişim kutusu görüntülenirse, tıklatın **Önkoşullar**.

## <a name="uielement-list"></a>UIElement listesi

|Öğe|Açıklama|
|-------------|-----------------|
|**Önkoşul bileşenlerini yüklemek için Kurulum programını oluşturun**|Uygulamanızın Kurulum programında önkoşul bileşenleri içerir (*Setup.exe*) böylece bunlar sırasıyla bağımlılık, uygulamanızın önce yüklenmesi. Varsayılan olarak, bu seçenek seçilidir. Seçilmezse, hiçbir *Setup.exe* oluşturulur.|
|**Yüklemek için hangi Önkoşullar seçin**|.NET Framework ve C++ çalışma zamanı kitaplıkları gibi bileşenleri yüklenip yüklenmeyeceğini belirtir.<br /><br />Örneğin, onay kutusunu seçerek yanına **SQL Server 2012 Express**, Kurulum programı bu bileşen hedef bilgisayar üzerinde yüklü olduğundan ve değilse yükleme olup olmadığını doğrulamalısınız belirtin.<br /><br />Önkoşul her paket hakkında ayrıntılı bilgi için bkz: [önkoşul bilgilerini](#prerequisites-information).|
|**Bileşen satıcısının web sitesinden önkoşulları**|Önkoşul bileşenlerinin satıcısının Web sitesinden yüklenmesini belirtir. Varsayılan seçenek budur.|
|**Önkoşulları Uygulamamla aynı konumdan indir**|Önkoşul bileşenlerinin uygulamayla aynı konumda yüklenmesini belirtir. Bu, tüm önkoşul yayımlama konumuna kopyalar. Bu seçeneğin çalışması için önkoşul paketleri geliştirme bilgisayarında olmalıdır.|
|**Önkoşulları aşağıdaki konumdan indir**|Önkoşul bileşenlerinin girdiğiniz konumdan yüklenmesini belirtir. Kullanabileceğiniz **Gözat** düğmesine tıklayarak bir konum seçin.|

## <a name="prerequisites-information"></a>Önkoşul bilgileri

Görünür önkoşul bileşenleri **Önkoşullar** iletişim kutusu aşağıdaki listede arasından farklı. Listelenen önkoşul **Önkoşullar iletişim kutusu** ilk kez iletişim kutusunu açtığınızda otomatik olarak ayarlanır. Projenin hedef çerçevesi daha sonra değiştirirseniz, yeni hedef Framework'ü el ile eşleşecek şekilde önkoşulları seçmeniz gerekir.

|Öğe|Açıklama|
|-------------|-----------------|
|**.NET framework 3.5 SP1**|Bu paket aşağıdaki yükler:<br /><br /> -.NET framework sürüm 2.0, 3.0 ve 3.5.<br />-(X86) ve 64-bit (x64) 32-bit işletim sistemlerinde tüm .NET Framework sürümleri için destek.<br />-Dil paketleri paket ile yüklenen her bir .NET Framework sürümü için.<br />-Hizmet paketleri .NET Framework 2.0 ve 3.0 için.<br /><br /> .NET framework 3.0 ile Windows Vista dahil edilir ve .NET Framework 3.5 ile Visual Studio yer alır. 32-bit işletim sistemleri ve hedef Framework'ü kümesi için derlenmiş tüm Visual Basic ve C# projeleri için .NET framework 3.5 gereklidir **.NET Framework 3.5**ve 64 bit için derlenmiş Visual Basic ve C# projeleri işletim sistemleri. (IA64 desteklenmiyor.) Varsayılan olarak tüm CPU mimarisi için Visual Basic ve Visual C# projeleri derlenmiş unutmayın. Daha fazla bilgi için bkz: [Visual Studio çoklu sürüm desteğine genel bakış](../../ide/visual-studio-multi-targeting-overview.md) ve [64-bit uygulamalar için önkoşulları dağıtmak](../../deployment/deploying-prerequisites-for-64-bit-applications.md).|
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