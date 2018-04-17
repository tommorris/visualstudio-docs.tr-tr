---
title: Yayımlama Sihirbazı (Visual Studio'da Office Geliştirme) | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
f1_keywords:
- VST.ProjectProperties.PublishWizard
- VST.PublishWizard.Publish.2007System
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- ClickOnce deployment [Office development in Visual Studio], Publish Wizard
- deploying applications [Office development in Visual Studio], Publish Wizard
- Office applications [Office development in Visual Studio], Publish Wizard
- Publish Wizard, Office solutions
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 67e3222c6f1deeca58b84aca4ba73d2826483b26
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="publish-wizard-office-development-in-visual-studio"></a>Yayımlama Sihirbazı (Visual Studio'da Office Geliştirme)
  Kullanım **Yayımlama Sihirbazı** belirtilen bir konuma çözüm dosyalarını kopyalamak için bildirim dosyalarını oluşturmak ve Kurulum programını oluşturun.  
  
 Bu Sihirbazı'na erişmek için **yapı** menüsünde seçin **Yayımla** *SolutionName*. Aynı zamanda erişebilirsiniz **Yayımlama Sihirbazı** gelen **Çözüm Gezgini**. Proje düğümünün kısayol menüsünü açın ve ardından **Yayımla**.  
  
 Her bölüm Sihirbazı'nın sayfasında açıklar.  
  
## <a name="where-do-you-want-to-publish-the-application"></a>Burada uygulamayı yayımlamak istiyor musunuz?  
 **Bu uygulamayı yayımlamak için konum belirtin**  
 Gerekli. Yayımlama konumu dizindir nerede **Yayımlama Sihirbazı** derlemeden bildirimleri, derlemeleri, geçici bir sertifika ve diğer dosyaları gibi çözüm dosyalarını kopyalar. Bu dizine yazma erişimi olmalıdır.  
  
 Disk yolu, dosya paylaşımı, FTP sitesi veya web sitesi URL'si konumunu yazın veya tıklatın **Gözat** konumuna gözatmak için düğmeyi. Yol aşağıdaki biçimlerde olabilir:  
  
-   C:\Deploy\MyApplication veya \MyApplication gibi standart Windows biçiminde göreli veya mutlak bir yol.  
  
-   Bir Evrensel Adlandırma Kuralı (UNC) yolu gibi \\\ServerName\MyApplication\\.  
  
-   Bir URL bir Web sitesi, gibi http://www.microsoft.com/MyApplication.  
  
 Varsayılan olarak, yayımlama konumdur *http://localhost/projectname/* IIS yüklü veya bunu yaparsanız publish\ dizin IIS yüklü.  
  
> [!NOTE]  
>  Hedef bilgisayarın Windows Vista çalıştırıyorsa, daha fazla noktalar vardır. Yerel yayımlama seçeneğini kullanmak için Windows Vista bilgisayarda yönetici olması gerekir. Ayrıca, her zaman varsayılan konumu: *yayımlama\\*  IIS yüklü olup olmadığını bağımsız olarak dizin.  
  
## <a name="what-is-the-default-installation-path-on-end-user-computers"></a>Son kullanıcı bilgisayarlarında varsayılan yükleme yolu nedir?  
 Yükleme yolu isteğe bağlıdır. İsterseniz, yükleme yolu daha sonra ayarlayabilirsiniz. Ayrıntılar için bkz [nasıl yapılır: Office çözümü yükleme konumunu değiştirmek](http://msdn.microsoft.com/en-us/d0eaa07b-2d72-4902-899f-2f9fb165b8fd).  
  
 Yükleme yolu, son kullanıcının ondan özelleştirmeyi yüklediği dizindir. Bu da çözümü güncelleştirmeleri denetlemek için kullanacağı yoludur. **Yayımlama Sihirbazı** aynı Girdiğiniz yol olmadığı sürece çözümü bu konuma dağıtmaz **bu uygulamayı yayımlamak için konum belirtin** önceki sayfada kutusu.  
  
 **Bir Web sitesinden**  
 Son kullanıcılar çözümü yüklemek için izleyeceği URL'sini belirtin.  
  
 **Bir UNC yolu veya dosya paylaşımından**  
 Son kullanıcılar çözümü yüklemek için izleyeceği UNC yolunu belirtin.  
  
 **Bir CD-ROM veya DVD-ROM'UNDAN**  
 Bu seçenek, bir yükleme yolu gerektirmez.  
  
 Visual Studio, CD veya DVD yazma değil. Çıktı bir CD veya DVD elle kopyalamanız gerekir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ClickOnce kullanarak Office çözümü dağıtma](../vsto/deploying-an-office-solution-by-using-clickonce.md)   
 [Yayımla Sayfası, Proje Tasarımcısı &#40;Visual Studio'da Office geliştirme&#41;](../vsto/publish-page-project-designer-office-development-in-visual-studio.md)   
 [Office Çözümünü Dağıtma](../vsto/deploying-an-office-solution.md)  
  
  