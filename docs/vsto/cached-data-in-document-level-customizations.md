---
title: "Belge düzeyi özelleştirmelerinde verileri önbelleğe | Microsoft Docs"
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
- data islands [Office development in Visual Studio]
- view [Office development in Visual Studio]
- caching data [Office development in Visual Studio], about caching data
- data caching [Office development in Visual Studio], about data caching
- data [Office development in Visual Studio], cache
- data [Office development in Visual Studio], document-level solutions
- document-level customizations [Office development in Visual Studio], data model
ms.assetid: 84808462-2c5d-4dc8-ab69-491d492b4a51
caps.latest.revision: "27"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: f90aeb03dd62d76064124e9870a5a4dbcd250621
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="cached-data-in-document-level-customizations"></a>Belge Düzeyi Özelleştirmelerdeki Önbelleğe Alınmış Veriler
  Office belgelerindeki görünümünden veri ayırmak için belge düzeyi özelleştirmeleri birincil amacı olan. Veri sayılar ve metin dahil olmak üzere belgede depolanan bilgileri gösterir. Görünüm kullanıcı arabirimi hem de Microsoft Office Word ve Microsoft Office Excel nesne modeline anlamına gelir.  
  
 Visual Studio ayıran verileri belge düzeyi özelleştirmelerinde görünümünden olarak katıştırılmış veri sağlayarak bir *veri adası*, olarak da bilinir *veri önbelleği*. Okuma ya da doğrudan Word veya Excel başlatmadan verileri değiştirebilir. Bu, Microsoft Office yüklü olmayan bir sunucu üzerinde belgeleri verilerde değişiklik yapmanız durumunda faydalı olur. Word ve Excel istemci ortamlarda kullanılmak için tasarlanmıştır; bir sunucu üzerinde çalıştırılmak üzere tasarlanmamıştır.  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
 Belge düzeyi özelleştirmeleri hakkında daha fazla bilgi için bkz: [Office çözümleri geliştirmesine genel bakış &#40; VSTO &#41; ](../vsto/office-solutions-development-overview-vsto.md) ve [belge düzeyi özelleştirmeler mimarisi](../vsto/architecture-of-document-level-customizations.md).  
  
## <a name="understanding-the-cached-data-programming-model"></a>Önbelleğe alınan veriler programlama modelini anlama  
 Veri adası çözümünüzdeki belirli gereksinimleri karşılayan herhangi bir nesne içerebilir. Bu nesneler dahil <xref:System.Data.DataSet> nesneleri <xref:System.Data.DataTable> nesneleri ve sıralanabilen herhangi bir nesne <xref:System.Xml.Serialization.XmlSerializer> sınıfı. Daha fazla bilgi için bkz: [veri önbelleğe alma](../vsto/caching-data.md).  
  
 Görünüm için önbelleğe alınan verileri sağlamak için Windows Forms denetimlerini bağlayabilirsiniz ve *konak denetimlerini* veri adası nesnelerine belgesinde. Veri bağlama veri adası verilere bağlı denetimler arasındaki bu ikisini eşitler. Doğrulama kodu denetimlerin bağımsızdır verileri de ekleyebilirsiniz. Daha fazla bilgi için bkz: [Office çözümlerinde denetimlere veri bağlama](../vsto/binding-data-to-controls-in-office-solutions.md).  
  
 Konak denetimleri Excel ve Word nesne modellerindeki yerel nesneleri sürümleri genişletilmiştir. Yerel nesnelerden farklı olarak, ana bilgisayar denetimleri yönetilen veri nesnelerine doğrudan bağlı olabilir. Daha fazla bilgi için bkz: [konak öğelerine ve denetimlerine genel bakış](../vsto/host-items-and-host-controls-overview.md) ve [Office belgeleri genel bakış Windows Forms denetimleri](../vsto/windows-forms-controls-on-office-documents-overview.md).  
  
## <a name="accessing-cached-data-on-the-server"></a>Sunucuda önbelleğe alınan verilere erişme  
 Bir belgedeki önbelleğe alınan verilere erişmek için kullanabileceğiniz <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> sınıfı. Bu sınıf, bir parçasıdır [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)], ve bir sunucuda çalışan Excel veya Word'den olmadan kullanılabilir. Kullanıcı belge sonra önbelleğe alınmış verileri değiştirme, veriye bağlı olan herhangi bir denetim değişiklikleri otomatik olarak eşitlenir ve kullanıcının güncelleştirilmiş verilerle sunulan açtığında. Daha fazla bilgi için bkz: [sunucudaki belgelerde verilere erişme](../vsto/accessing-data-in-documents-on-the-server.md).  
  
 Excel ve Word yalnızca istemcide görüntülemek için bu sunucudaki veri yazmak için gerekli değildir. Excel ve Word bile sunucuya yüklenmesi gerekmez. Bu, geliştirilmiş ölçeklenebilirlik ve veri Adaları içeren belgeleri hızlı, toplu işleme gerçekleştirmenize olanak sağlar.  
  
## <a name="data-caching-for-offline-use"></a>Çevrimdışı kullanım için önbelleğe alma  
 Veri adası veri depolama çevrimdışı senaryolara olanak sağlar. Bir kullanıcı ilk kez bir belge açılır veya belge sunucusundan gelen istekleri, veri adası en son verilerle doldurulur. Veri adası belgede önbelleğe alınır ve ardından çevrimdışı olarak kullanılabilir. Dinamik bağlantı kullanılabilir olsa bile kullanıcı (ve kodunuzu) veri yönetebilirsiniz. Kullanıcı yeniden bağlandığında, verilerde yapılan değişiklikleri geri sunucu veri kaynağına yayılamaz.  
  
## <a name="cached-data-and-custom-xml-parts-compared"></a>Önbelleğe alınan veriler ve Karşılaştırılan Özel XML bölümleri  
 Özel XML bölümleri, bir belgedeki rasgele XML parçalarının depolamak için bir yol olarak 2007 Microsoft Office sistemi tanıtıldı. Özel XML bölümleri birçok veri önbelleği aynı senaryolarda yararlı olsa da, veri adası ve özel XML bölümleri arasında bazı farklar vardır. Özel XML bölümleri hakkında daha fazla bilgi için bkz: [özel XML bölümlerine genel bakış](../vsto/custom-xml-parts-overview.md).  
  
 Aşağıdaki tabloda bazı farklar ve benzerlikler listeler.  
  
||Veri önbelleği|Özel XML bölümleri|  
|-|----------------|----------------------|  
|Office uygulamaları bunları kullanabilir miyim?|Aşağıdaki uygulamalar için belge düzeyi özelleştirmeleri:<br /><br /> -Excel<br />-Word|Aşağıdaki uygulamalar için belge düzeyi ve uygulama düzeyi çözümleri:<br /><br /> -Excel<br />-PowerPoint<br />-Word|  
|Hangi veri türlerini, depolayabilir miyim?|Herhangi ortak bir nesne özelleştirme derlemenizde belirli gereksinimleri karşılıyor. Daha fazla bilgi için bkz: [veri önbelleğe alma](../vsto/caching-data.md).|Tüm XML verileri.|  
|Microsoft Office uygulamaları başlatmadan veri erişebilir mi?|Kullanarak Evet, <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> sınıfı tarafından sağlanan [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)].|Sınıfları kullanarak Evet, <xref:System.IO.Packaging> ad alanı, veya açık XML biçimi SDK'sını kullanarak.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Office çözümlerindeki veriler](../vsto/data-in-office-solutions.md)   
 [Visual Studio'da Office çözümleri mimarisi](../vsto/architecture-of-office-solutions-in-visual-studio.md)  
  
  