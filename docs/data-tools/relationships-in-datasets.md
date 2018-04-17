---
title: Veri kümeleri arasında ilişkiler oluşturmak için DataRelation kullanın | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vbData.Microsoft.VSDesigner.DataSource.DesignRelation
- vbdata.Microsoft.VSDesigner.DataSource.DesignRelation
helpviewer_keywords:
- relationships, about relationships
- datasets [Visual Basic], relationships
- relationships, datasets
ms.assetid: cfe274f0-71fe-40f6-994e-7c7f6273c9ba
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 94fb9217b779d00314b2a188ae2fe6f7d0ba4bb1
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="create-relationships-between-datasets"></a>Veri kümeleri arasında ilişkiler oluşturun
İlgili verileri içeren veri kümeleri tabloları kullanım <xref:System.Data.DataRelation> nesneleri tabloları arasında bir üst/alt ilişkisi temsil eder ve ilgili kayıtları birbirlerinden döndürmek için. İlgili tablolar kullanarak veri kümelerine ekleme **veri kaynağı Yapılandırma Sihirbazı**, veya **veri kümesi Tasarımcısı**, oluşturur ve yapılandırır <xref:System.Data.DataRelation> nesnesi.  
  
<xref:System.Data.DataRelation> Nesnesi iki işlevleri gerçekleştirir:  
  
-   Kullanılabilir birlikte çalıştığınız bir kayıtla ilgili kayıt yapabilirsiniz. Bir üst kayıtta varsa alt kayıtları sağlar (<xref:System.Data.DataRow.GetChildRows%2A>) ve bir alt kayıtla çalışıyorsanız üst kaydı (<xref:System.Data.DataRow.GetParentRow%2A>).  
  
-   Bir üst kaydı sildiğinizde ilgili alt kayıtları silme gibi başvuru bütünlüğü kısıtlamalarını zorunlu kılabilir.  
  
Doğru bir birleşim ve işlevini arasındaki farkı anlamak önemlidir bir <xref:System.Data.DataRelation> nesnesi. Doğru bir birleştirme kayıtları üst ve alt tablodan alınır ve tek, düz kayıt kümesi koyun. Kullandığınızda, bir <xref:System.Data.DataRelation> nesne, yeni bir kayıt oluşturulur. Bunun yerine, DataRelation tablolar arasında ilişki izler ve üst ve alt kayıtları eşitlenmiş tutar.  
  
## <a name="datarelation-objects-and-constraints"></a>DataRelation nesneleri ve kısıtlamaları  
A <xref:System.Data.DataRelation> nesnesi oluşturun ve aşağıdaki kısıtlamalar uygulamak için de kullanılır:  
  
-   Tablodaki bir sütun yinelenen içerdiğini garanti bir benzersiz kısıtlamasına.  
  
-   Bir veri kümesi üst ve alt tabloda arasında bilgi tutarlılığını korumak için kullanılan bir yabancı anahtar kısıtlaması.  
  
Belirttiğiniz kısıtlamaları bir <xref:System.Data.DataRelation> nesnesi, otomatik olarak uygun nesneleri oluşturma veya özelliklerini ayarlama uygulanır. Bir yabancı anahtar kısıtlaması kullanarak oluşturursanız <xref:System.Data.DataRelation> nesnesi, örneklerini <xref:System.Data.ForeignKeyConstraint> sınıfı eklenir <xref:System.Data.DataRelation> nesnenin <xref:System.Data.DataRelation.ChildKeyConstraint%2A> özelliği.  
  
Benzersiz bir kısıtlama uygulanan yalnızca ayarlayarak ya da <xref:System.Data.DataColumn.Unique%2A> özelliği için bir veri sütununun `true` veya örneği ekleyerek <xref:System.Data.UniqueConstraint> sınıfının <xref:System.Data.DataRelation> nesnenin <xref:System.Data.DataRelation.ParentKeyConstraint%2A> özelliği. Bir veri kümesinde kısıtlamaları askıya alma hakkında daha fazla bilgi için bkz: [bir veri kümesini doldururken kısıtlamaları kapatma kapatma](../data-tools/turn-off-constraints-while-filling-a-dataset.md).  
  
### <a name="referential-integrity-rules"></a>Bilgi tutarlılığı kuralları  
Yabancı anahtar kısıtlaması bir parçası olarak, üç noktalarda uygulanan bilgi tutarlılığı kuralları belirtebilirsiniz:  
  
-   Bir üst kayıt güncelleştirildiğinde  
  
-   Bir üst kaydı silindiğinde  
  
-   Bir değişiklik olduğunda kabul veya reddetti  
  
Yapabileceğiniz kuralları belirtilen <xref:System.Data.Rule> numaralandırma ve olan aşağıdaki tabloda listelenmektedir.  
  
|Yabancı anahtar kısıtlaması kuralı|Eylem|  
|----------------------------------|------------|  
|<xref:System.Data.Rule.Cascade>|Üst kayda yapılan değişiklik (güncelleştirme veya silme) alt tablosundaki ilgili kayıtlar da yapılır.|  
|<xref:System.Data.Rule.SetNull>|Alt kayıtlar silinmez, ancak alt kayıtları yabancı anahtarı kümesine <xref:System.DBNull>. Bu ayar, alt kayıtlar "artık" bırakılabilir — diğer bir deyişle, bunlar hiç üst kayıtlar ilişkisi. **Not:** bu kuralı kullanarak alt tablosunda geçersiz veri içinde sonuçlanabilir.|  
|<xref:System.Data.Rule.SetDefault>|İlgili alt kayıtları yabancı anahtarı varsayılan değer olarak ayarlanır (sütunun tarafından belirlenen <xref:System.Data.DataColumn.DefaultValue%2A> özelliği).|  
|<xref:System.Data.Rule.None>|İlgili alt kayıtları değişiklik yapılmaz. Bu ayar, alt kayıtları geçersiz üst kayıtlar başvurular içerebilir.|  
  
