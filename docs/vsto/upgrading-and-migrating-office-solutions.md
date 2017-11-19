---
title: "Yükseltme ve Office çözümleri geçirme | Microsoft Docs"
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
- Office applications [Office development in Visual Studio], upgrading
- Office projects [Office development in Visual Studio], upgrading
- upgrading applications [Office development in Visual Studio]
- upgrading Office solutions in Visual Studio
- migrating Office solutions in Visual Studio
ms.assetid: cc60cdcb-593d-498a-8358-f1f3ac673fe1
caps.latest.revision: "105"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 8189032a38aba69b63cb96f824c973b0d41a1aad
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="upgrading-and-migrating-office-solutions"></a>Office Çözümlerini Yükseltme ve Geçirme
  Visual Studio daha önceki bir sürümünde oluşturulmuş bir Microsoft Office project varsa, geçerli Visual Studio sürümlerinde kullanmak için proje yükseltmeniz gerekir. Microsoft Office project yükseltmek için Microsoft Office geliştirici araçlarını içeren Visual Studio sürümünde açın. Microsoft Office geliştirici araçlarını içeren Visual Studio sürümleri hakkında daha fazla bilgi için bkz: [Office çözümleri geliştirmek için bilgisayarı yapılandırma](../vsto/configuring-a-computer-to-develop-office-solutions.md).  
  
