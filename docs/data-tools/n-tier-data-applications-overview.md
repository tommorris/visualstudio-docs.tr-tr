---
title: "N katmanlı veri uygulamalarına genel bakış | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- presentation tier
- middle tier
- data tier
- n-tier applications, about n-tier applications
ms.assetid: 1020581d-eaaa-41a2-aca4-bf4c212895f6
caps.latest.revision: "26"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.workload: data-storage
ms.openlocfilehash: 894e3f7d2ad605aa1e8b8a52a72cd8f83dc90192
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="n-tier-data-applications-overview"></a>N Katmanlı Veri Uygulamalarına Genel Bakış
*N katmanlı* veri uygulamalardır birden çok ayrılmış veri uygulamalarını *katmanları*. "Dağıtılmış uygulamalar" ve "çok katmanlı uygulamalar" olarak da adlandırılan, istemci ve sunucu arasında dağıtılan ayrık katmanları işlemeye n katmanlı uygulamalar ayırın. Veri erişimi uygulamaları geliştirirken açıkça birbirinden uygulamayı oluşturan çeşitli katmanları arasında olması gerekir.  
  
Tipik bir n katmanlı uygulama sunu katmanı, orta katman ve veri katmanı içerir. N katmanlı uygulama çeşitli katmanında ayırmak için en kolay yolu, uygulamanızda dahil etmek istediğiniz her katman için ayrı projeleri oluşturmaktır. Örneğin, sunu katmanı Orta katmanda bulunan bir sınıf kitaplığı veri erişim mantığı olabilir ancak bir Windows Forms uygulaması olabilir. Ayrıca, sunu katmanı orta katman bir hizmeti gibi bir hizmeti aracılığıyla veri erişim mantık iletişim. Uygulama bileşenleri ayrı katmanlara ayırma Bakım ve uygulama ölçeklenebilirliği artırır. Tüm çözüm yeniden tasarlamanız gereksinimi olmadan tek katmanda uygulanabilir yeni teknolojileri daha kolay benimsenmesi etkinleştirerek bunu yapar. Ayrıca, n katmanlı uygulamalar genellikle hassas bilgileri Orta, sunu katmanı yalıtma tutar katman, depolayın.  
  
Visual Studio geliştiriciler n katmanlı uygulamalar oluşturmanıza yardımcı olmak için çeşitli özellikler içerir:  
  
-   Veri kümesi sağlayan bir **DataSet projesi** , dataset (veri varlığı katman) ve TableAdapters öğelerini ayırmanıza olanak tanır özelliği (veri erişim katmanı) ayrık projelerine.  
  
-   [LINQ-SQL Visual Studio Araçları](../data-tools/linq-to-sql-tools-in-visual-studio2.md) ayrı ad alanında DataContext ve veri sınıfları oluşturmak için ayarları sağlar. Bu veri erişimi ve veri varlığı katmanları mantıksal ayrımı sağlar.  
  
-   [LINQ-SQL](/dotnet/framework/data/adonet/sql/linq/index) sağlar <xref:System.Data.Linq.Table%601.Attach%2A> bir uygulamada farklı katmanlarındaki DataContext bir araya getirme olanak tanıyan yöntemi. Daha fazla bilgi için bkz: [N katmanlı ve uzak uygulamalarla LINQ-SQL](/dotnet/framework/data/adonet/sql/linq/n-tier-and-remote-applications-with-linq-to-sql).  
  
## <a name="presentation-tier"></a>Sunu katmanı  
*Sunu katmanı* kullanıcıların bir uygulama ile etkileşim katmanı. Ek uygulama mantığını genellikle de içerir. Tipik sunu katmanı bileşenleri şunları içerir:  
  
-   Veri bileşenleri gibi bağlama <xref:System.Windows.Forms.BindingSource> ve <xref:System.Windows.Forms.BindingNavigator>.  
  
-   Veri gösterimlerini gibi nesne [LINQ-SQL](/dotnet/framework/data/adonet/sql/linq/index) sunu katmanı kullanmak için sınıflar.  
  
