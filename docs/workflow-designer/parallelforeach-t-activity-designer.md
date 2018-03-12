---
title: "ParallelForEach&lt;T&gt; etkinlik Tasarımcısı | Microsoft Docs"
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Statements.ParallelForEach`1.UI
ms.assetid: e93a4843-aef2-4d3e-9a0a-a2d3d1411aa7
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 4d8a46b2535c976bbfe490f85fc5cc5fd6082bc7
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/12/2018
---
# <a name="parallelforeachlttgt-activity-designer"></a>ParallelForEach&lt;T&gt; etkinlik Tasarımcısı
<xref:System.Activities.Statements.ParallelForEach%601> Etkinliği bir koleksiyonun öğelerini numaralandırır ve zaman uyumsuz olarak aynı iş parçacığı üzerinde olduğu paralel koleksiyonunun her öğe için katıştırılmış bir deyimini yürütür. Bu akış denetimi etkinliği yerine kullanın <xref:System.Activities.Statements.Sequence> boşta gitmek için bu etkinliği alt etkinliklerinin beklenen varsa etkinlik.

 <xref:System.Activities.Statements.ParallelForEach%601> Etkinliği olan bir <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A> bir kullanıcı tarafından belirtilen içeren özelliği [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] ifade. <xref:System.Activities.Statements.ParallelForEach%601> Etkinlik her dal tamamlandıktan sonra bu özellik değerlendirir. Değerlendirilirse **true**, sonra <xref:System.Activities.Statements.ParallelForEach%601> etkinlik tamamlandıktan dala çalıştırmadan. Varsa <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A> için değerlendirmez **true**, sonra <xref:System.Activities.Statements.ParallelForEach%601> tüm alt etkinliklerinin tamamlandığında etkinliği tamamlar.

## <a name="the-parallelforeacht-activity"></a>ParallelForEach < T\> etkinliği
 <xref:System.Activities.Statements.ParallelForEach%601> değerleri ve zamanlamaları numaralandırır <xref:System.Activities.Statements.ParallelForEach%601.Body%2A> numaralandırır üzerinde her değeri. Yalnızca zamanlar <xref:System.Activities.Statements.ParallelForEach%601.Body%2A>. Gövde nasıl yürütür bağlıdır <xref:System.Activities.Statements.ParallelForEach%601.Body%2A> boşta gider.

 Varsa <xref:System.Activities.Statements.ParallelForEach%601.Body%2A> değil Git zamanlanmış etkinlikler yığın işlenir çünkü boşta ters sırada yürütülmeden, son zamanlanan etkinlikten önce yürütür. {1,2,3,4} koleksiyonu varsa, örneğin, <xref:System.Activities.Statements.ParallelForEach%601> ve bir **WriteLine** değeri dışına yazmak gövdesi olarak. 4, 3, 2, 1 konsolda yazdırılabilir vardır. Bunun nedeni, **WriteLine** bunu 4 sonra boşta geçmez **WriteLine** etkinlikleri zamanlanmış, yığın davranış kullanarak yürütülen (son çıkış ilk).

 Ancak etkinlikler varsa <xref:System.Activities.Statements.ParallelForEach%601.Body%2A> gibi boşta gidin bir <xref:System.ServiceModel.Activities.Receive> etkinlik veya <xref:System.Activities.Statements.Delay> etkinlik. Ardından tamamlanmalarını bekleyin gerek yoktur. <xref:System.Activities.Statements.ParallelForEach%601> sonraki giden gövde aktivitesi ve çalıştırmak üzere deneyin. Bu etkinlik çok, boşta kalırsa <xref:System.Activities.Statements.ParallelForEach%601> yeniden sonraki gövde faaliyete taşır.

### <a name="using-the-parallelforeacht-activity-designer"></a>ParallelForEach kullanarak\<T > etkinlik Tasarımcısı
 **ParallelForEach\<T >** etkinlik Tasarımcısı bulunabilir **akış denetimi** kategorisini **araç**, hangi tıklayarakerişildiğinde **Araç kutusu** sol tarafındaki sekmesinde [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] (Alternatif olarak, seçin **araç** gelen **Görünüm** menüsü veya CTRL + ALT + X.)

 **ParallelForEach\<T >** gelen etkinlik Tasarımcısı sürüklenebilir **araç** ve oturum bırakılan [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] etkinlik tasarımcıları normalde yerleştirilir olduğunda, yüzey için Örneğin, içini bir **dizisi** etkinlik Tasarımcısı. İçine bırakmadan sonra [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)], oluşturduğu bir <xref:System.Activities.Statements.ParallelForEach%601> içeren varsayılan etkinlik bir <xref:System.Activities.Activity.DisplayName%2A> , **ParallelForEach < Int32\>.**

### <a name="parallelforeacht-properties-in-the-workflow-designer"></a>ParallelForEach < T\> iş akışı Tasarımcısı'nda özellikleri
 Aşağıdaki tabloda en kullanışlı gösterilmektedir <xref:System.Activities.Statements.ParallelForEach%601> etkinlik özellikleri ve bunların Tasarımcısı'nda nasıl kullanıldığı açıklanmaktadır.

|Özellik adı|Gerekli|Kullanım|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Etkinlik Tasarımcısı kolay görünen adını başlığı belirtir. Varsayılan değer **ParallelForEach\<Int32 >**. Değer, isteğe bağlı olarak düzenlenebilir **özellikleri** ızgara veya doğrudan başlığındaki etkinlik Tasarımcısı.|
|<xref:System.Activities.Statements.ParallelForEach%601.Body%2A>|False|Koleksiyondaki her öğe için yürütme etkinliği. Eklemek için <xref:System.Activities.Statements.ParallelForEach%601.Body%2A> etkinlik, bir etkinlik araç bırakma **gövde** kutusuna **ParallelForEach\<T >** etkinlik Tasarımcısı "Buraya etkinliğini Drop" İpucu metni.|
|**TypeArgument**|Doğru|Öğe türü <xref:System.Activities.Statements.ParallelForEach%601.Values%2A> genel parametresi tarafından belirtilen koleksiyon *T*. Varsayılan olarak, **TypeArgument** ayarlanır **Int32**. T türü olarak değiştirmek için **ParallelForEach < T\>**  etkinlik Tasarımcısı değerini değiştirme **TypeArgument** özellik kılavuzunda birleşik giriş kutusu.|
|<xref:System.Activities.Statements.ParallelForEach%601.Values%2A>|Doğru|Üzerinden yineleme öğeleri koleksiyonu. Ayarlamak için <xref:System.Activities.Statements.ParallelForEach%601.Values%2A>, bir [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] ifadesinde **değerleri** kutusuna **ForEach < T\>**  ipucu metnini "Enter VB ifadesi" veya içinde kutusunda etkinlik Tasarımcısı **Değerleri** kutusuna **özellikleri** penceresi.|
|<xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A>||Her yineleme tamamlandıktan sonra değerlendirilir. Bekleyen true sonra zamanlanmış olarak değerlendirir, yinelemeleri iptal edilir. Bu özellik ayarlanmamışsa, tüm zamanlanmış deyimleri tamamlanana kadar yürütün.|

 Varsayılan olarak, döngü yineleyici öğesi olarak adlandırılır. Yineleyici değişken adını değiştirebilirsiniz **ForEach** kutusunda **ParallelForEach\<T >** etkinlik Tasarımcısı. Döngü yineleyici alt ifadelerde kullanılabilir <xref:System.Activities.Statements.ParallelForEach%601> etkinlik.

## <a name="see-also"></a>Ayrıca bkz.

- [Sırası](../workflow-designer/sequence-activity-designer.md)
- [Paralel](../workflow-designer/parallel-activity-designer.md)
- [Denetim Akışı](../workflow-designer/control-flow-activity-designers.md)