> [!NOTE]  
>  Office deneyimi boyunca genişletmek çözümleri geliştirirken ilgileniyor [birden çok platform](https://dev.office.com/add-in-availability)? Yeni [Office eklentileri modeli](https://dev.office.com/docs/add-ins/overview/office-add-ins). VSTO eklentilerini ve çözümlerle karşılaştırıldığında küçük bir yer Office eklentileri sahip ve teknoloji, HTML5, JavaScript, CSS3 ve XML gibi programlama neredeyse her web kullanarak oluşturabilirsiniz.  
  
> [!NOTE]  
>  Visual Studio, Visual Studio'nun önceki sürümleri kullanılarak oluşturulan InfoPath form şablon projelerini yükseltme yapamazsınız. Bu proje türleri, Visual Studio'nun geçerli sürümde desteklenmez.  
  
## <a name="changes-to-upgraded-projects"></a>Yükseltilen Projelerdeki değişiklikler  
 Microsoft Office project yükselttiğinizde, aşağıdaki öğeleri hedeflemek için projeyi Visual Studio değiştirir:  
  
-   Office çalışma zamanı için Visual Studio 2010 Araçları. Daha fazla bilgi için bkz: [Office çalışma zamanı genel bakış için Visual Studio Araçları](../vsto/visual-studio-tools-for-office-runtime-overview.md).  
  
-   Geçerli derleme başvuruları.  
  
-   (Visual Studio 2013 için yalnızca yükseltme sırasında) proje türü tarafından desteklenen .NET Framework sürümü.  
  
-   Microsoft Office (Visual Studio 2013 için yalnızca yükseltme sırasında) proje türü tarafından desteklenen bir sürümü.  
  
## <a name="assembly-references"></a>Derleme başvuruları  
 Visual Studio Proje aşağıdaki derleme başvurularını yükseltir:  
  
-   Microsoft Office birincil birlikte çalışma derlemeleri (PIA).  
  
-   Derlemelerde [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]. Bu derlemeler hakkında daha fazla bilgi için bkz: [Office çalışma zamanı genel bakış için Visual Studio Araçları](../vsto/visual-studio-tools-for-office-runtime-overview.md).  
  
-   Yeni veya güncelleştirilmiş bağımlı derlemeleri sürümleri.  
  
## <a name="targeted-net-framework"></a>Hedeflenen .NET Framework  
 Bir projesini Visual Studio 2013'e yükselttiğinizde, Visual Studio ya da hedeflemek için projeyi değiştirir [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)] veya [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)]. Projenin hedeflediği .NET framework sürümünü Office hangi sürümünün bilgisayarınızda yüklü bağlıdır. Varsa [!INCLUDE[Office_15_short](../vsto/includes/office-15-short-md.md)] olan yüklüyse, Visual Studio hedeflemek için projeyi değiştirir [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)]. Aksi takdirde, Visual Studio hedeflemek için projeyi değiştirir [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)].  
  
> [!NOTE]  
>  Geliştirme ve son kullanıcı bilgisayarlarında güncellendiyse bir çözümü çalıştırmak için bazı ek adımlar gerçekleştirmeniz gerekebilir ve bazı özellikleri kullanıyorsa, projenizin artık derleyin. Daha fazla bilgi için bkz: [geçirme Office çözümlerini .NET Framework 4 veya sonraki bir sürüme](../vsto/migrating-office-solutions-to-the-dotnet-framework-4-or-later.md).  
  
 Hedefliyorsanız [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] veya daha sonra Office projesinde, .NET Framework 3.5 hedeflediğinizde, kullanılabilir olmayan bazı özellikleri kullanabilirsiniz. Daha fazla bilgi için bkz: [tasarlama ve oluşturma Office çözümleri](../vsto/designing-and-creating-office-solutions.md).  
  
## <a name="targeted-office-application"></a>Hedeflenen Office uygulaması  
 Bir Office projesini Visual Studio 2013'e yükselttiğinizde, Visual Studio Proje türü, bir belge düzeyi özelleştirme veya VSTO eklenti projesi gibi tarafından desteklenen Microsoft Office sürümü hedeflemek için projeyi değiştirir.  
  
 Office projelerinde Visual Studio 2013 hedef [!INCLUDE[Office_15_short](../vsto/includes/office-15-short-md.md)] ve [!INCLUDE[office14_long](../vsto/includes/office14-long-md.md)] uygulamalar. Visual Studio yüklediğiniz office en son sürümünü hedeflemek için projeyi değiştirir. Office'in bu sürümleri hiçbiri yüklüyse, Visual Studio Proje yükseltmez.  
  
> [!NOTE]  
>  Hedefe VSTO eklenti projesindeki yükseltirseniz [!INCLUDE[Office_15_short](../vsto/includes/office-15-short-md.md)] veya sonrası olduğundan emin olun `ThisAddIn_Startup` olay işleyicisi VSTO eklentisinin uygulama belgeye erişen kodu içermiyor. Daha fazla bilgi için bkz: [bir belgeyi Office uygulama başlatılır erişme](../vsto/programming-vsto-add-ins.md#AccessingDocuments).  
  
 Belge düzeyi özelleştirmeleri için [!INCLUDE[vs_current_short](../sharepoint/includes/vs-current-short-md.md)] .xls veya .doc uzantısı, Office Açık XML biçimine belgeler gibi bir ikili biçimine sahip belgelerin projesinde dönüştürür. Open XML hakkında daha fazla bilgi için bkz: [yeni dosya adı uzantılarını ve açık XML Biçimleri giriş](https://support.office.com/en-nz/article/Introduction-to-new-file-name-extensions-eca81dcb-5626-4e5b-8362-524d13ae4ec1).  
  
> [!NOTE]  
>  Akıllı etiketler Excel 2010 ve Word 2010, kullanım dışı bırakılmıştır. Çözümünüzü akıllı etiketler kullanıyorsa, test ve Visual Studio 2013 veya Visual Studio 2015 hata ayıklama önce bu nedenle, bunları kaldırmanız gerekir.  
  
## <a name="upgrading-microsoft-office-2003-projects"></a>Microsoft Office 2003 projelerini yükseltme  
 Belge düzeyi özelleştirmeleri ve Microsoft Office 2003 hedef VSTO Add-ins yükseltme için ek bazı noktalar vardır.  
  
### <a name="document-level-projects"></a>Belge düzeyi projelerine  
 Proje belgede Windows Forms denetimleri içeriyorsa, ayrıca Office ikinci sürümü proje yükseltmeden önce çalışma zamanı için Visual Studio 2005 Araçları sahip olmalıdır. Proje yükseltmeden önce bu sürüm çalışma zamanının geliştirme bilgisayarınızda yüklü değilse, yükseltilen proje derleme içeren veya çalıştırma zamanı hataları olabilir. Proje yükseltme işlemini tamamladıktan sonra diğer Office çözümleri tarafından kullanılmadığından, Visual Studio 2005 araçları Office ikinci Edition çalışma zamanı için geliştirme bilgisayardan kaldırabilirsiniz. Bu sürüm çalışma zamanının Microsoft Download Center yeniden dağıtılabilir paket olarak kullanılabilir [için Microsoft Visual Studio 2005 araçları Office ikinci Edition çalışma zamanı (VSTO 2005 SE) (x86)](http://go.microsoft.com/fwlink/?linkid=49612).  
  
### <a name="vsto-add-in-projects"></a>VSTO eklentisi projelerine  
 VSTO eklentilerini yüklemek için yapılandırılmış bir kurulum veya InstallShield Limited Edition proje özgün projeniz için çözüm dosyasını dahil, Visual Studio Proje yükseltir, ancak başka değişiklikler projeye yapmaz. Bir Windows Installer dosyası VSTO eklentinizi dağıtmak için kullanmaya devam etmek istiyorsanız, aşağıdaki gibi yeni önkoşulları yüklemek için Kurulum veya InstallShield Limited Edition projesini değiştirmelisiniz [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)], Visual Studio 2010 Araçları Office çalışma zamanı için ve isteğe bağlı VSTO eklentinizi tarafından başvurulan birincil birlikte çalışma derlemeleri. Daha fazla bilgi için bkz: [tarafından Windows Installer kullanarak Office çözümü dağıtma](../vsto/deploying-an-office-solution-by-using-windows-installer.md).  
  
 VSTO eklentinizi dağıtmak için ClickOnce kullanmak istiyorsanız, Kurulum veya InstallShield Limited Edition projesini tamamen silebilirsiniz. VSTO eklentileri ClickOnce kullanarak dağıtma hakkında daha fazla bilgi için bkz: [Office çözümü dağıtma](../vsto/deploying-an-office-solution.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: Office çözümlerini yükseltme](http://msdn.microsoft.com/en-us/a269e539-b717-4680-a568-2152b070347e)   
 [Office çözümlerini geçirme .NET Framework 4 veya üstü](../vsto/migrating-office-solutions-to-the-dotnet-framework-4-or-later.md)   
 [Proje yükseltme, Seçenekler iletişim kutusu](../vsto/project-upgrade-options-dialog-box.md)  
  
  