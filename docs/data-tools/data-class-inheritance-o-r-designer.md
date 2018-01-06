---
title: "Veri sınıf devralma (O R Tasarımcısı) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: af32653c-f4e6-4217-8c5a-e32b322b4918
caps.latest.revision: "3"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.workload: data-storage
ms.openlocfilehash: c881f70b966a4a0b4d5bf173bcac4569d6a9c1ae
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="data-class-inheritance-or-designer"></a>Veri sınıf devralma (O/R Tasarımcısı)
Gibi diğer nesneler [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] sınıf devralma kullanabilirsiniz ve diğer sınıflardan türetilmiş olmalıdır. Kod içinde bir sınıf diğerinden devralır bildirme tarafından nesneleri arasındaki ilişkiler devralma belirtebilirsiniz. Bir veritabanında, çeşitli yollarla devralma ilişkisi oluşturulur. [!INCLUDE[vs_ordesigner_long](../data-tools/includes/vs_ordesigner_long_md.md)] ([!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]) Genellikle ilişkisel sistemlerinde gerçekleştirilir gibi tek Tablo Devralma kavramını destekler.  
  
 Tek Tablo Devralma temel ve türetilen sınıflar için sütun içeren bir tek veritabanı tablosu yok. İlişkisel veri ile ayrıştırıcı sütunun herhangi verilen kayıt ait hangi sınıfı belirleyen bir değer içerir. Örneğin, herkesin bir şirket tarafından işe içeren bir kişi tablo göz önünde bulundurun. Bazı kişiler çalışanlar ve bazı kişiler yöneticileri. Kişi tablosu çalışanlar için yöneticileri ve 2 değerini 1 değerine sahip türü adlı bir sütun içerir. Ayrıştırıcı sütunun türünü sütundur. Bu senaryoda, çalışanların öğesinin bir alt kümesi oluşturmak ve yalnızca bir tür değeri 2 sahip kayıtları sınıfıyla doldurun.  
  
 Yapılandırdığınızda devralma varlık sınıflarını kullanarak [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)], iki kez tasarımcıya devralma veri içeren tek tablo sürükleyin: devralma hiyerarşisinde her sınıf için bir kez. Tabloları Designer'a ekledikten sonra bunları bir devralma öğesinden bağlamak **Nesne İlişkisel Tasarımcısı** araç kutusunu ve ardından kümesi dört devralma özelliklerinde **özellikleri** penceresi.  
  
## <a name="inheritance-properties"></a>Devralma Özellikleri  
 Aşağıdaki tabloda, devralma özellikleri ve açıklamaları listelenmektedir:  
  
|Özellik|Açıklama|  
|--------------|-----------------|  
|Ayrıştırıcı özelliği|Hangi sınıfın belirler (sütuna eşlenen) özelliği geçerli kayıt ait.|  
|Taban sınıf Ayrıştırıcıyı değeri|Bir kayıt temel sınıfını olduğunu belirler (Ayrıştırıcıyı özelliği olarak tasarlanmış sütunda) değeri.|  
|Türetilmiş sınıf Ayrıştırıcıyı değeri|Bir kayıt türetilmiş sınıf olduğunu belirleyen değeri (Ayrıştırıcıyı özelliği olarak tasarlanmış özelliğinde).|  
|Devralma varsayılan|Özellik değeri olarak tasarlanmış olduğunda doldurulması gerekir sınıfının **Ayrıştırıcıyı özelliği** ya da eşleşmiyor **temel sınıf Ayrıştırıcıyı değeri** veya **türetilen sınıfı Ayrıştırıcı değeri**.|  
  
 Devralma kullanan ve ilişkisel verilere karşılık gelen bir nesne modeli oluşturmak biraz kafa karıştırıcı olabilir. Bu konuda temel kavramları ve devralma yapılandırmak için gerekli olan özellikler hakkında bilgi sağlar. Devralma ile yapılandırma hakkında daha anlaşılır bir açıklama aşağıdaki konularda [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)].  
  
|Konu|Açıklama|  
|-----------|-----------------|  
|[Nasıl yapılır: devralma O/R Tasarımcısı kullanarak yapılandırma](../data-tools/how-to-configure-inheritance-by-using-the-o-r-designer.md)|Tek Tablo Devralma kullanarak varlık sınıfları yapılandırmayı açıklar [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)].|  
|[İzlenecek yol: Tek tablo devralma (O/R Tasarımcısı) kullanarak LINQ-SQL sınıfları oluşturma](../data-tools/walkthrough-creating-linq-to-sql-classes-by-using-single-table-inheritance-o-r-designer.md)|Tek Tablo Devralma kullanarak varlık sınıfları yapılandırma hakkında adım adım yönergeler sağlar [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)].|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [LINQ-SQL Visual Studio Araçları](../data-tools/linq-to-sql-tools-in-visual-studio2.md)   
 [İzlenecek yol: LINQ-SQL sınıfları (O R Tasarımcısı) oluşturma](how-to-create-linq-to-sql-classes-mapped-to-tables-and-views-o-r-designer.md)   
 [İzlenecek yol: Tek tablo devralma (O/R Tasarımcısı) kullanarak LINQ-SQL sınıfları oluşturma](../data-tools/walkthrough-creating-linq-to-sql-classes-by-using-single-table-inheritance-o-r-designer.md)   
 [Başlarken](/dotnet/framework/data/adonet/sql/linq/getting-started)