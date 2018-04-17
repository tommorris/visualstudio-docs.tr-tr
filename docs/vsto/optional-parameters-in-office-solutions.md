---
title: Office çözümlerinde isteğe bağlı parametreler | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office applications [Office development in Visual Studio], optional parameters
- Visual C# [Office development in Visual Studio], optional parameters
- Visual Basic [Office development in Visual Studio], optional parameters
- application development [Office development in Visual Studio], optional parameters
- missing field [Office development in Visual Studio]
- optional parameters [Office development in Visual Studio]
- parameters [Office development in Visual Studio], optional
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: d417b5126989736c6126ae7c80bfcbc86f336a09
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="optional-parameters-in-office-solutions"></a>Office Çözümlerinde İsteğe Bağlı Parametreler
  Microsoft Office uygulamalarının nesne modelleri yöntemlere birçoğu, isteğe bağlı parametreleri kabul eder. Visual Studio'da Office çözümü geliştirmek için Visual Basic kullanırsanız, her eksik parametre için varsayılan değerleri otomatik olarak kullanıldığından isteğe bağlı parametre için bir değer geçirmek zorunda değildir. Çoğu durumda, Visual C# projelerine isteğe bağlı parametreler atlayabilirsiniz. Ancak, atlayamazsınız **ref** parametrelerinin `ThisDocument` belge düzeyi Word projeleri sınıfta.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
 Visual C# ve Visual Basic projelerinde isteğe bağlı parametreler ile çalışma hakkında daha fazla bilgi için bkz: [adlandırılmış ve isteğe bağlı bağımsız değişkenler &#40;C&#35; Programlama Kılavuzu&#41; ](/dotnet/csharp/programming-guide/classes-and-structs/named-and-optional-arguments) ve [isteğe bağlı parametreler &#40;Visual Basic&#41;](/dotnet/visual-basic/programming-guide/language-features/procedures/optional-parameters).  
  
> [!NOTE]  
>  Visual Studio'nun önceki sürümleri, Visual C# projelerinde her isteğe bağlı bir parametre için bir değer geçmesi gerekir. Kolaylık olması için bu projeler adlı bir genel değişkeni dahil `missing` parametresinin varsayılan değeri kullanmak istediğinizde isteğe bağlı bir parametre geçirebilirsiniz. Visual Studio'da Office için Visual C# projeleri hala dahil `missing` değişkeni, ancak genellikle gerekmez Office çözümleri geliştirirken kullanmak [!INCLUDE[vs_dev12](../vsto/includes/vs-dev12-md.md)], isteğe bağlı yöntemlerini çağırdığınızda dışında **ref** Parametrelerde `ThisDocument` Word için belge düzeyi projelerine sınıfı.  
  
