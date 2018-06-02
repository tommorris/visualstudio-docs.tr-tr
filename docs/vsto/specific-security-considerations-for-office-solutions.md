---
title: Office çözümleri için belirli güvenlik konuları
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- troubleshooting Office development in Visual Studio, security
- trusted code [Office development in Visual Studio]
- blocked code [Office development in Visual Studio]
- Outlook [Office development in Visual Studio], object model guard
- malicious code [Office development in Visual Studio]
- Outlook object model guard [Office development in Visual Studio]
- security [Office development in Visual Studio], troubleshooting
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 7da9446a4a5e4538164b09d1f11733f7bde3de24
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34693363"
---
# <a name="specific-security-considerations-for-office-solutions"></a>Office çözümleri için belirli güvenlik konuları
  Microsoft Office ve Microsoft .NET Framework tarafından sağlanan güvenlik özellikleri, Office çözümleri olası güvenlik tehditlerine karşı korumaya yardımcı olabilir. Bu konuda bu tehditlerinden bazıları aşağıda açıklanmıştır ve bunlara karşı korunmasına yardımcı olacak öneriler sunar. Ayrıca, Microsoft Office güvenlik ayarları Office çözümleri nasıl etkilediği hakkında bilgiler içerir.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
## <a name="trusted-code-is-repurposed-in-a-new-malicious-document"></a>Güvenilir kod yeni, kötü amaçlı bir belge amacı  
 Bir saldırgan, belirli bir amaç için örneğin, bir iş uygulaması için kişisel bilgileri yükleniyor tasarlanmıştır güvenilen kod alın ve çalışma gibi başka bir belgede onu yeniden kullanabilirsiniz. Kod özgün belgeye çalışmıyorsa ve kişisel bilgilerini elde etmek veya farklı bir kullanıcı tarafından açıldığında artan ayrıcalıklarla kodu çalıştırma gibi diğer tehditlere açmak bilmez. Alternatif olarak, kurbana gönderildiğinde, beklenmedik bir şekilde davranır sağlayacak şekilde, saldırganın yalnızca çalışma sayfasındaki verileri değiştirebilirsiniz. Değerleri, formülleri veya koduna bağlı çalışma sunu özelliklerini değiştirerek, kötü niyetli bir kullanıcı başka bir kullanıcı değiştirilmiş bir dosya göndererek saldırmak mümkündür. Ayrıca kullanıcılar çalışma sayfasındaki değerleri değiştirerek beklenir olmayan bilgilere erişmek için mümkün olabilir.  
  
 Derleme konumu ve belge konumu yürütmek için yeterli kanıt olmalıdır olduğundan, Bu saldırının bağlamak kolay değildir. Örneğin, belgeleri e-posta eklerindeki veya güvenilmeyen intranet sunucuları çalıştırmak için yeterli izinlere sahip değil.  
  
 Bu saldırıyı yapmak için kod koruyabilmeleri verilerine dayalı kararlar kolaylaştırır şekilde yazılmalıdır. Örnek bir veritabanı sunucusu adını içeren gizli bir hücreye sahip bir çalışma oluşturuyor. Kullanıcı çalışma sayfası SQL kimlik doğrulaması ve bir sabit kodlanmış SA parolası kullanarak bu sunucuya bağlanma girişiminde bir ASPX sayfasına gönderir. Bir saldırgan, gizli hücrenin içeriğini farklı bir bilgisayar adı ile değiştirin ve SA parolasını alabilir. İçin bu sorun, hiçbir sabit kodlu parolaları önlemek ve her zaman sunucu kimliklerini sunucu erişmeden önce iyi olduğu bilinen sunucuları iç listesine karşı denetleyin.  
  
### <a name="recommendations"></a>Önerileri  
  
-   Kullanıcı, belge, bir veritabanı, bir web hizmeti veya başka bir kaynaktan gelmediğini giriş ve verileri, her zaman doğrulayın.  
  