Genellikle sunu katmanı hizmet başvurusunu kullanarak orta katman erişen (örneğin, bir [Windows Communication Foundation Hizmetleri ve Visual Studio'da WCF Veri Hizmetleri](../data-tools/windows-communication-foundation-services-and-wcf-data-services-in-visual-studio.md) uygulama). Sunu katmanı veri katmanı doğrudan erişmez. Sunu katmanı orta katman veri erişim bileşeni aracılığıyla veri katmanı ile iletişim kurar.  
  
## <a name="middle-tier"></a>Orta katman  
*Orta katman* sunu katmanı ve veri katmanı katman kullanın birbirleri ile iletişim kurmak için. Tipik orta katman bileşenleri şunları içerir:  
  
-   İş kuralları ve veri doğrulama gibi iş mantığı.  
  
-   Veri erişim bileşenleri ve aşağıdaki gibi mantığı:  
  
    -   [TableAdapters](create-and-configure-tableadapters.md) ve [DataAdapters ve DataReader](/dotnet/framework/data/adonet/dataadapters-and-datareaders).  
  
    -   Veri gösterimlerini gibi nesne [LINQ-SQL](/dotnet/framework/data/adonet/sql/linq/index) sınıflar.  
  
    -   Kimlik doğrulama, yetkilendirme ve kişiselleştirme gibi ortak uygulama hizmetleri.  
  
Aşağıdaki çizimde, özellikleri ve Visual Studio'da kullanılabilir olduğunu ve bunlar n katmanlı uygulama orta katman için nerelerde teknolojileri gösterir.  
  
![Orta katman bileşenleri](../data-tools/media/ntiermid.png "NtierMid")  
Orta katman  
  
Orta katman veri katmanına bir veri bağlantısı kullanarak genellikle bağlanır. Bu veri bağlantısının veri erişimi bileşeni, tipik olarak depolanır.  
  
## <a name="data-tier"></a>Veri katmanı  
*Veri katmanı* temel bir uygulama verilerini depolayan sunucudur (örneğin, çalışan bir sunucu [!INCLUDE[ssNoVersion](../data-tools/includes/ssnoversion_md.md)]).  
  
Aşağıdaki çizimde, özellikleri ve Visual Studio'da kullanılabilir olduğunu ve bunlar n katmanlı uygulama veri katmanına nerelerde teknolojileri gösterir.  
  
![Veri katmanı bileşenleri](../data-tools/media/ntierdatatier.png "ntierdatatier")  
Veri katmanı  
  
Veri katmanı sunu katmanındaki istemciden doğrudan erişilemez. Bunun yerine, orta katman veri erişim bileşeni sunu ve veri katmanlarını arasındaki iletişim için kullanılır.  
  
## <a name="help-for-n-tier-development"></a>N katmanlı geliştirme için Yardım  
Aşağıdaki konular n katmanlı uygulamalar ile çalışma hakkında bilgi sağlar:  
  
[Veri kümeleri ile TableAdapter’ları farklı projelere ayırma](../data-tools/separate-datasets-and-tableadapters-into-different-projects.md)  
  
[İzlenecek yol: N katmanlı veri uygulaması oluşturma](../data-tools/walkthrough-creating-an-n-tier-data-application.md)  

[LINQ to SQL ile N Katmanı ve Uzak Uygulamalar](/dotnet/framework/data/adonet/sql/linq/n-tier-and-remote-applications-with-linq-to-sql)  
  
## <a name="see-also"></a>Ayrıca bkz.
[İzlenecek yol: N katmanlı veri uygulaması oluşturma](../data-tools/walkthrough-creating-an-n-tier-data-application.md)   
[Hiyerarşik güncelleştirme](../data-tools/hierarchical-update.md)   
[Visual Studio'da veri kümesi araçları](../data-tools/dataset-tools-in-visual-studio.md)   
[Visual Studio'da verilere erişime](../data-tools/accessing-data-in-visual-studio.md)