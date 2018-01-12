---
title: "Verileri önbelleğe alma | Microsoft Docs"
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
- data caching [Office development in Visual Studio], about caching data
- data [Office development in Visual Studio], caching
- data caching [Office development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 0d036f11d60a8da1362464a875fdc0f2771cac0e
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="caching-data"></a>Verileri Önbelleğe Alma
  Böylece çevrimdışı veya Microsoft Office Word veya Microsoft Office Excel açmadan veriler erişilebilir bir belge düzeyi özelleştirmelerinde veri nesnelerini önbelleğe alabilir. Bir nesne önbelleğe almak için nesneyi belirli gereksinimleri karşılayan bir veri türü olmalıdır. .NET Framework'teki birçok ortak veri türleri dahil olmak üzere bu gereksinimleri karşılayan <xref:System.String>, <xref:System.Data.DataSet>, ve <xref:System.Data.DataTable>.  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
 Nesne veri önbelleğine eklemek için iki yolu vardır:  
  
-   Çözüm yapılandırıldığında veri önbelleğine nesne eklemek için uygulamanız <xref:Microsoft.VisualStudio.Tools.Applications.Runtime.CachedAttribute> özniteliğini nesne bildirimine. Daha fazla bilgi için bkz: [nasıl yapılır: bir sunucuya veya çevrimdışı kullanım için verileri önbelleğe](../vsto/how-to-cache-data-for-use-offline-or-on-a-server.md).  
  
-   Program aracılığıyla bir nesne çalışma zamanında veri önbelleğine eklemek için kullanın `StartCaching` gibi yöntemi bir ana öğe `ThisDocument` veya `ThisWorkbook` sınıfları. Daha fazla bilgi için bkz: [nasıl yapılır: program aracılığıyla bir veri kaynağı Office belgesinden önbelleğe](../vsto/how-to-programmatically-cache-a-data-source-in-an-office-document.md).  
  
 Bir nesne veri önbelleğine ekledikten sonra erişim ve Word veya Excel başlatmadan önbelleğe alınmış verileri değiştirme. Daha fazla bilgi için bkz: [sunucudaki belgelerde verilere erişme](../vsto/accessing-data-in-documents-on-the-server.md).  
  
## <a name="requirements-for-data-objects-to-be-cached"></a>Önbelleğe alınacak veri nesneleri için gereksinimleri  
 Bir veri nesnesi çözümünüzdeki önbelleğe almak için nesne bu gereksinimleri karşılaması gerekir:  
  
-   Okuma/yazma ortak alan veya bir konak öğesi özelliği gibi olması `ThisDocument` veya `ThisWorkbook` sınıfları.  
  
-   Bir dizin oluşturucu veya diğer parametreli özellik olmamalıdır.  
  
 Ayrıca, veri nesnesi getirilmeli <xref:System.Xml.Serialization.XmlSerializer> nesne türünü anlamına gelir sınıfı şu özelliklere sahip olması gerekir:  
  
-   Bir ortak türü olmalıdır.  
  
-   Hiçbir parametre bir public oluşturucuya sahip.  
  
-   Ek güvenlik ayrıcalıkları gerektiren kod yürütmez.  
  
-   (Diğer özelliklerini göz ardı edilir) yalnızca okuma/yazma ortak özellikleri kullanıma sunar.  
  
-   Çok boyutlu diziler (iç içe diziler kabul edilir) kullanıma sunmak değil.  
  
-   Arabirimler özellikleri ve alanları döndürür değil.  
  
-   Uygulamaz <xref:System.Collections.IDictionary> koleksiyonu durumunda.  
  
 Bir veri nesnesini önbelleğe aldığınızda [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] depolanan XML dizesine nesneyi serileştiren bir *özel XML parçaları* belgedeki. Daha fazla bilgi için bkz: [özel XML bölümlerine genel bakış](../vsto/custom-xml-parts-overview.md).  
  
## <a name="cached-data-size-limits"></a>Önbelleğe alınan veriler boyutu sınırları  
 Toplam veri önbelleği belgede ve herhangi bir veri önbelleği tek bir nesnenin boyutu ekleyebilirsiniz veri miktarını bazı sınırlamalar vardır. Bu sınırı aşarsanız, verileri veri önbelleğine kaydedildikten sonra uygulama kapanabilir.  
  
 Bu sınırlar önlemek için aşağıdaki yönergeleri izleyin:  
  
-   10 MB'den büyük herhangi bir nesnenin veri önbelleğine eklemeyin.  
  
-   Birden fazla 100 MB Toplam veri tek bir belgenin veri önbelleğindeki eklemeyin.  
  
 Bunlar yaklaşık değerlerdir. Tam sınırları kullanılabilir RAM ve çalışan işlemlerin sayısı gibi çeşitli etmenlere bağlıdır.  
  
## <a name="controlling-the-behavior-of-cached-objects"></a>Önbelleğe alınan nesnelerin davranışını denetleme  
 Önbelleğe alınan nesnesinin davranışı üzerinde daha fazla denetim kazanmak için uygulayabileceğiniz <xref:Microsoft.VisualStudio.Tools.Applications.Runtime.ICachedType> arabirimde önbelleğe alınmış nesnenin türü. Örneğin, kullanıcı nesnesi değiştirildiğinde nasıl bilgilendirileceğini denetlemek istiyorsanız, bu arabirimi uygulayabilirsiniz. Nasıl uygulandığını gösteren kod örnekleri için <xref:Microsoft.VisualStudio.Tools.Applications.Runtime.ICachedType>, bkz: `ControlCollection` sınıfı dinamik denetimleri örnek Excel ve Word Dinamik denetimler örneğindeki [Office geliştirme örnekleri ve izlenecek yollar](../vsto/office-development-samples-and-walkthroughs.md).  
  
## <a name="persisting-changes-to-cached-data-in-password-protected-documents"></a>Önbelleğe alınan verilerin parola korumalı belgeler üzerinde kalıcı yapılan değişiklikler  
 Veri nesneleri, parola korumalı belgede önbelleğe önbelleğe alınmış verilerde yapılan değişiklikler kaydedilmez. İki yöntem geçersiz kılarak önbelleğe alınmış veri değişikliklerini kaydedebilir. Belge kaydedildiğinde korumayı geçici olarak kaldırmak için bu yöntemleri geçersiz kılın ve kaydetme sonra koruma yeniden işlemi tamamlandı.  
  
 Daha fazla bilgi için bkz: [nasıl yapılır: bir parola korumalı belgede veriyi önbelleğe alma](../vsto/how-to-cache-data-in-a-password-protected-document.md).  
  
## <a name="preventing-data-loss-when-adding-null-values-to-the-data-cache"></a>Null değerler veri önbelleğine eklerken veri kaybını önleme  
 Veri önbelleğine nesneler eklediğinizde, önbelleğe alınmış tüm nesneler olmayan bir başlatılmalıdır**null** belge kaydedilip kapatılmadan önce değer. Önbelleğe alınan herhangi bir nesne varsa bir **null** değer belge kaydedilip kapatıldığında [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] önbelleğe alınmış tüm nesneler veri önbelleğinden otomatik olarak kaldırır.  
  
 Bir nesneyle eklerseniz, bir **null** kullanarak veri önbelleği değerine <xref:Microsoft.VisualStudio.Tools.Applications.Runtime.CachedAttribute> özniteliği tasarım zamanında kullandığınız <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> önbelleğe alınan veriler başlatmak için sınıf nesneleri belge açılmadan önce. Word veya Excel belge bir son kullanıcı tarafından açılmadan önce yüklü olmayan bir sunucuda önbelleğe alınan veriler başlatmak istiyorsanız kullanışlıdır. Daha fazla bilgi için bkz: [sunucudaki belgelerde verilere erişme](../vsto/accessing-data-in-documents-on-the-server.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: veri kullanımı için çevrimdışı veya sunucuda önbelleğe alma](../vsto/how-to-cache-data-for-use-offline-or-on-a-server.md)   
 [Nasıl yapılır: program aracılığıyla bir veri kaynağı Office belgesinden önbelleğe alma](../vsto/how-to-programmatically-cache-a-data-source-in-an-office-document.md)   
 [Nasıl yapılır: bir parola korumalı belgede veriyi önbelleğe alma](../vsto/how-to-cache-data-in-a-password-protected-document.md)   
 [İzlenecek Yol: Önbellekteki Veri Kümesini Kullanarak Ana Öğe-Ayrıntı İlişkisi Oluşturma](../vsto/walkthrough-creating-a-master-detail-relation-using-a-cached-dataset.md)  
  
  