-   Kullanıcı adına ayrıcalıklı verileri almak ve korumasız bir çalışma sayfasına koyma gibi işlevselliği, belirli türde oluştururken dikkatli olun.  
  
-   Uygulama türüne bağlı olarak, bu belgenin özgün herhangi bir kod yürütmeden önce çalıştığını doğrulamak için mantıklı olabilir. Örneğin, bilinen ve güvenli bir konumda depolanan bir belgeden çalıştığından emin olun.  
  
-   Uygulamanız herhangi ayrıcalıklı Eylemler gerçekleştiriyorsa belge açıldığında bir uyarı görüntüleyecek şekilde iyi bir fikir olabilir. Örneğin, bir giriş ekranı veya uygulama kişisel bilgilere erişebilir ve kullanıcı devam etmek Seç sahip olduğunu belirten bir başlangıç iletişim kutusu oluşturabilirsiniz. Bir son kullanıcı zararsız görünen bir belgeden bu tür bir uyarı alırsa, isterse herhangi bir şey ele önce uygulamadan Çık mümkün olacaktır.  
  
## <a name="code-is-blocked-by-the-outlook-object-model-guard"></a>Kod Outlook nesne modeli Koruması tarafından engellendi  
 Microsoft Office, belirli özellikleri, yöntemleri ve nesneleri nesne modelinde kullanarak kod kısıtlayabilirsiniz. Bu nesnelere erişimi kısıtlayarak, Outlook e-posta solucanlar ve virüs zararlı amaçlar için nesne modeli kullanarak önlemeye yardımcı olur. Bu güvenlik özelliği Outlook nesne modeli koruması bilinir. Bir VSTO eklenti nesne modeli koruması etkinken kısıtlı özelliği veya yöntemi kullanmayı denerse, Outlook işlemi durdurmak kullanıcının sağlar ya da kullanıcının sınırlı bir süre için özellik veya yöntem erişim olanak tanıyan bir güvenlik uyarısı görüntüler. süre. Visual Studio'da Office çözümleri kullanılarak oluşturulan Outlook VSTO eklentileri, kullanıcı işlemi durdurursa, özel durum oluşturacak bir <xref:System.Runtime.InteropServices.COMException>.  
  
 Nesne modeli koruması VSTO eklentileri Outlook Microsoft Exchange Server ile kullanılıp bağlı olarak farklı şekillerde etkileyebilir:  
  
-   Outlook Exchange ile kullanılmıyorsa yönetici etkinleştirebilir veya tüm VSTO eklentileri bilgisayarda için nesne modeli koruması devre dışı bırakın.  
  
