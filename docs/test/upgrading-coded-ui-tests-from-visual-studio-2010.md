---
title: "Kodlanmış UI testleri Visual Studio 2010'dan yükseltme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
ms.author: gewarren
manager: ghogen
ms.workload: multiple
author: gewarren
ms.openlocfilehash: 9e89ff364b0b10ee85be6fdd98d3e328f8c337ee
ms.sourcegitcommit: 7ae502c5767a34dc35e760ff02032f4902c7c02b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/09/2018
---
# <a name="upgrading-coded-ui-tests-from-visual-studio-2010"></a>Visual Studio 2010'dan Kodlanmış UI Testlerini Yükseltme
Test oluşturulmuş kodlanmış UI testleri içeren projeleri [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)] SP1 sessizce Visual Studio 2012 veya sonraki sürümlerde açıldığında onarıldı. Test projeleri kaynak denetimine işaretlenirse, proje dosyalarını bu onarım için teslim alınır. Onardıktan sonra bu test kodlanmış UI testleri can içeren projeleri sonra her ikisinde de kullanılması [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)] SP1 ve [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)].  
  
 **Gereksinimler**  
  
-   Visual Studio Enterprise  
  
> [!NOTE]
>  Visual Studio birden fazla test proje türü içerir. Yeni bir kodlanmış UI testi oluşturmak, bir kodlanmış UI test proje türü oluşturulur. Daha fazla bilgi için bkz: [Visual Studio'nun önceki sürümleri yükseltme testlerden](http://msdn.microsoft.com/en-us/e9c8b7f6-bd72-448e-8edb-d090dcc5cf52).  
  
> [!WARNING]
>  [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)]Kodlanmış UI testleri içeren test projeleri gerekir yeniden test projesinde açtığınızda [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)] veya [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)] yana birimi ile [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)].  
  
> [!WARNING]
>  Oluşturulan bir test projesi zaman [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)] ve yalnızca birim testleri içeren açılır [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)], kodlanmış UI testleri kendisine eklenemez. Benzer şekilde, oluşturulan birim testi projesi kodlanmış UI testi ekleyemezsiniz [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)].  
  
## <a name="compatibility-issues-between-visual-studio-2010-and-visual-studio-2012-or-later"></a>Visual Studio 2010 ve Visual Studio 2012 veya sonraki sürümünü arasındaki uyumluluk sorunları  
 Aşağıdaki tabloda zaman geçiş kodlanmış UI testleri arasında dikkate etmeniz gereken sorunları listeler [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)] ve [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)].  
  
> [!CAUTION]
>  Kodlanmış UI test projeleri Çözüm Gezgini'nde görünmeyen başvurularında ilgili bilinen bir sorun yoktur. Daha fazla bilgi için üzerinde bulunan Benioku dosyasına bakın [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)] yükleme medyası.  
  
|Kodlanmış UI işlevi|Sorun|Çözüm|  
|----------------------------|-----------|--------------|  
|Silverlight UI testi desteklenmiyor[!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)]|**Yapı başarısız olur**<br /><br /> Varsa [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)] özellik Pack 2 ve sahip kodlanmış UI testi projelerini Silverlight uygulamaları için oluşturulan, bu projeleri de açılamaz [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)].|Bu projelerde yönetmek öneririz [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)] yalnızca Feature Pack 2.|  
|Firefox UI testi desteklenmiyor[!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)]|**Yapı başarılı olur, test çalışması başarısız olur**<br /><br /> Varsa [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)] özellik Pack 2 ve sahip Firefox web uygulamaları için kodlanmış UI testi projelerini oluşturulan, bu projeleri de açılamaz [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)].|Bu projelerde yönetmek öneririz [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)] yalnızca Feature Pack 2.|  
|Yeni kullanıcı Arabirimi kodu test API'ler eklenmiştir[!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)]|**Yapı başarısız olur**<br /><br /> Kodlanmış UI testleri Yeni UI testi API'si kullanma oluşturursanız [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)], bu projeleri de açılamaz [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)].|Yeni API kullanarak projeleri içinde yönetilebilir [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)] yalnızca.|  
|İçinde [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)], başvuruları csproj dosyasındaki 'Seç' deyimi içinde eklendi. İçinde [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)], bir geri bildirim hedefleri dosya kodlanmış UI Test derleme başvuruları dahil etmek için kullanıyoruz.|İçinde [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)], oluşturduğunuz Test projesi için kodlanmış UI testi eklenemez [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)] (veya SP1) kodlanmış bir UI testi içermiyordu.<br /><br /> Onarım işlemini hedefleri dosyasını ve Seç deyimi ekler. Kodlanmış UI testi Test projesinde değil sonra projeyi onarıldı olarak işaretlenir ve uygun başvuruları eklenmez, kodlanmış UI testi eklerken [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)].|Kullanarak aynı çözüm içinde yeni bir Test projesi oluşturmak zorunda kalırsınız [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)] ve yeni kodlanmış UI testi ekleyin. Alternatif olarak, Test projesinde içine kodlanmış UI testleri ekleyebilmeniz için [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)] SP1 ve açık, proje içinde [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)].|  
  
