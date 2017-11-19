---
title: "ClickOnce uygulamalarında yerel ve uzak veri erişimi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, data
- data access, ClickOnce applications
ms.assetid: be5cbe12-6cb6-49c9-aa59-a1624e1eef3d
caps.latest.revision: "21"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.openlocfilehash: 5474a2101a96576d7043c10cc3fd35fad3756653
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="accessing-local-and-remote-data-in-clickonce-applications"></a>ClickOnce Uygulamalarında Yerel ve Uzak Veri Erişimi
Uygulamaların çoğu veri üretir veya tüketir. [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]Okuma ve yerel olarak ve uzaktan veri yazma için çeşitli seçenekler sağlar.  
  
## <a name="local-data"></a>Yerel veriler  
 İle [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)], aşağıdaki yöntemlerden birini kullanarak yerel olarak veri depolamak ve yükleyin:  
  
-   [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]Veri dizini  
  
-   Yalıtılmış Depolama  
  
-   Diğer yerel dosyalar  
  
### <a name="clickonce-data-directory"></a>ClickOnce veri dizini  
 Her [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] yerel bir bilgisayarda yüklü uygulama kullanıcının belgeler ve ayarlar klasöründe depolanan bir veri dizinine sahiptir. Dahil herhangi bir dosyayı bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama ve bir uygulama yüklendiğinde "data" dosyası bu dizine kopyalanır olarak işaretli. Veri dosyaları, en sık kullanılan herhangi bir dosya türü olabilir metin, XML ve Microsoft Access .mdb dosyaları gibi veritabanı dosyaları.  
  
 Veri dizini uygulama açıkça depolayan ve tutar veri uygulama tarafından yönetilen verileri için tasarlanmıştır. Tüm statik uygulama bildiriminde "data" olarak işaretlenmemiş (nondependency) dosyalar yerine uygulama dizininde bulunur. Bu dizin, uygulamanızın yürütülebilir dosyanın (.exe) dosyaları ve derlemeler bulunduğu ' dir.  
  
> [!NOTE]
>  Zaman bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama kaldırıldığında, kendi veri dizini de kaldırılır. Hiç veri dizini belgeler gibi uç-kullanıcıya yönetilen veri depolamak için kullanın.  
  
#### <a name="marking-data-files-in-a-clickonce-distribution"></a>ClickOnce dağıtım veri dosyalarında işaretleme  
 Veri dizini içine varolan bir dosyayı koymak için var olan dosyayı bir veri dosyası olarak işaretlemelisiniz, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulamanın uygulama bildirim dosyasının. Daha fazla bilgi için bkz: [nasıl yapılır: ClickOnce uygulamasına bir veri dosyası dahil](../deployment/how-to-include-a-data-file-in-a-clickonce-application.md).  
  
#### <a name="reading-from-and-writing-to-the-data-directory"></a>Okuma ve veri dizinine yazma  
 Veri Dizininden okuma gerektirir, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama isteği okuma izni; benzer şekilde, dizine yazma izni gerektirir. Tam güven ile çalışacak şekilde yapılandırdıysanız, uygulamanızı otomatik olarak bu izne sahiptir. İzin yükseltme veya güvenilir uygulama dağıtımı'nı kullanarak, uygulamanız için yükseltme yaptığınıza izinleri hakkında daha fazla bilgi için bkz: [ClickOnce uygulamalarının güvenliğini sağlama](../deployment/securing-clickonce-applications.md).  
  
