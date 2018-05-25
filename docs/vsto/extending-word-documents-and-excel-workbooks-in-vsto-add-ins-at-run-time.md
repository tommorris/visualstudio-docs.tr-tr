---
title: Word belgelerini ve Excel çalışma kitaplarını VSTO eklentileri çalışma zamanında genişletme
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- GetVstoObject method
- application-level add-ins [Office development in Visual Studio], adding controls to documents
- host items [Office development in Visual Studio], creating at run time in add-ins
- application-level add-ins [Office development in Visual Studio], extending Word documents
- application-level add-ins [Office development in Visual Studio], extending Excel workbooks
- controls [Office development in Visual Studio], adding at run time
- HasVstoObject method
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 7b7461ba184850ba53099327fdad44e3103dcd87
ms.sourcegitcommit: 697162f54d3c4e30df702fd0289e447e211e3a85
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/25/2018
---
# <a name="extend-word-documents-and-excel-workbooks-in-vsto-add-ins-at-runtime"></a>Word belgelerini ve Excel çalışma kitaplarını çalışma zamanında VSTO eklentilerini genişletme
  Bir VSTO eklentisi, Word belgelerini ve Excel çalışma kitapları aşağıdaki şekillerde özelleştirmek için kullanabilirsiniz:  
  
-   Yönetilen denetimleri herhangi bir açık belgeye veya çalışma sayfası ekleyin.  
  
-   Varolan liste nesnesini bir Excel çalışma sayfası üzerinde genişletilmiş bir dönüştürme <xref:Microsoft.Office.Tools.Excel.ListObject> olayları gösterir ve verilere Windows Forms veri bağlama modelini kullanarak bağlanabilir.  
  
-   Belirli belgeler, çalışma kitaplarını ve çalışma sayfaları için Word ve Excel tarafından sunulan erişim uygulama düzeyi olayları.  
  
 Bu işlevselliği kullanmak için belge veya çalışma kitabını genişletir çalışma zamanında bir nesne oluşturur.  
  
 **Uygulandığı öğe:** bu makaledeki bilgiler şu uygulamalar için VSTO eklentisi projelerine yöneliktir: Excel ve Word. Daha fazla bilgi için bkz: [Office uygulaması ve proje türüne göre kullanılabilen özellikler](../vsto/features-available-by-office-application-and-project-type.md).  
  
