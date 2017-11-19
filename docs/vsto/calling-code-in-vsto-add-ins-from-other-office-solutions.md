---
title: "VSTO eklentilerinde diğer Office Çözümlerinden kod çağırma | Microsoft Docs"
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
- VBA [Office development in Visual Studio], calling code in application-level add-ins
- application-level add-ins [Office development in Visual Studio], calling code from other solutions
- calling add-in code
- add-ins [Office development in Visual Studio], calling code from other solutions
- interoperability [Office development in Visual Studio]
- calling code from VBA
ms.assetid: c1f16b4c-9291-49ed-9694-a83a37109612
caps.latest.revision: "54"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 38508a664ff94628dfd3fd5ec00eacb32fbb1187
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="calling-code-in-vsto-add-ins-from-other-office-solutions"></a>VSTO Eklentilerinde Diğer Office Çözümlerinden Kod Çağırma
  VSTO eklentinizi diğer Microsoft Office çözümleri dahil olmak üzere diğer çözümleri için de bir nesne getirebilir. VSTO eklentinizi diğer çözümlerin kullanması için etkinleştirmek istediğiniz bir hizmet sağlarsa, bu yararlıdır. Bir Web hizmetinden finansal verileri hesaplamalar gerçekleştirir. Microsoft Office Excel için VSTO eklenti varsa, örneğin, diğer çözümleri bu hesaplamalar çağırarak Excel VSTO eklenti çalışma zamanında gerçekleştirebilirsiniz.  
  
 [!INCLUDE[appliesto_allapp](../vsto/includes/appliesto-allapp-md.md)]  
  
 Bu işlemde iki ana adım vardır:  
  
-   VSTO eklentinizi içinde diğer çözümleri nesneye kullanıma sunar.  
  
-   Başka bir çözümde, VSTO eklenti ve nesne araması üyeleri tarafından oluşturulan nesneye erişin.  
  
## <a name="types-of-solutions-that-can-call-code-in-an-add-in"></a>Tür bir eklentilerinde kod çağırabilir çözümler  
 VSTO eklenti çözümleri aşağıdaki türden bir nesnesinde getirebilir:  
  
-   Visual Basic for Applications (VBA) kodu aynı uygulama işleminde VSTO eklentinizi olarak yüklenen bir belgedeki.  
  
-   Aynı uygulama işleminde VSTO eklentinizi yüklenen belge düzeyi özelleştirmeleri.  
  
-   Diğer VSTO Visual Studio'da Office proje şablonları kullanılarak oluşturulmuş eklentileri.  
  
-   COM VSTO eklentileri (diğer bir deyişle, VSTO uygulayan eklentileri <xref:Extensibility.IDTExtensibility2> doğrudan arabirim).  
  
-   VSTO eklentinizi daha farklı bir işlemde çalışan herhangi bir çözümü (Bu tür çözümler olarak da adlandırılır *işlem dışı istemciler*). Bunlar, bir Windows Forms veya konsol uygulamasını ve VSTO farklı bir işlem içinde yüklenen eklentileri gibi bir Office uygulaması otomatikleştirmek uygulamaları içerir.  
  
## <a name="exposing-objects-to-other-solutions"></a>Diğer çözümleri nesnelerini gösterme  
 VSTO eklentinizi diğer çözümleri için bir nesnesinde kullanıma sunmak için VSTO eklentinizi aşağıdaki adımları gerçekleştirin:  
  
1.  Diğer çözümlerde oluşturmak istediğiniz bir sınıf tanımlayın.  
  
2.  Geçersiz kılma <xref:Microsoft.Office.Tools.AddInBase.RequestComAddInAutomationService%2A> yönteminde `ThisAddIn` sınıfı. Diğer çözümleri kullanıma sunmak istediğiniz sınıfının bir örneğini döndürür.  
  