> [!NOTE]
>  Kuruluşunuz güvenilir uygulama dağıtımı kullanmaz ve izin yükseltmeyi devre dışı, izinleri sunduğundan başarısız olur.  
  
 Uygulamanız bu izinlere sahip olduktan sonra veri dizini içinde sınıfların yöntemi çağrılarını kullanarak erişebildiğinizi <xref:System.IO>. Windows Forms içinde veri dizinin yolunu elde edebilirsiniz [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] kullanarak uygulama <xref:System.Deployment.Application.ApplicationDeployment.DataDirectory%2A> tanımlanan özelliği <xref:System.Deployment.Application.ApplicationDeployment.CurrentDeployment%2A> özelliği <xref:System.Deployment.Application.ApplicationDeployment>. Bu, veri erişim için en kullanışlı ve önerilen yoludur. Aşağıdaki kod örneği, dağıtımınızda bir veri dosyası olarak dahil alan ve csv.txt olarak adlandırılan bir metin dosyası için bunu gösterilmiştir.  
  
 [!code-csharp[ClickOnce.OpenDataFile#1](../deployment/codesnippet/CSharp/accessing-local-and-remote-data-in-clickonce-applications_1.cs)]
 [!code-vb[ClickOnce.OpenDataFile#1](../deployment/codesnippet/VisualBasic/accessing-local-and-remote-data-in-clickonce-applications_1.vb)]  
  
 Veri dosyası olarak dağıtımınızda dosyaları işaretleme daha fazla bilgi için bkz: [nasıl yapılır: ClickOnce uygulamasına bir veri dosyası dahil](../deployment/how-to-include-a-data-file-in-a-clickonce-application.md).  
  
 İlgili değişkenleri kullanarak veri dizini yolunu elde edebilirsiniz <xref:System.Windows.Forms.Application> gibi sınıfı <xref:System.Windows.Forms.Application.LocalUserAppDataPath%2A>.  
  
 Diğer dosya türleri düzenleme ek izinler gerektirebilir. Bir Access veritabanı (.mdb) dosyası kullanmak istiyorsanız, örneğin, uygulamanızın tam güven ilgili kullanmak için onay gerekir <xref:System.Data> sınıfları.  
  
#### <a name="data-directory-and-application-versions"></a>Veri dizini ve uygulama sürümleri  
 Her bir uygulamanın sürümü diğer sürümlerden ayrılmış kendi veri dizini vardır. [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]uygulamanın çalışma zamanında yeni veri dosyaları oluşturmak için bir konum sahip olması mı veri dosyalarının dağıtımdaki bağımsız olarak bu dizini oluşturur. Bir uygulamanın yeni bir sürümü yüklü olduğunda [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] tüm dosyalar önceki sürümün Veri Dizininden yeni sürümün veri dizinine kopyalayın — tarafından oluşturulan veya özgün dağıtımında uygulama.  
  
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]bir veri dosyası, farklı bir karma değeri uygulamanın yeni sürümü eski sürümü varsa dosyanın eski sürümünü sunucunun daha yeni sürümü ile değiştirir. Ayrıca, yeni oluşturulan uygulamanın önceki sürümü dosya varsa aynı ada sahip yeni sürümün dağıtımdaki bir dosya olarak [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] ile yeni dosyayı eski sürümün dosyasının üzerine yazar. Her iki durumda da, eski dosyaları bir dizini içinde alt adlı veri eklenecektir `.pre`, böylece uygulama geçiş amacıyla eski verileri erişmeye devam edebilirsiniz.  
  
 Veri geçişi geçirmiş gerekiyorsa, kullanabileceğiniz [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] dağıtım eski veri dizininden yeni veri dizinine özel taşıma gerçekleştirmek için API. Kullanarak mevcut bir yüklemeyi test gerekecek <xref:System.Deployment.Application.ApplicationDeployment.IsFirstRun%2A>, update kullanarak karşıdan <xref:System.Deployment.Application.ApplicationDeployment.Update%2A> veya <xref:System.Deployment.Application.ApplicationDeployment.UpdateAsync%2A>, ve herhangi bir özel veri geçişi iş güncelleştirmeden sonra kendi tamamlandı.  
  
### <a name="isolated-storage"></a>Yalıtılmış Depolama  
 Yalıtılmış Depolama oluşturmak ve basit bir API kullanarak dosyalara erişen bir API sağlar. Depolanan dosyaların gerçek konumunu Geliştirici hem kullanıcı gizlenir.  
  
 Yalıtılmış Depolama works tüm sürümlerinde [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]. Yalıtılmış Depolama ek izin verir gerek kalmadan kısmen güvenilir uygulamalar içinde de çalışır. Yalıtılmış Depolama uygulamanızı kısmi güvende çalıştırmanız gerekir, ancak uygulamaya özgü verileri korumalıdır kullanmalısınız.  
  
 Daha fazla bilgi için bkz: [yalıtılmış depolama](/dotnet/standard/io/isolated-storage).  
  
### <a name="other-local-files"></a>Diğer yerel dosyalar  
 Uygulamanızı veya bunları raporları, görüntüler, müzik vb. gibi son kullanıcı verilerini kaydetmesi gerekir çalışıyorsanız, uygulamanızı gerektirir <xref:System.Security.Permissions.FileIOPermission> okuyup veri yerel dosya sistemine yazma.  
  
## <a name="remote-data"></a>Uzak Veriler  
 Belirli bir noktada, uygulamanızın olasılıkla müşteri verileri veya pazar bilgileri gibi uzak bir Web sitesinden bilgi almak vardır. Bu bölüm, uzak verileri almak için kullanılan en yaygın teknikleri açıklar.  
  
### <a name="accessing-files-by-using-http"></a>HTTP kullanarak dosyalara erişme  
 Kullanarak bir Web sunucusundan veri erişebilirsiniz <xref:System.Net.WebClient> veya <xref:System.Net.HttpWebRequest> sınıfını <xref:System.Net> ad alanı. Veriler statik dosyalar olabilir veya [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] ham metni veya XML veri döndüren uygulamaları. Verilerinizi XML biçiminde verileri almanın en hızlı yolu kullanarak ise, <xref:System.Xml.XmlDocument> sınıfı, özelliği <xref:System.Xml.XmlDocument.Load%2A> yöntem bağımsız değişken olarak bir URL alır. Bir örnek için bkz: [bir XML belgesi DOM okuma](/dotnet/standard/data/xml/reading-an-xml-document-into-the-dom).  
  
 Uygulamanızın HTTP üzerinden uzak veri eriştiğinde güvenlik dikkate almanız gerekir. Varsayılan olarak, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulamanın erişim için ağ kaynaklarına, uygulamanızın nasıl dağıtıldığına bağlı olarak, kısıtlanmış olabilir. Kötü amaçlı programların ayrıcalıklı uzak veri erişimini veya ağ üzerindeki diğer bilgisayarlara saldırmak için kullanıcının bilgisayar kullanarak engellemek için bu kısıtlamalar uygulanır.  
  
 Aşağıdaki tabloda, kullanıyor olabileceğiniz dağıtım stratejilerini ve varsayılan Web izinlerini listeler.  
  
|Dağıtım türü|Varsayılan ağ izinleri|  
|---------------------|---------------------------------|  
|Web yükleme|Yalnızca uygulamanın yüklü olduğu Web sunucusuna erişebilir|  
|Dosya Paylaşımı yükleme|Tüm Web sunucularının erişemiyor|  
|CD-ROM yükleme|Tüm Web sunucularına erişebilir|  
  
 Varsa, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama, bir Web sunucusu güvenlik kısıtlamaları nedeniyle erişemiyor, uygulama onay gerekir <xref:System.Net.WebPermission> bu Web sitesi için. Güvenlik izinlerini artırma hakkında daha fazla bilgi için bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama, bkz: [ClickOnce uygulamalarının güvenliğini sağlama](../deployment/securing-clickonce-applications.md).  
  
### <a name="accessing-data-through-an-xml-web-service"></a>XML Web hizmeti aracılığıyla verilere erişme  
 Verilerinizi bir XML Web hizmeti olarak kullanıma sunmak, bir XML Web hizmeti proxy'si kullanarak verilere erişebilirsiniz. Proxy bir [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] Sınıf Oluştur kullanarak [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. XML Web hizmeti işlemleri — müşteriler, yerleştirme siparişleri ve benzeri alma gibi — proxy üzerinde yöntemler olarak sunulur. Bu Web Hizmetleri ham metin veya XML dosyaları kullanmak çok daha kolay hale getirir.  
  
 Olarak aynı güvenlik sınırlamaları XML Web hizmetiniz HTTP üzerinden çalışırsa, hizmet bağlanacak <xref:System.Net.WebClient> ve <xref:System.Net.HttpWebRequest> sınıfları.  
  
### <a name="accessing-a-database-directly"></a>Bir veritabanına doğrudan erişim  
 İçinde yer alan sınıfları kullanabilirsiniz <xref:System.Data> ağınızın, ancak SQL Server için güvenlik sorunları dikkate almalı gibi bir veritabanı sunucusu ile doğrudan bağlantı kurmak için ad alanı. HTTP isteklerinin tersine, veritabanı bağlantı isteklerini kısmi güven altında varsayılan olarak her zaman Yasak; yüklerseniz, yalnızca bu tür varsayılan izni, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] ROM'dan uygulama. Bu, uygulama tam güven verir. Belirli bir SQL Server veritabanına erişimi etkinleştirmek için uygulamanızın istemelidir <xref:System.Data.SqlClient.SqlClientPermission> ona; SQL sunucusu dışında bir veritabanına erişimi etkinleştirmek için bunu istemelidir <xref:System.Data.OleDb.OleDbPermission>.  
  
 Çoğu zaman, veritabanına doğrudan erişmeniz gerekmez, ancak bunun yerine yazılmış bir Web sunucusu uygulaması aracılığıyla erişirsiniz [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] veya bir XML Web hizmeti. Bu şekilde tüm veritabanı erişimlerinin ise genellikle en iyi yöntem, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama bir Web sunucusundan dağıtılır. Uygulamanızın izinlerini yükseltmeden kısmi güvende sunucuya erişebilirsiniz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: ClickOnce uygulamasına bir veri dosyası dahil](../deployment/how-to-include-a-data-file-in-a-clickonce-application.md)