## <a name="generate-extended-objects-in-vsto-add-ins"></a>VSTO eklentileri Genişletilmiş nesneler oluşturmak  
 *Genişletilmiş nesneleri* yerel Word veya Excel nesne modellerinde varolan nesnelere işlevsellik ekleyen Office çalışma zamanı için Visual Studio Araçları tarafından sağlanan türleri örnekleridir (adlı *yerel Office nesneleri*). Genişletilmiş nesne Word veya Excel nesnesi oluşturmak için kullanmak `GetVstoObject` yöntemi. İlk kez, çağırdığınızda `GetVstoObject` yöntemi belirtilen Word veya Excel nesne, belirtilen nesne genişleten yeni bir nesne döndürür. Yöntemini çağırın ve aynı Word veya Excel belirtin her zaman nesne aynı genişletilmiş nesnesi döndürür.  
  
 Genişletilmiş nesne türünü yerel Office nesnesinin türü aynı ada sahip, ancak türü tanımlanan <xref:Microsoft.Office.Tools.Excel> veya <xref:Microsoft.Office.Tools.Word> ad alanı. Örneğin, çağırırsanız `GetVstoObject` genişletmek için yöntemi bir <xref:Microsoft.Office.Interop.Word.Document> nesne, yöntem döndürür bir <xref:Microsoft.Office.Tools.Word.Document> nesnesi.  
  
 `GetVstoObject` Yöntemleri öncelikle VSTO eklentisi projelerine kullanılacak yöneliktir. Belge düzeyi projelerine de bu yöntemleri kullanabilirsiniz, ancak farklı şekilde davranır ve daha az kullanıma sahiptirler.  
  
 Genişletilmiş nesne için belirli bir yerel Office nesnesi zaten oluşturulmuş olup olmadığını belirlemek için `HasVstoObject` yöntemi. Daha fazla bilgi için bkz: [Office nesne genişletilmiş olup olmadığını belirlemek](#HasVstoObject).  
  
### <a name="generate-host-items"></a>Konak öğeleri oluşturma  
 Kullandığınızda `GetVstoObject` belge düzeyinde bir nesne genişletmek için (diğer bir deyişle, bir <xref:Microsoft.Office.Interop.Excel.Workbook>, <xref:Microsoft.Office.Interop.Excel.Worksheet>, veya <xref:Microsoft.Office.Interop.Word.Document>), döndürülen nesne adında bir *konak öğesi*. Bir konak öğesi diğer genişletilmiş nesneler ve denetimler de dahil olmak üzere diğer nesneleri içeren bir türüdür. Karşılık gelen türünü Word veya Excel birincil birlikte çalışma derlemesi benzer, ancak ek özelliklere sahiptir. Konak öğeleri hakkında daha fazla bilgi için bkz: [konak öğelerini ve konak denetimlerine genel bakış](../vsto/host-items-and-host-controls-overview.md).  
  
 Bir konak öğesi oluşturduktan sonra yönetilen denetimleri belge, çalışma kitabı veya çalışma sayfası eklemek için kullanabilirsiniz. Daha fazla bilgi için bkz: [Ekle yönetilen denetimleri belgelere ve çalışma sayfaları](#AddControls).  
  
#### <a name="to-generate-a-host-item-for-a-word-document"></a>Bir Word belgesi için bir konak öğesi oluşturmak için  
  
-   Aşağıdaki kod örneğinde etkin belge için bir konak öğesi oluşturmak nasıl gösterir.  
  
     [!code-vb[Trin_WordAddInDynamicControls#8](../vsto/codesnippet/VisualBasic/trin_wordaddindynamiccontrols/ThisAddIn.vb#8)]
     [!code-csharp[Trin_WordAddInDynamicControls#8](../vsto/codesnippet/CSharp/Trin_WordAddInDynamicControls/ThisAddIn.cs#8)]  
  
#### <a name="to-generate-a-host-item-for-an-excel-workbook"></a>Bir Excel çalışma kitabı konak öğesi oluşturmak için  
  
-   Aşağıdaki kod örneğinde, etkin çalışma kitabı konak öğesi oluşturmak gösterilmiştir.  
  
     [!code-vb[Trin_ExcelAddInDynamicControls#2](../vsto/codesnippet/VisualBasic/trin_exceladdindynamiccontrols4/ThisAddIn.vb#2)]
     [!code-csharp[Trin_ExcelAddInDynamicControls#2](../vsto/codesnippet/CSharp/trin_exceladdindynamiccontrols4/ThisAddIn.cs#2)]  
  
#### <a name="to-generate-a-host-item-for-an-excel-worksheet"></a>Excel çalışma sayfası konak öğesi oluşturmak için  
  
-   Aşağıdaki kod örneğinde, etkin çalışma sayfası konak öğesi projedeki gösterilmiştir.  
  
     [!code-vb[Trin_ExcelAddInDynamicControls#1](../vsto/codesnippet/VisualBasic/trin_exceladdindynamiccontrols4/ThisAddIn.vb#1)]
     [!code-csharp[Trin_ExcelAddInDynamicControls#1](../vsto/codesnippet/CSharp/trin_exceladdindynamiccontrols4/ThisAddIn.cs#1)]  
  
### <a name="generate-listobject-host-controls"></a>ListObject ana bilgisayar denetimleri  
 Kullandığınızda `GetVstoObject` genişletmek için yöntemi bir <xref:Microsoft.Office.Interop.Excel.ListObject>, yöntem bir <xref:Microsoft.Office.Tools.Excel.ListObject>. <xref:Microsoft.Office.Tools.Excel.ListObject> Tüm özellikleri özgün sahip <xref:Microsoft.Office.Interop.Excel.ListObject>. Ayrıca, ek bir işlevselliğe sahiptir ve verilere Windows Forms veri bağlama modelini kullanarak bağlanabilir. Daha fazla bilgi için bkz: [ListObject denetimi](../vsto/listobject-control.md).  
  
#### <a name="to-generate-a-host-control-for-a-listobject"></a>ListObject konak denetimi oluşturmak için  
  
-   Aşağıdaki kod örneğinde nasıl oluşturulacağını gösteren bir <xref:Microsoft.Office.Tools.Excel.ListObject> ilk kez <xref:Microsoft.Office.Interop.Excel.ListObject> projesinde etkin çalışma sayfasında.  
  
     [!code-vb[Trin_ExcelAddInDynamicControls#3](../vsto/codesnippet/VisualBasic/trin_exceladdindynamiccontrols4/ThisAddIn.vb#3)]
     [!code-csharp[Trin_ExcelAddInDynamicControls#3](../vsto/codesnippet/CSharp/trin_exceladdindynamiccontrols4/ThisAddIn.cs#3)]  
  
###  <a name="AddControls"></a> Yönetilen denetimleri belgelere ve çalışma kitaplarına ekleme  
 Oluşturduğunuz sonra bir <xref:Microsoft.Office.Tools.Word.Document> veya <xref:Microsoft.Office.Tools.Excel.Worksheet>bu genişletilmiş çalışma nesneleri temsil etmek veya belgeye denetimleri ekleyebilirsiniz. Denetim eklemek için kullanın `Controls` özelliği <xref:Microsoft.Office.Tools.Word.Document> veya <xref:Microsoft.Office.Tools.Excel.Worksheet>. Daha fazla bilgi için bkz: [Office belgelerine çalışma zamanında denetimler ekleme](../vsto/adding-controls-to-office-documents-at-run-time.md).  
  
 Windows Forms denetimleri ekleme veya *konak denetimlerini*. Bir konak kontrolü tarafından sağlanan bir denetimdir [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] , karşılık gelen bir denetim Word veya Excel birincil birlikte çalışma derlemesindeki sarmalar. Bir konak kontrolü tüm yerel Office nesnesini davranışını kullanıma sunar. Ayrıca, olayları başlatır ve verilere Windows Forms veri bağlama modelini kullanarak bağlanabilir. Daha fazla bilgi için bkz: [konak öğelerini ve konak denetimlerine genel bakış](../vsto/host-items-and-host-controls-overview.md).  
  
> [!NOTE]  
>  Ekleyemezsiniz bir <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> bir çalışma sayfasına denetim veya <xref:Microsoft.Office.Tools.Word.XMLNode> veya <xref:Microsoft.Office.Tools.Word.XMLNodes> denetimini VSTO eklenti kullanarak belgeye. Bu ana bilgisayar denetimleri programlı olarak eklenemez. Daha fazla bilgi için bkz: [konak denetimlerinin ve konak öğelerinin programlama sınırlamaları](../vsto/programmatic-limitations-of-host-items-and-host-controls.md).  
  
### <a name="persist-and-remove-controls"></a>Kalıcı ve denetimleri kaldırma  
 Bir belge ya da çalışma sayfasına yönetilen denetimler eklediğinizde, Belge kaydedildiğinde ve sonra kapalı olduğunda denetimleri kalıcı değildir. Tüm ana bilgisayar denetimleri, böylece yalnızca arka plandaki yerel Office nesneleri geride bıraktığı kaldırılır. Örneğin, bir <xref:Microsoft.Office.Tools.Excel.ListObject> hale bir <xref:Microsoft.Office.Interop.Excel.ListObject>. Tüm Windows Forms denetimleri de kaldırılır, ancak denetimler için ActiveX sarmalayıcıları belgede geride bıraktığı. VSTO eklentinizi içinde Denetimleri'ni temizlemek için ya da belge bir sonraki açılışında denetimleri yeniden oluşturmak için kod eklemeniz gerekir. Daha fazla bilgi için bkz: [Office belgelerinde Dinamik denetimleri kalıcı](../vsto/persisting-dynamic-controls-in-office-documents.md).  
  
## <a name="access-application-level-events-on-documents-and-workbooks"></a>Erişim uygulama düzeyi olaylarına belgeler ve çalışma kitapları  
 Yerel Word ve Excel nesne modelleri bazı belge, çalışma kitabı ve çalışma olayları yalnızca uygulama düzeyinde oluşturulur. Örneğin, <xref:Microsoft.Office.Interop.Word.ApplicationEvents4_Event.DocumentBeforeSave> olayı Word'de belge açıldığında, ancak bu olay tanımlanan <xref:Microsoft.Office.Interop.Word.Application> sınıfı, yerine <xref:Microsoft.Office.Interop.Word.Document> sınıfı.  
  
 VSTO eklentinizi içinde yalnızca yerel Office nesneleri kullandığınızda, bu uygulama düzeyi olayları işlemek ve olayı belge bir özelleştirilmiş olup olmadığını belirlemek için ek kod yazmanız gerekir. Konak öğeleri belirli bir belge için olayları işlemek daha kolay için bu olayları belge düzeyinde sağlar. Bir konak öğesi oluşturmak ve ardından o konak öğesi için olayını işle.  
  
### <a name="example-that-uses-native-word-objects"></a>Yerel Word nesneleri kullanan örnek  
 Aşağıdaki kod örneğinde Word belgeleri için bir uygulama düzeyi olay nasıl ele alınacağını gösterir. `CreateDocument` Yöntemi yeni bir belge oluşturur ve ardından tanımlayan bir <xref:Microsoft.Office.Interop.Word.ApplicationEvents4_Event.DocumentBeforeSave> bu belgenin kaydedilmesini engelleyen olay işleyicisi. Olay için ortaya çıkan bir uygulama düzeyi olaydır <xref:Microsoft.Office.Interop.Word.Application> gerekir nesne ve olay işleyicisi karşılaştırmak `Doc` parametresiyle `document1` belirlemek için nesne `document1` kaydedilmiş belgeyi temsil eder.  
  
 [!code-vb[Trin_WordAddInDynamicControls #12](../vsto/codesnippet/VisualBasic/trin_wordaddindynamiccontrols/ThisAddIn.vb#12)]
 [!code-csharp[Trin_WordAddInDynamicControls#12](../vsto/codesnippet/CSharp/Trin_WordAddInDynamicControls/ThisAddIn.cs#12)]  
  
### <a name="examples-that-use-a-host-item"></a>Konak öğesi kullanan örnekler  
 Aşağıdaki kod örnekleri bu işlem kolaylaştırılmıştır <xref:Microsoft.Office.Tools.Word.Document.BeforeSave> olayı bir <xref:Microsoft.Office.Tools.Word.Document> konak öğesi. `CreateDocument2` Yöntem bu örneklerde oluşturur bir <xref:Microsoft.Office.Tools.Word.Document> genişleten `document2` nesnesi ve ardından tanımlayan bir <xref:Microsoft.Office.Tools.Word.Document.BeforeSave> belgenin kaydedilmesini engelleyen olay işleyicisi. Olay işleyicisi yalnızca çağrılır `document2` kaydedilir ve kaydetme işlemini iptal hangi belgenin kaydedildiğini doğrulamak için ek iş yapmadan olmadan eylem.  
  
 Aşağıdaki kod örneğinde bu görevin nasıl yapılacağı gösterilmektedir.  
  
 [!code-vb[Trin_WordAddInDynamicControls #13](../vsto/codesnippet/VisualBasic/trin_wordaddindynamiccontrols/ThisAddIn.vb#13)]
 [!code-csharp[Trin_WordAddInDynamicControls#13](../vsto/codesnippet/CSharp/Trin_WordAddInDynamicControls/ThisAddIn.cs#13)]  
  
##  <a name="HasVstoObject"></a> Office nesne genişletilmiş olup olmadığını belirleme  
 Genişletilmiş nesne için belirli bir yerel Office nesnesi zaten oluşturulmuş olup olmadığını belirlemek için `HasVstoObject` yöntemi. Bu yöntem **true** genişletilmiş bir nesne zaten oluşturulduysa.  
  
 Kullanım `Globals.Factory.HasVstoMethod` yöntemi. Yerel Word veya Excel nesnesi gibi geçirmek bir <xref:Microsoft.Office.Interop.Word.Document> veya <xref:Microsoft.Office.Interop.Excel.Worksheet>, Genişletilmiş nesne için test etmek istediğiniz.  
  
 `HasVstoObject` Yöntemi, yalnızca belirtilen bir Office nesnesi Genişletilmiş nesne olduğunda kodu çalıştırmak istediğinizde yararlıdır. Örneğin, bir Word VSTO işleyen eklenti varsa <xref:Microsoft.Office.Interop.Word.ApplicationEvents4_Event.DocumentBeforeSave> kaydedilmeden önce yönetilen denetimleri belgeden kaldırmak için kullanmak için olay `HasVstoObject` belge genişletilmiş olup olmadığını belirlemek amacıyla yöntemi. Belge genişletilmemiş, denetimleri yönetilen olamaz ve olay işleyicisi belgede denetimleri temizlemek çalışmadan geri dönebilirsiniz.  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [VSTO eklentilerini programlama](../vsto/programming-vsto-add-ins.md)   
 [Office belgelerine çalışma zamanında denetimler ekleme](../vsto/adding-controls-to-office-documents-at-run-time.md)   
 [Konak öğelerine ve denetimlerine genel bakış](../vsto/host-items-and-host-controls-overview.md)   
 [Office geliştirme örnekleri ve izlenecek yollar](../vsto/office-development-samples-and-walkthroughs.md)  
  
  