### <a name="defining-the-class-you-want-to-expose-to-other-solutions"></a>Diğer çözümlerde oluşturmak istediğiniz sınıfı tanımlama  
 En azından kullanıma sunmak istediğiniz sınıfı ortak olmalıdır, gerekir <xref:System.Runtime.InteropServices.ComVisibleAttribute> özniteliğini **true**, ve kullanıma gerekir [IDispatch](https://msdn.microsoft.com/library/windows/desktop/ms221608.aspx) arabirimi.  
  
 Kullanıma sunmak için önerilen yöntem [IDispatch](https://msdn.microsoft.com/library/windows/desktop/ms221608.aspx) arabirimidir aşağıdaki adımları gerçekleştirmek için:  
  
1.  Diğer çözümleri kullanıma sunmak istediğiniz üyeleri bildiren bir arabirim tanımlayın. Bu arabirim, VSTO eklenti projenizde tanımlayabilirsiniz. Ancak, VSTO eklentinizi çağrı çözümleri VSTO Eklenti projenizi başvurulmadan arabirimi başvurabilmek VBA olmayan çözümlerine sınıfı kullanıma sunmak istiyorsanız, bu arabirim ayrı sınıf kitaplığında tanımlamak isteyebilirsiniz.  
  
2.  Uygulama <xref:System.Runtime.InteropServices.ComVisibleAttribute> özniteliği bu arabirime ve bu öznitelik ayarlanırsa **doğru**.  
  
3.  Bu arabirim uygulamak için sınıfınızı değiştirin.  
  
4.  Uygulama <xref:System.Runtime.InteropServices.ClassInterfaceAttribute> özniteliği sınıfınıza ve bu özniteliği None olarak ayarlanmış değerini <xref:System.Runtime.InteropServices.ClassInterfaceType> numaralandırması.  
  
5.  İşlem dışı istemciler sınıfına kullanıma sunmak istiyorsanız, aşağıdakileri yapmanız gerekebilir:  
  
    -   Sınıfından türetilen <xref:System.Runtime.InteropServices.StandardOleMarshalObject>. Daha fazla bilgi için bkz: [gösterme sınıfları işlem dışı istemcilere](#outofproc).  
  
    -   Ayarlama **kaydetmek için COM birlikte çalışma** arabirimi tanımladığınız yerlerde projesinde özelliği. Bu seçenek, yalnızca istemcilerin VSTO eklenti çağırmak için erken bağlama kullanmasını etkinleştirmek istiyorsanız gereklidir.  
  
 Aşağıdaki kod örneğinde gösteren bir `AddInUtilities` ile sınıf bir `ImportData` diğer çözümleri tarafından çağrılan yöntemi. Bu kodu daha geniş bir anlatım bağlamında görmek için bkz: [izlenecek yol: eklentide bir VSTO VBA'dan Kod Çağırma](../vsto/walkthrough-calling-code-in-a-vsto-add-in-from-vba.md).  
  
 [!code-csharp[Trin_AddInInteropWalkthrough#3](../vsto/codesnippet/CSharp/Trin_AddInInteropWalkthrough/AddInUtilities.cs#3)]
 [!code-vb[Trin_AddInInteropWalkthrough#3](../vsto/codesnippet/VisualBasic/Trin_AddInInteropWalkthrough/AddInUtilities.vb#3)]  
  
### <a name="exposing-classes-to-vba"></a>VBA sınıfları gösterme  
 Yukarıda verilen adımları gerçekleştirdiğinizde, VBA kodu arabiriminde bildirdiğiniz yöntemleri çağırabilir. VBA kodu sınıfınızın temel sınıflardan gibi edinir yöntemleri de dahil olmak üzere sınıfınızda diğer yöntemleri çağıramaz <xref:System.Object>.  
  
 Bunun yerine getirebilir [IDispatch](https://msdn.microsoft.com/library/windows/desktop/ms221608.aspx) ayarlayarak arabirimi <xref:System.Runtime.InteropServices.ClassInterfaceAttribute> özniteliği AutoDispatch ya AutoDual değerine <xref:System.Runtime.InteropServices.ClassInterfaceType> numaralandırması. Bunu yaparsanız, ayrı bir arabirim yöntemleri bildirme gerekmez. VBA kodu gibi temel sınıflardan elde edilen yöntemler de dahil olmak üzere sınıfınızda herhangi bir ortak ve statik olmayan yöntem ancak çağırabilir <xref:System.Object>. Ayrıca, erken bağlama kullanan işlem dışı istemciler sınıfınız çağrılamaz.  
  
###  <a name="outofproc"></a>İşlem dışı istemcilere sınıfları gösterme  
 VSTO eklentinizi işlem dışı istemcilere bir sınıfta kullanıma sunmak istiyorsanız, sınıfından türetilmelidir <xref:System.Runtime.InteropServices.StandardOleMarshalObject> işlem dışı istemciler VSTO eklenti nesnenizin çağırabilirsiniz emin olmak için. Aksi takdirde, nesnenizin örneği bir işlem dışı istemcisinde almanın girişimleri beklenmedik şekilde başarısız olabilir.  
  
 Bir Office uygulamasının nesne modeline tüm çağrıları ana UI iş parçacığında yapılması gerekir, ancak bir işlem dışı istemcisinden gelen çağrıları nesnenize rasgele bir RPC (uzak yordam çağrısı) parçacığında ulaşır budur. .NET Framework'teki COM hazırlama mekanizması iş parçacığı geçiş yapmaz ve bunun yerine ana kullanıcı Arabirimi iş parçacığı yerine gelen RPC iş nesnenize çağrısı hazırlamak çalışır. Nesnenizin türeyen bir sınıf örneği olup olmadığını <xref:System.Runtime.InteropServices.StandardOleMarshalObject>, nesnenize gelen çağrıları otomatik olarak konak uygulamanın ana kullanıcı Arabirimi iş parçacığı olacağı sunulan nesnenin oluşturulduğu, iş parçacığına sıralanmış.  
  
 Office çözümlerinde iş parçacığı kullanma hakkında daha fazla bilgi için bkz: [Office iş parçacığı oluşturma desteği](../vsto/threading-support-in-office.md).  
  
### <a name="overriding-the-requestcomaddinautomationservice-method"></a>RequestComAddInAutomationService yöntemini geçersiz kılma  
 Aşağıdaki kod örneğinde nasıl geçersiz kılınacağı gösterilmektedir <xref:Microsoft.Office.Tools.AddInBase.RequestComAddInAutomationService%2A> içinde `ThisAddIn` VSTO eklentinizi sınıfta. Bu örnekte adlı bir sınıf tanımladığınız varsayılır `AddInUtilities` diğer çözümlerde oluşturmak istediğiniz. Bu kodu daha geniş bir anlatım bağlamında görmek için bkz: [izlenecek yol: eklentide bir VSTO VBA'dan Kod Çağırma](../vsto/walkthrough-calling-code-in-a-vsto-add-in-from-vba.md).  
  
 [!code-csharp[Trin_AddInInteropWalkthrough#1](../vsto/codesnippet/CSharp/Trin_AddInInteropWalkthrough/ThisAddIn.cs#1)]
 [!code-vb[Trin_AddInInteropWalkthrough#1](../vsto/codesnippet/VisualBasic/Trin_AddInInteropWalkthrough/ThisAddIn.vb#1)]  
  
 VSTO eklentinizi yüklendiğinde, [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] çağrıları <xref:Microsoft.Office.Tools.AddInBase.RequestComAddInAutomationService%2A> yöntemi. Çalışma zamanı döndürülen nesneyi atar <xref:Microsoft.Office.Core.COMAddIn.Object%2A> özelliği bir <xref:Microsoft.Office.Core.COMAddIn> VSTO eklentinizi temsil eden nesne. Bu <xref:Microsoft.Office.Core.COMAddIn> nesnesidir diğer Office çözümleri ve Office otomatikleştirmek çözümleri için kullanılabilir.  
  
## <a name="accessing-objects-from-other-solutions"></a>Diğer çözümlerden nesnelere erişme  
 VSTO eklentinizi içinde sunulan nesne çağırmak için istemci çözümde aşağıdaki adımları gerçekleştirin:  
  
1.  Alma <xref:Microsoft.Office.Core.COMAddIn> gösterilen için VSTO eklentisi temsil eden nesne. İstemciler tüm kullanılabilir VSTO Eklentileri Office uygulama konağının nesne modelinde Application.COMAddIns özelliğini kullanarak erişebilirsiniz.  
  
2.  Erişim <xref:Microsoft.Office.Core.COMAddIn.Object%2A> özelliği <xref:Microsoft.Office.Core.COMAddIn> nesnesi. Bu özellik, VSTO eklentiden gösterilen nesnesini döndürür.  
  
3.  Sunulan nesnenin üyelerine çağırın.  
  
 Dönüş değerini kullanacak şekilde <xref:Microsoft.Office.Core.COMAddIn.Object%2A> özelliği, VBA ve VBA olmayan istemciler için farklıdır. İşlem dışı istemciler için bir olası yarış durumu önlemek ek kod gereklidir.  
  
### <a name="accessing-objects-from-vba-solutions"></a>VBA çözümlerinden nesnelere erişme  
 Aşağıdaki kod örneğinde VBA VSTO eklenti tarafından sunulan bir yöntemi çağırmak için nasıl kullanılacağı gösterilmektedir. Bu VBA makrosu adlı bir yöntemi çağırır `ImportData` VSTO adlı eklenti içinde tanımlanan **ExcelImportData**. Bu kodu daha geniş bir anlatım bağlamında görmek için bkz: [izlenecek yol: eklentide bir VSTO VBA'dan Kod Çağırma](../vsto/walkthrough-calling-code-in-a-vsto-add-in-from-vba.md).  
  
```  
Sub CallVSTOMethod()  
    Dim addIn As COMAddIn  
    Dim automationObject As Object  
    Set addIn = Application.COMAddIns("ExcelImportData")  
    Set automationObject = addIn.Object  
    automationObject.ImportData  
End Sub  
```  
  
### <a name="accessing-objects-from-non-vba-solutions"></a>VBA olmayan çözümlerden nesnelere erişme  
 VBA olmayan çözümde dönüştürmeniz gerekir <xref:Microsoft.Office.Core.COMAddIn.Object%2A> özellik değerini arabirimine onu uygular ve ardından arayüz nesnesi üzerinde gösterilen yöntemleri çağırabilirsiniz. Aşağıdaki kod örneğinde nasıl çağırılacağını `ImportData` bir farklı VSTO Visual Studio'da Office geliştirici araçları kullanılarak oluşturulmuş eklenti yönteminden.  
  
```vb  
Dim addIn As Office.COMAddIn = Globals.ThisAddIn.Application.COMAddIns.Item("ExcelImportData")  
Dim utilities As ExcelImportData.IAddInUtilities = TryCast( _  
    addIn.Object, ExcelImportData.IAddInUtilities)  
utilities.ImportData()  
```  
  
```csharp  
object addInName = "ExcelImportData";  
Office.COMAddIn addIn = Globals.ThisAddIn.Application.COMAddIns.Item(ref addInName);  
ExcelImportData.IAddInUtilities utilities = (ExcelImportData.IAddInUtilities)addIn.Object;  
utilities.ImportData();  
```  
  
 Değerini cast çalışırsanız, bu örnekte, <xref:Microsoft.Office.Core.COMAddIn.Object%2A> özelliğine `AddInUtilities` sınıfı yerine `IAddInUtilities` kodu arabirimi, throw bir <xref:System.InvalidCastException>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [VSTO eklentilerini programlama](../vsto/programming-vsto-add-ins.md)   
 [İzlenecek yol: Bir VSTO eklentisinde VBA'dan kod çağırma](../vsto/walkthrough-calling-code-in-a-vsto-add-in-from-vba.md)   
 [Office çözümleri geliştirme](../vsto/developing-office-solutions.md)   
 [Nasıl yapılır: Visual Studio'da Office projeleri oluşturma](../vsto/how-to-create-office-projects-in-visual-studio.md)   
 [VSTO eklentileri mimarisi](../vsto/architecture-of-vsto-add-ins.md)   
 [Genişletilebilirlik arabirimlerini kullanarak kullanıcı Arabirimi özelliklerini özelleştirme](../vsto/customizing-ui-features-by-using-extensibility-interfaces.md)  
  
  