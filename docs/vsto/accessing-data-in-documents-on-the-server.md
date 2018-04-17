---
title: Sunucudaki belgelerde verilere erişme | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- data [Office development in Visual Studio], accessing on server
- data access [Office development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 7d1831649c36249f4858dc5bd52ea90b4fd938eb
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="accessing-data-in-documents-on-the-server"></a>Sunucudaki Belgelerde Verilere Erişme
  Microsoft Office Word veya Microsoft Office Excel nesne modelini kullanmak zorunda kalmadan bir belge düzeyi özelleştirmelerinde veri karşı programlama yapabilirsiniz. Bu belgede Word sahip olmayan bir sunucuda bulunan verilere erişebilir veya Excel yüklü anlamına gelir. Örneğin, bir sunucuda kod (örneğin, bir [!INCLUDE[vstecasp](../sharepoint/includes/vstecasp-md.md)] sayfa) bir belgedeki verileri özelleştirebilir ve özelleştirilmiş belgeyi son kullanıcıya gönderin. Son kullanıcı belgeyi açtığında, veri bağlama çözüm bütünleştirilmiş kodda özelleştirilmiş veri belgeye bağlar. Belgedeki verileri kullanıcı arabiriminden ayrılmış olduğundan, bu mümkündür. Daha fazla bilgi için bkz: [önbelleğe alınmış verileri belge düzeyi özelleştirmelerinde](../vsto/cached-data-in-document-level-customizations.md).  

 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  

## <a name="caching-data-for-use-on-a-server"></a>Sunucuda kullanmak için verileri önbelleğe alma  
 Belgedeki bir veri nesnesini önbelleğe almak için kendisiyle işaretlemek <xref:Microsoft.VisualStudio.Tools.Applications.Runtime.CachedAttribute> özniteliği tasarım zamanında veya kullanmak `StartCaching` çalışma zamanında konak öğesinin yöntemi. Belgede, bir veri nesnesini önbelleğe aldığınızda [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] belgede depolanan bir XML dizesine nesneyi seri hale getirir. Nesneleri önbelleğe almak için uygun olması için belirli gereksinimleri karşılaması gerekir. Daha fazla bilgi için bkz: [veri önbelleğe alma](../vsto/caching-data.md).  

 Sunucu tarafı kodu, veri önbelleğindeki tüm veri nesnelerini yönetebilirsiniz. Böylece istemci üzerinde belge açıldığında verilerde yapılan sunucu tarafı değişiklikleri otomatik olarak görünmesini önbelleğe alınan veriler örneklerine ilişkili denetimleri kullanıcı arabirimi ile eşitlenir.  

## <a name="accessing-data-in-the-cache"></a>Önbellekteki verilere erişme  
 Önbellekteki verileri uygulamalardan ofis dışından örneğin bir konsol uygulaması, bir Windows Forms uygulaması veya bir Web sayfasına erişebilirsiniz. Önbelleğe alınan verilere erişen uygulama tam güven olmalıdır; kısmi güven ilişkisi olan bir Web uygulaması ekleme, almak veya bir Office belgesine önbelleğe alınmış verileri değiştirme.  

 Veri önbelleği tarafından sunulan bir koleksiyon hiyerarşisi aracılığıyla erişilebilen <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.CachedData%2A> özelliği <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> sınıfı:  

-   <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.CachedData%2A> Özelliği döndürür bir <xref:Microsoft.VisualStudio.Tools.Applications.CachedData>, tüm belge düzeyi özelleştirmelerinde önbelleğe alınmış verileri içerir.  

-   Her <xref:Microsoft.VisualStudio.Tools.Applications.CachedData> birini veya birkaçını içeriyor <xref:Microsoft.VisualStudio.Tools.Applications.CachedDataHostItem> nesneleri. A <xref:Microsoft.VisualStudio.Tools.Applications.CachedDataHostItem> tüm tek bir sınıf içinde tanımlanmış önbelleğe alınan veriler nesneleri içerir.  

-   Her <xref:Microsoft.VisualStudio.Tools.Applications.CachedDataHostItem> birini veya birkaçını içeriyor <xref:Microsoft.VisualStudio.Tools.Applications.CachedDataItem> nesneleri. A <xref:Microsoft.VisualStudio.Tools.Applications.CachedDataItem> tek bir önbelleğe alınan veri nesnesi temsil eder.  

 Aşağıdaki kod örneğinde, önbelleğe alınan dizesinde erişmek gösterilmiştir `Sheet1` Excel çalışma kitabı sınıfı. Bu örnek için sağlanan daha büyük bir örneğin parçasıdır <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.Save%2A> yöntemi.  

 [!code-csharp[Trin_ServerDocument#12](../vsto/codesnippet/CSharp/Trin_ServerDocument/Form1.cs#12)]
 [!code-vb[Trin_ServerDocument#12](../vsto/codesnippet/VisualBasic/Trin_ServerDocument/Form1.vb#12)]  

## <a name="modifying-data-in-the-cache"></a>Önbellekteki verileri değiştirme  
 Önbelleğe alınmış veri nesnesini değiştirmek için genellikle aşağıdaki adımları gerçekleştirin:  

1.  Nesne yeni bir örneğini XML gösterimine önbelleğe alınmış nesnenin seri durumdan çıkarır. XML kullanarak erişebilirsiniz <xref:Microsoft.VisualStudio.Tools.Applications.CachedDataItem.Xml%2A> özelliği <xref:Microsoft.VisualStudio.Tools.Applications.CachedDataItem> önbelleğe alınmış veri nesnesini temsil eden.  

2.  Bu kopyaya değişiklikleri yapın.  

3.  Değiştirilen nesneyi, aşağıdaki seçeneklerden birini kullanarak veri önbelleğine sıralayın:  

    -   Otomatik olarak değişiklikleri seri hale getirmek istiyorsanız, kullanmak <xref:Microsoft.VisualStudio.Tools.Applications.CachedDataItem.SerializeDataInstance%2A> yöntemi. Bu yöntem **DiffGram** seri hale getirme biçimi <xref:System.Data.DataSet>, <xref:System.Data.DataTable>ve veri önbelleğindeki veri kümesi nesnelerini belirtilmiş. **DiffGram** biçimi, veri önbelleğine çevrimdışı bir belgede yapılan değişikliklerin sunucuya doğru olarak gönderilmesini sağlar.  

    -   Önbelleğe alınmış verilerde yapılan değişiklikleri için kendi sıralamanızı gerçekleştirmek istiyorsanız, doğrudan yazabileceğiniz <xref:Microsoft.VisualStudio.Tools.Applications.CachedDataItem.Xml%2A> özelliği. Belirtin **DiffGram** kullanırsanız biçimlendirmek bir <xref:System.Data.Common.DataAdapter> verilerde yapılan değişikliklerle bir veritabanını güncelleştirmek için bir <xref:System.Data.DataSet>, <xref:System.Data.DataTable>, veya türü belirtilmiş veri kümesi. Aksi takdirde <xref:System.Data.Common.DataAdapter> varolan satırları değiştirmek yerine yeni satır ekleyerek veritabanını güncelleştirir.  

### <a name="modifying-data-without-deserializing-the-current-value"></a>Geçerli değer seri durumdan olmadan verileri değiştirme  
 Bazı durumlarda, ilk geçerli değeri seri durumdan çıkarılırken olmadan önbelleğe alınmış nesnenin değerini değiştirmek isteyebilirsiniz. Örneğin, bir dize ya da tamsayı gibi basit bir türe sahip bir nesne değeri değiştiriyorsanız veya önbelleğe alınmış başlatma bunu yapabilirsiniz <xref:System.Data.DataSet> bir sunucudaki bir belgedeki. Bu durumlarda, kullandığınız <xref:Microsoft.VisualStudio.Tools.Applications.CachedDataItem.SerializeDataInstance%2A> geçerli değeri önbelleğe alınmış nesnenin ilk seri durumdan çıkarılırken olmadan yöntemi.  

 Aşağıdaki kod örneğinde önbelleğe alınan dize değerini değiştirmek gösterilmiştir `Sheet1` Excel çalışma kitabı sınıfı. Bu örnek için sağlanan daha büyük bir örneğin parçasıdır <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.Save%2A> yöntemi.  

 [!code-csharp[Trin_ServerDocument#11](../vsto/codesnippet/CSharp/Trin_ServerDocument/Form1.cs#11)]
 [!code-vb[Trin_ServerDocument#11](../vsto/codesnippet/VisualBasic/Trin_ServerDocument/Form1.vb#11)]  

### <a name="modifying-null-values-in-the-data-cache"></a>Veri önbelleğindeki null değerlerini değiştirme  
 Veri önbelleği değerine sahip nesneleri depolamaz **null** zaman Belge kaydedildiğinde ve kapalı. Önbelleğe alınan veriler değişiklik yaptığınızda bu sınırlamaya birkaç sonuçları vardır:  

-   Değer veri önbelleğindeki herhangi bir nesne ayarlarsanız **null**, tüm veri önbelleğindeki nesneleri otomatik olarak ayarlanacak **null** zaman belge açılır ve tüm veri önbelleği zaman silinecek Belge kapalı ve kaydedilir. Diğer bir deyişle, veri önbelleğinden önbelleğe alınmış nesnelerin tümü kaldırılacak ve <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.CachedData%2A> koleksiyonu boş olacaktır.  

-   Bir çözüm yapı **null** kullanarak bu nesneleri başlatmak istediğiniz veri ve nesneleri <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> sınıfı belge önce ilk kez açıldığında, tüm nesneleri başlattığınızdan emin olun veri önbelleğindeki. Yalnızca bazı nesneler başlatmak, tüm nesneleri ayarlanacak **null** zaman belge açılır ve belge kaydedilip kapatıldığında tüm veri önbelleği temizlenir.  

## <a name="accessing-typed-datasets-in-the-cache"></a>Yazılan veri kümeleri önbelleğinde erişme  
 Yazılan veri kümesindeki veriler Office çözümü ve bir Windows Forms uygulaması gibi bir uygulama ofis dışından erişmek isterseniz veya bir [!INCLUDE[vstecasp](../sharepoint/includes/vstecasp-md.md)] proje, hem de başvuruda bulunulan ayrı bir derleme içindeki türü belirtilmiş veri kümesi tanımlamalıdır projeleri. Kullanarak türü belirtilmiş veri kümesi her proje için eklerseniz **veri kaynağı Yapılandırma Sihirbazı** veya **veri kümesi Tasarımcısı**, .NET Framework yazılan veri kümeleri farklı iki projelerinde kabul eder . Yazılan veri kümeleri oluşturma hakkında daha fazla bilgi için bkz: [oluşturma ve Visual Studio'da veri kümelerini yapılandırma](/visualstudio/data-tools/create-and-configure-datasets-in-visual-studio).  

## <a name="see-also"></a>Ayrıca Bkz.  
 [Sunucudaki belgelerde verilere erişme](../vsto/accessing-data-in-documents-on-the-server.md)   
 [Belge Düzeyi Özelleştirmelerdeki Önbelleğe Alınmış Veriler](../vsto/cached-data-in-document-level-customizations.md)  