##  <a name="UpgradingCodedUIFromVS2010_Update"></a>Visual Studio 2010 SP1 Güncelleştirmesi  
 Bir güncelleştirme [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)] adresten uyumluluk destek veya sonraki sürümü için Visual Studio 2012 SP1 ve Windows 8 veya üzeri, kullanılabilir [Microsoft Download Center](http://www.microsoft.com/download/details.aspx?id=34677) ve ayrıca bir Visual Studio olarak güncelleştirin.  
  
 Aşağıdaki güncelleştirme uygulandıktan sonra [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)] kodlanmış UI test aracı özellikleri Windows 8 için geliştirilmiş SP1:  
  
-   Windows 8 çalıştıran bir bilgisayarda Microsoft .NET Framework 4.5 tabanlı Windows Presentation Foundation (WPF) denetimleri için kodlanmış UI testini çalıştırabilirsiniz.  
  
-   Kodlanmış UI testi 64-bit (x 64) Internet Explorer 10 için Windows 8 çalıştıran bir bilgisayarda çalıştırabilirsiniz.  
  
 Güncelleştirme ayrıca aşağıdaki sorunlar için düzeltmeler içerir:  
  
-   **Kod kapsamı:** Visual Studio 2012'de tarafından oluşturulan bir kod kapsamı dosyasını (.coverage) açmak için bağlanamama [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)] SP1.  
  
-   **Stranded test yapılarını:** ekibinizin geçersiz bir kullanıcı Team Foundation Server (TFS) 2010 için atanan bir test yapıya sahip. Örneğin, bir kullanıcı şirket ayrıldı, ancak hala kendisine atanmış bir test çalışması içeriyor. TFS 2010 için TFS 2012 yükseltin. Kullandığınız [!INCLUDE[TCMext](../misc/includes/tcmext_md.md)] yükseltilmiş TFS sunucusuna bağlanmak için 2010. Test yapı kullanarak TFS kullanıcılara atamak mümkün olmayan [!INCLUDE[TCMext](../misc/includes/tcmext_md.md)] 2010.  
  
-   **Yük testleri:** bir bilgisayarda yerel ağ (LAN) profili dışındaki bir ağ türü ile birlikte bir yük testi çalıştırdığınızda bu Windows 8 çalıştıran, ağ öykünücüsü sürücüsü işletim sisteminizin çökmesine neden olur. Daha fazla ayrıntı için bkz: [KB makalesi 2736182](http://support.microsoft.com/kb/2736182).  
  
## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio Projelerini Taşıma, Geçirme ve Yükseltme](../porting/port-migrate-and-upgrade-visual-studio-projects.md)  
[Testleri Visual Studio'nun önceki sürümlerinden yükseltme](http://msdn.microsoft.com/en-us/e9c8b7f6-bd72-448e-8edb-d090dcc5cf52)  
[Kodunuzu Test Etmek için UI Otomasyonunu Kullanma](../test/use-ui-automation-to-test-your-code.md)  
[Kodlanmış UI Testleri ve Eylem Kayıtları için Desteklenen Yapılandırmalar ve Platformlar](../test/supported-configurations-and-platforms-for-coded-ui-tests-and-action-recordings.md)