Veri kümesi tablolardaki güncelleştirmeleri hakkında daha fazla bilgi için bkz: [verileri veritabanına kaydetmek](../data-tools/save-data-back-to-the-database.md).  
  
### <a name="constraint-only-relations"></a>Yalnızca kısıtlaması ilişkileri  
Oluştururken bir <xref:System.Data.DataRelation> nesnesi, ilişki yalnızca kısıtlamaları zorlamak için kullanılması gerektiğini belirtme seçeneği vardır; diğer bir deyişle, bu da ilgili kayıtları erişmek için kullanılmayacak. Biraz daha verimli olur ve ilgili kayıtları özelliğine sahip olandan daha az yöntemleri içeren bir veri kümesi oluşturmak için bu seçeneği kullanın. Ancak, ilgili kayıtlara erişme mümkün olmayacaktır. Örneğin, yalnızca kısıtlaması ilişkisi alt kayıtları hala olan üst kaydını silme engeller ve alt kayıtları üst erişilemiyor.  
  
## <a name="manually-creating-a-data-relation-in-the-dataset-designer"></a>El ile veri kümesi Tasarımcısı'nda veri ilişkisi oluşturma  
Visual Studio'da veri Tasarım araçları kullanarak veri tabloları oluşturduğunuzda, veri kaynağından bilgileri toplanabilir ilişkileri otomatik olarak oluşturulur. Veri tablolarından el ile eklerseniz **DataSet** sekmesinde **araç**, ilişki elle oluşturmanız gerekebilir. Oluşturma hakkında bilgi için <xref:System.Data.DataRelation> nesneleri programlı olarak bkz [ekleme DataRelations](/dotnet/framework/data/adonet/dataset-datatable-dataview/adding-datarelations).  
  
Veri tabloları arasında ilişkiler görünür satırlar halinde **veri kümesi Tasarımcısı**, ilişki bire çok yönünü gösteren bir anahtar ve sonsuz karakteri ile. Varsayılan olarak, ilişkinin adını tasarım yüzeyine görünmez.  
  
[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]  
  
#### <a name="to-create-a-relationship-between-two-data-tables"></a>İki veri tabloları arasında bir ilişki oluşturmak için  
  
1.  Bir veri kümesini açma **veri kümesi Tasarımcısı**. Daha fazla bilgi için bkz: [izlenecek yol: veri kümesi tasarımcısında bir veri kümesi oluşturma](walkthrough-creating-a-dataset-with-the-dataset-designer.md).  
  
2.  Sürükleme bir **ilişkisi** nesnesinin **DataSet** ilişki alt veri tablosunda üzerine araç.  
  
     **İlişkisi** iletişim kutusu açılır ve doldurma **alt tablo** sürüklediğiniz tablo kutusuyla **ilişkisi** üzerine nesne.  
  
3.  Üst tablodan seçin **üst tablo** kutusu. Üst tablo bir-çok ilişkisi "bir" tarafındaki kayıtları içerir.  
  
4.  Doğru alt tablo görüntülendiğini doğrulayın **alt tablo** kutusu. Alt tablo bir-çok ilişkisi "birçok" tarafındaki kayıtları içerir.  
  
5.  İlişki için bir ad yazın **adı** kutusunda veya seçili tablolara varsayılan adı bırakın. Bu gerçek adıdır <xref:System.Data.DataRelation> kodu nesnesi.  
  
6.  Tabloları birleştirme sütunları seçin **anahtar sütunları** ve **yabancı anahtar sütunları** listeler.  
  
7.  Bir ilişki, kısıtlama veya her ikisini de oluşturmak bu seçeneği seçin.   
  
8.  Seçin veya temizleyin **iç içe geçmiş ilişkisi** kutusu. Bu seçenek ayarlar seçme <xref:System.Data.DataRelation.Nested%2A> özelliğine `true`, ve satır ilişkisinin XML verileri olarak yazılmış ya da eşitlenmiş olan satırları üst sütun içinde iç içe alt neden <xref:System.Xml.XmlDataDocument>. Daha fazla bilgi için bkz: [iç içe geçme DataRelations](/dotnet/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations).  
  
9. Bu tablolardaki kayıtlarda değişiklik yapıyorsunuz zaman zorlanacak kurallarını ayarlayın. Daha fazla bilgi için bkz. <xref:System.Data.Rule>.  
  
10. Tıklatın **Tamam** ilişki oluşturmak için. Tasarımcı iki tablo arasında bir ilişki satır görünür.  
  
#### <a name="to-display-a-relation-name-in-the-dataset-designer"></a>Veri kümesi Tasarımcısı'nda bir ilişki adı görüntülemek için  
  
1.  Bir veri kümesini açma **veri kümesi Tasarımcısı**. Daha fazla bilgi için bkz: [izlenecek yol: veri kümesi tasarımcısında bir veri kümesi oluşturma](walkthrough-creating-a-dataset-with-the-dataset-designer.md).  
  
2.  Gelen **veri** menüsünde, select **ilişki etiketlerini göster** ilişki adı görüntülemek için komutu. İlişki adı gizlemek için bu komutu temizleyin.

## <a name="see-also"></a>Ayrıca bkz.
[Visual Studio’da veri kümeleri oluşturma ve yapılandırma](../data-tools/create-and-configure-datasets-in-visual-studio.md)