-   Outlook Exchange ile kullanılırsa, bir yönetici etkinleştirebilir veya tüm VSTO eklentileri bilgisayarda için nesne modeli koruması devre dışı bırakmak veya yönetici belirli VSTO eklentileri nesne modeli koruması karşılaşılmadan çalıştırabilirsiniz belirtebilirsiniz. Yöneticiler ayrıca nesne modelinin belirli alanlar için nesne modeli koruması davranışını değiştirebilirsiniz. Örneğin, Yöneticiler otomatik olarak nesne modeli koruması etkinleştirilmiş olsa dahi VSTO programlı olarak, e-posta göndermek eklentileri izin verebilir.  
  
 Outlook 2007'de başlayarak, Outlook güvenliğini sağlamanın Geliştirici ve kullanıcı deneyimini geliştirmek için nesne modeli koruması davranışını değiştirildi. Daha fazla bilgi için bkz: [kod Outlook 2007'deki güvenlik değişiklikleri](http://go.microsoft.com/fwlink/?LinkId=73429).  
  
### <a name="minimize-object-model-guard-warnings"></a>Nesne modeli koruyucusu uyarılarını simge durumuna küçült  
 Sınırlı özellikleri ve yöntemleri kullandığınızda güvenlik uyarılarını önlemek için VSTO eklentinizi Outlook nesnelerden aldığına emin olun `Application` alanını `ThisAddIn` projenizdeki sınıfı. Bu alan hakkında daha fazla bilgi için bkz: [Program VSTO eklentileri](../vsto/programming-vsto-add-ins.md).  
  
 Yalnızca bu nesneden elde edilen Outlook nesneleri tarafından nesne modeli koruması güvenebilir. Buna karşılık, elde edilen yeni bir nesneleri `Microsoft.Office.Interop.Outlook.Application` nesne güvenilir olmayan ve kısıtlı özellikleri ve yöntemleri nesne modeli koruması etkinse, güvenlik uyarıları verir.  
  
 Nesne modeli koruması etkinse, aşağıdaki kod örneğinde bir güvenlik uyarısı görüntüler. `To` Özelliği `Microsoft.Office.Interop.Outlook.MailItem` sınıfı tarafından nesne modeli koruması kısıtlanmış. `Microsoft.Office.Interop.Outlook.MailItem` Kodunu alır çünkü nesne güvenilmeyen bir `Microsoft.Office.Interop.Outlook.Application` kullanılarak oluşturulan **yeni** alanından elde yerine işleci `Application` alan.  
  
 [!code-csharp[Trin_VstcoreOutlookSecurity#1](../vsto/codesnippet/CSharp/Trin_VstcoreOutlookSecurity/ThisAddIn.cs#1)]
 [!code-vb[Trin_VstcoreOutlookSecurity#1](../vsto/codesnippet/VisualBasic/Trin_VstcoreOutlookSecurity/ThisAddIn.vb#1)]  
  
 Aşağıdaki kod örneğinde kısıtlanmış özelliğine kullanımı gösterilmiştir bir `Microsoft.Office.Interop.Outlook.MailItem` nesne modeli Koruması tarafından güvenilen bir nesne. Kodu güvenilir kullanan `Application` almak için alan `Microsoft.Office.Interop.Outlook.MailItem`.  
  
 [!code-csharp[Trin_VstcoreOutlookSecurity#2](../vsto/codesnippet/CSharp/Trin_VstcoreOutlookSecurity/ThisAddIn.cs#2)]
 [!code-vb[Trin_VstcoreOutlookSecurity#2](../vsto/codesnippet/VisualBasic/Trin_VstcoreOutlookSecurity/ThisAddIn.vb#2)]  
  
> [!NOTE]  
>  Outlook Exchange ile kullanılırsa, tüm Outlook nesnelerden alma `ThisAddIn.Application` VSTO eklentinizi tüm Outlook nesne modeline erişebilir olacağını garanti etmez. Bir Exchange Yöneticisi Outlook otomatik olarak ayarlar, Outlook Kime özelliğine erişmek önceki kod örneğinde vermez, bu kod örneği kullanıyor olsa bile, tüm Outlook nesne modeli kullanarak adres bilgilerine erişme girişimleri reddedebileceğiniz Güvenilen `ThisAddIn.Application` alan.  
  
### <a name="specify-which-add-ins-to-trust-when-using-exchange"></a>Exchange kullanılırken güvenmek için hangi eklentileri belirtin  
 Outlook Exchange ile kullanıldığında, yöneticiler belirli VSTO eklentileri nesne modeli koruması karşılaşılmadan çalıştırabilirsiniz belirtebilirsiniz. Outlook VSTO Visual Studio'da Office çözümleri kullanılarak oluşturulan eklentileri tek tek güvenilir olamaz; Bunlar yalnızca grup olarak güvenilir olabilir.  
  
 Bir VSTO VSTO eklentisinin giriş noktası DLL üzerinde bir karma kod eklenti Outlook güvenir. Tüm Outlook VSTO hedefleyen eklentileri [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] aynı giriş noktası DLL'ine (*VSTOLoader.dll*). Bunun anlamı tüm VSTO hedefleyen eklenti yönetici güveniyorsa bu durumda [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] nesne modeli koruması sonra tüm diğer VSTO hedefleyen eklentileri karşılaşılmadan çalıştırmak için [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] de güvenli olur. Belirli VSTO nesne modeli koruması karşılaşılmadan çalıştırmak için eklentileri güvenen hakkında daha fazla bilgi için bkz: [Outlook kullandığı virüs önleme özellikleri yönetmek için bir yöntem belirtmek](http://go.microsoft.com/fwlink/?LinkId=128773).  
  
## <a name="permission-changes-do-not-take-effect-immediately"></a>İzin değişiklikleri hemen etkili olmaz  
 Yönetici bir belge veya derleme için izinleri ayarlarsa, kullanıcılar çıkın ve bu değişikliklerin uygulanabilmesi tüm Office uygulamalarını yeniden başlatmanız gerekir.  
  
 Microsoft Office uygulamalarını barındıran diğer uygulamalar da zorlanmasını yeni izinler engelleyebilir. Kullanıcılar, Office, barındırılan veya tek başına, güvenlik ilkeleri değiştirildiğinde kullanan tüm uygulamalar çıkın.  
  
## <a name="trust-center-settings-in-the-microsoft-office-system-do-not-affect-add-ins-or-document-level-customizations"></a>Microsoft Office System Center ayarları eklentileri veya belge düzeyi özelleştirmeleri etkilemez güven  
 Kullanıcıları engelleyebilir VSTO eklentileri yüklenmesini bir seçenek ayarlayarak **Güven Merkezi**. Ancak, VSTO eklentileri ve Visual Studio'da Office çözümleri kullanılarak oluşturulan belge düzeyi özelleştirmeleri bu güven ayarlarından etkilenmez.  
  
 Kullanıcı VSTO eklentileri yüklenmesini kullanarak engelliyorsa **Güven Merkezi**, VSTO eklentileri aşağıdaki türleri yüklenmez:  
  
-   Yönetilen ve yönetilmeyen COM VSTO eklentileri.  
  
-   Yönetilen ve yönetilmeyen belgeler.  
  
-   Yönetilen ve yönetilmeyen Otomasyon VSTO eklentileri.  
  
-   Yönetilen ve yönetilmeyen gerçek zamanlı veri bileşenleri.  
  
 Aşağıdaki yordamlar, kullanıcıların nasıl kullanabileceğinizi açıklar **Güven Merkezi** Microsoft yüklenmesini VSTO eklentileri kısıtlamak için [!INCLUDE[Office_15_short](../vsto/includes/office-15-short-md.md)] ve Microsoft Office 2010. Bu yordamları VSTO eklentileri veya Visual Studio'da Office geliştirme araçları kullanılarak oluşturulan özelleştirmeleri etkilemez.  
  
#### <a name="to-disable-vsto-add-ins-in-microsoft-office-2010-and-microsoft-includeoffice15shortvstoincludesoffice-15-short-mdmd-applications"></a>VSTO eklentileri Microsoft Office 2010 ve Microsoft devre dışı bırakmak için [!INCLUDE[Office_15_short](../vsto/includes/office-15-short-md.md)] uygulamalar  
  
1.  Seçin **dosya** sekmesi.  
  
2.  Seçin *ApplicationName* **seçenekleri** düğmesi.  
  
3.  Kategoriler bölmesinde seçin **Güven Merkezi**.  
  
4.  Ayrıntılar bölmesinde seçin **Güven Merkezi Ayarları**.  
  
5.  Kategoriler bölmesinde seçin **eklentileri**.  
  
6.  Ayrıntılar bölmesinde seçin **gerektiren uygulama güvenilir yayımcı tarafından imzalanmış eklentileri** veya **tüm uygulama eklentileri devre dışı**.  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Office çözümleri güvenli](../vsto/securing-office-solutions.md)  
  
  