## <a name="example-in-excel"></a>Excel'de bir örnek  
 <xref:Microsoft.Office.Tools.Excel.Worksheet.CheckSpelling%2A> Yöntemi birçok isteğe bağlı parametreye sahiptir. Bazı parametrelerin değerlerini belirtin ve aşağıdaki kod örneğinde gösterildiği gibi diğer varsayılan değerini kabul edin. Bu örnek bir belge düzeyi projesi adlı bir çalışma sayfası sınıfıyla birlikte gerektirir `Sheet1`.  
  
 [!code-csharp[Trin_VstrefGeneralExcel#1](../vsto/codesnippet/CSharp/excelworkbook1/Sheet1.cs#1)]
 [!code-vb[Trin_VstrefGeneralExcel#1](../vsto/codesnippet/VisualBasic/excelworkbook1/Sheet1.vb#1)]  
  
## <a name="example-in-word"></a>Word'de bir örnek  
 <xref:Microsoft.Office.Interop.Word.Find.Execute%2A> Yöntemi birçok isteğe bağlı parametreye sahiptir. Bazı parametrelerin değerlerini belirtin ve aşağıdaki kod örneğinde gösterildiği gibi diğer varsayılan değerini kabul edin.  
  
 [!code-vb[Trin_VstrefGeneralWord#1](../vsto/codesnippet/VisualBasic/worddocument1/ThisDocument.vb#1)]
 [!code-csharp[Trin_VstrefGeneralWord#1](../vsto/codesnippet/CSharp/worddocument1/ThisDocument.cs#1)]  
  
## <a name="using-optional-parameters-of-methods-in-the-thisdocument-class-in-visual-c-document-level-projects-for-word"></a>Visual C# belge düzeyi projelerine ThisDocument sınıfı yöntemlerinin isteğe bağlı parametreler için Word kullanılarak  
 Word nesne modeli isteğe bağlı olan birçok yöntem içerir **ref** kabul parametreleri <xref:System.Object> değerleri. Ancak, atlayamazsınız **ref** oluşturulan yöntemlerinin parametrelerinin `ThisDocument` Word için belge düzeyi projelerine Visual C# sınıfı. Visual C# sağlar, isteğe bağlı atlamak **ref** yalnızca arabirimleri, yöntemlerinin parametrelerini sınıfların değil. Atlayamazsınız çünkü Örneğin, aşağıdaki kod örneğinde, derlenmiyor **ref** parametrelerinin <xref:Microsoft.Office.Tools.Word.DocumentBase.CheckSpelling%2A> yöntemi `ThisDocument` sınıfı.  
  
 [!code-csharp[Trin_VstrefGeneralWord#3](../vsto/codesnippet/CSharp/worddocument1/ThisDocument.cs#3)]  
  
 Yöntemlerini çağırdığınızda `ThisDocument` sınıfında, aşağıdaki yönergeleri izleyin:  
  
-   İsteğe bağlı varsayılan değerini kabul etmek için **ref** parametresi, geçişi `missing` değişken parametre. `missing` Değişkeni Visual C# Office projelerinde otomatik olarak tanımlanır ve değer atanmış <xref:System.Type.Missing> oluşturulan proje kodu.  
  
-   İsteğe bağlı bir kendi değeri belirtmek için **ref** parametresini belirtmek istediğiniz değer atanmış bir nesne bildirme ve nesneyi parametresine geçirin.  
  
 Aşağıdaki kod örneğinde nasıl çağırılacağını <xref:Microsoft.Office.Tools.Word.DocumentBase.CheckSpelling%2A> yöntemi için bir değer belirterek *ignoreUppercase* parametre ve diğer parametreler için varsayılan değeri kabul etme.  
  
 [!code-csharp[Trin_VstrefGeneralWord#4](../vsto/codesnippet/CSharp/worddocument1/ThisDocument.cs#4)]  
  
 İsteğe bağlı atlayarak kod yazmak istiyorsanız **ref** bir yöntemin parametre `ThisDocument` sınıfı, alternatif olarak çağırabilirsiniz aynı yöntemi üzerinde <xref:Microsoft.Office.Interop.Word.Document> tarafından döndürülen nesne <xref:Microsoft.Office.Tools.Word.Document.InnerObject%2A> özelliği ve atlayın Bu yöntem parametrelerinden. Çünkü bunu yapabilirsiniz <xref:Microsoft.Office.Interop.Word.Document> bir sınıf yerine bir arabirim değil.  
  
 [!code-csharp[Trin_VstrefGeneralWord#5](../vsto/codesnippet/CSharp/worddocument1/ThisDocument.cs#5)]  
  
 Değer ve başvuru türü parametreleri hakkında daha fazla bilgi için bkz: [geçirme bağımsız değişkenleri değere ve başvuruya göre &#40;Visual Basic&#41; ](/dotnet/visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference) (Visual Basic için) ve [geçirme parametreleri &#40;C&#35; Programlama Kılavuzu&#41;](/dotnet/csharp/programming-guide/classes-and-structs/passing-parameters).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Office çözümleri geliştirme](../vsto/developing-office-solutions.md)   
 [Office Çözümlerinde Kod Yazma](../vsto/writing-code-in-office-solutions.md)  
  
  