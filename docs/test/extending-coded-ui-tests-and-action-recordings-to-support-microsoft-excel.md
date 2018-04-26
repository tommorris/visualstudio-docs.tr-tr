---
title: Kodlanmış Kullanıcı Arabirimi Testlerini ve Eylem Kayıtlarını Microsoft Excel'i Desteklemek için Genişletme
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 9a98481123e26a72a1553d01c29d8e7ee023faaa
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="extend-coded-ui-tests-and-action-recordings-to-support-microsoft-excel"></a>Kodlanmış UI testleri ve Eylem kayıtlarını Microsoft Excel'i desteklemek için genişletme

Kodlanmış UI testleri ve eylem kayıtları için test çerçevesi her kullanıcı arabirimini desteklemiyor. Test etmek istediğiniz belirli kullanıcı Arabirimi desteklemiyor olabilir. Örneğin, hemen kodlanmış bir UI testi veya için bir eylem kaydı oluşturamazsınız bir [!INCLUDE[ofprexcel](../test/includes/ofprexcel_md.md)] elektronik tablo. Ancak, belirli UI kodlanmış UI test çerçevesi genişletilebilirlik yararlanarak destekleyecek kodlanmış UI test çerçevesi kendi uzantınızı oluşturabilirsiniz. Kodlanmış UI testleri ve eylem kayıtları için oluşturulmasını desteklemek için framework genişletmek nasıl bir örneği aşağıdaki konuda verir [!INCLUDE[ofprexcel](../test/includes/ofprexcel_md.md)]. Desteklenen platformlar hakkında daha fazla bilgi için bkz: [kodlanmış UI testleri ve eylem kayıtları için desteklenen yapılandırmalar ve platformlar](../test/supported-configurations-and-platforms-for-coded-ui-tests-and-action-recordings.md).

Bu bölümde, kaydedebilir ve Excel çalışma testleri kayıttan kodlanmış bir UI testi uzantısı gösterir. Uzantı her bölümü, bu bölümde ve kod açıklamaları yalnızca böyle bir uzantı oluşturmak isteyen geliştiriciler için açıklanmıştır.

![UI testi mimarisi](../test/media/ui_testarch.png)

## <a name="download-the-sample"></a>Örnek indirme

Dört projelerinde örnek oluşan `CodedUIExtensibilitySample.sln` çözüm:

-   CodedUIExtensibilitySample

-   ExcelCodedUIAddinHelper

-   ExcelUICommunicationHelper

-   SampleTestProject

Bu örnek alma [blog gönderisi](https://blogs.msdn.microsoft.com/gautamg/2010/01/05/3-introducing-sample-excel-extension/).

> [!NOTE]
> Örnek Microsoft Excel 2010 ile kullanılmak üzere tasarlanmıştır. Örnek Microsoft Excel diğer sürümleri de çalışabilir, ancak şu anda desteklenmiyor.

## <a name="details-about-the-sample"></a>Örnek Ayrıntıları

Aşağıdaki bölümler örnek ve yapısı hakkında bilgi sağlar.

### <a name="microsoft-excel-add-in-excelcodeduiaddinhelper"></a>Microsoft Excel Eklentisi: ExcelCodedUIAddinHelper
 Bu proje Excel işleminde çalışan bir eklenti içerir. Bkz: [kodlanmış UI testi için örnek Excel eklentisi](../test/sample-excel-add-in-for-coded-ui-testing.md) eklenti projesi kısa bir genel bakış için.

 Daha fazla bilgi için bkz: [izlenecek yol: Excel için oluşturma bilgisayarınızı ilk VSTO eklenti](http://msdn.microsoft.com/Library/a855e2be-3ecf-4112-a7f5-ec0f7fad3b5f).

### <a name="excel-ui-communication-exceluicommunicationhelper"></a>Excel UI iletişimi: ExcelUIcommunicationHelper
 Bu proje içerir `IExcelUICommunication` arabirimi ve kodlanmış UI test çerçevesi ile Excel arasında veri iletmek için kullanılan bilgileri içerir. Daha fazla bilgi için bkz: [Excel Communicator arabirimi örnekleme](../test/sample-excel-communicator-interface.md).

### <a name="coded-ui-test-extension-codeduiexentsibilitysample"></a>Kodlanmış UI testi uzantısı: CodedUIExentsibilitySample
 Bu proje bir Excel çalışma testlerinde kullanılan özel sınıflar içerir. Bu sınıfların her biri için kod oldukça kendinden açıklamalıdır. Ancak, her özel bir sınıf kısa bir açıklamasını sağlar. Daha fazla bilgi için bkz: [örnek kodlanmış UI testi uzantısı Excel için](../test/sample-coded-ui-test-extension-for-excel.md).

### <a name="deploying-your-add-in-and-extension"></a>Eklenti ve uzantısı dağıtma
 Tüm projeleri ve nesneleri oluşturduktan sonra sağlanan çalıştırmak `CopyDrop.bat` dosyasını yönetici olarak. Bu dosyayı kopyalar `ExcelCodedUIAddinHelper` DLL ve PDB dosyalarını:

 "`%CommonProgramFiles(x86)%\Microsoft Shared\VSTT\<version number>\UITestExtensionPackages\*.*`", sürüm numarası 11.0, olabilir burada 12,0 vb. dayalı, Visual Studio sürümü.

 `ExcelUICommunicationHelper` DLL ve PDB dosyalarını kopyalanır `"%ProgramFiles(x86)%\Microsoft Visual Studio <version number>\Common7\IDE\PrivateAssemblies"`.

 Tam kopya yollarını ayarlamanız gerekebilir, ancak hiçbir ek yükleme gereklidir. 64-bit makine üzerinde çalıştırmak için 32-bit Visual Studio Enterprise komut istemi kullanın `CopyDrop.bat` dosya.

### <a name="testing-excel-with-the-sampletestproject"></a>SampleTestProject ile test etme

Değil, veya kendi test projesi oluşturun ve olabilirsiniz kendi test kaydetmek, Excel belirli bir sürümünü kullanan sağlanan test projesinde testi çalıştırabilirsiniz. Daha fazla bilgi için bkz: [kodlanmış UI testleri oluşturma](../test/use-ui-automation-to-test-your-code.md).

## <a name="see-also"></a>Ayrıca bkz.

- <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestPropertyProvider>
- <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyElement>
- <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter>
- <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITestExtensionPackage>
- [Kodunuzu Test Etmek için UI Otomasyonunu Kullanma](../test/use-ui-automation-to-test-your-code.md)
- [Kodlanmış UI Testleri için En İyi Yöntemler](../test/best-practices-for-coded-ui-tests.md)
- [Kodlanmış UI Testleri ve Eylem Kayıtları için Desteklenen Yapılandırmalar ve Platformlar](../test/supported-configurations-and-platforms-for-coded-ui-tests-and-action-recordings.md)