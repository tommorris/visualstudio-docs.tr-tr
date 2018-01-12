---
title: "VBA ve belge düzeyi özelleştirmelerini birleştirme | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VST.VBAInterop.InvalidAssemblyVersion
- VST.VBAInterop.ProjectLoadFailure
- VST.VBAInterop.MissingGUID
- VST.VBAInterop.EnableComCallers
- VST.VBAInterop.PersistVBACode
- VST.VBAInterop.ReferenceAssemblyFromVBA
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- documents [Office development in Visual Studio], Visual Basic for Applications and
- VBA [Office development in Visual Studio]
- Office documents [Office development in Visual Studio], Visual Basic for Applications and
- VBA [Office development in Visual Studio], about VBA and document-level customizations
- managed code [Office development in Visual Studio], Visual Basic for Applications and
- document-level customizations [Office development in Visual Studio], Visual Basic for Applications and
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 63f316d3ac6fefbef37735cddc8fb7a87a8d4bfb
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="combining-vba-and-document-level-customizations"></a>VBA ve Belge Düzeyi Özelleştirmelerini Birleştirme
  Visual Basic for Applications (VBA) kodunu Microsoft Office Word veya Microsoft Office Excel için belge düzeyi özelleştirme parçası olan bir belgedeki kullanabilirsiniz. VBA kodu özelleştirme derlemesinden belgede çağırabilir veya özelleştirme derlemesindeki kodu çağırmak için belgedeki VBA kodu etkinleştirmek için projenizi yapılandırabilirsiniz.  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
## <a name="behavior-of-vba-code-in-a-document-level-customization"></a>Belge düzeyi özelleştirmelerinde VBA kodunun davranışı  
 Visual Studio, projenizin açtığınızda, belge tasarım modunda açılır. VBA kodu çalıştırmadan belge ve kod çalışabilmeniz için belge tasarım modunda olduğunda VBA kodu çalışmaz.  
  
 Çözümü çalıştırdığınızda, belgede çıkarılan olayları olay işleyicileri VBA ve özelleştirme derlemesini seçin ve her iki kod kümesi çalıştırın. Hangi kodu önce diğer çalıştıracak önceden belirleyemiyor; Bu, tek tek her durumda sınama aracılığıyla belirlemelisiniz. İki kod kümesi dikkatli bir biçimde düzenlenir ve test beklenmeyen sonuçlar alabilirsiniz.  
  
## <a name="calling-vba-code-from-the-customization-assembly"></a>Özelleştirme Derlemesinden VBA kodu çağırma  
 Word belgelerinde makroları çağırabilir ve Excel çalışma kitaplarını makroları ve işlevleri çağırabilir. Bunu yapmak için aşağıdaki yöntemlerden birini kullanın:  
  
-   Word için çağrı <xref:Microsoft.Office.Interop.Word._Application.Run%2A>yöntemi <xref:Microsoft.Office.Interop.Word.Application> sınıfı.  
  
-   Excel için çağrı <xref:Microsoft.Office.Interop.Excel._Application.Run%2A> yöntemi <xref:Microsoft.Office.Interop.Excel.Application> sınıfı.  
  
 Her bir yöntemin ilk parametre makrosu veya aramak istediğiniz işlevi adını tanımlar ve diğer isteğe bağlı parametreler makro veya işlev parametreleri belirtin. Word ve Excel için ilk parametre farklı biçimlerde olabilir:  
  
-   Word için ilk parametre şablonunu, modül ve makro adı herhangi bir bileşimi olabilir bir dizedir. Belge adı belirtirseniz, kodunuzu yalnızca makroları geçerli bağlamla ilgili belgelerdeki çalıştırabilirsiniz — herhangi bir belgede yalnızca hiçbir makrosu.  
  
-   Excel için ilk parametre makro adını belirten bir dize olabilir bir <xref:Microsoft.Office.Interop.Excel.Range> işlevi olduğu veya kayıtlı DLL (XLL) işlevi için bir kayıt kimliği gösterir. Bir dize geçirirseniz, dize etkin çalışma sayfasının bağlamı değerlendirilir.  
  
 Aşağıdaki kod örneğinde adlı makro çağırmaya gösterilmiştir `MyMacro` Excel için belge düzeyi projesindeki. Bu örnek varsayar `MyMacro` tanımlanan `Sheet1`.  
  
```vb  
Globals.Sheet1.Application.Run("MyMacro")  
```  
  
```csharp  
Globals.Sheet1.Application.Run("MyMacro", missing, missing, missing,  
    missing, missing, missing, missing, missing, missing, missing,  
    missing, missing, missing, missing, missing, missing, missing,  
    missing, missing, missing, missing, missing, missing, missing,   
    missing, missing, missing, missing, missing, missing);  
```  
  
> [!NOTE]  
>  Genel kullanma hakkında bilgi için `missing` değişkeni isteğe bağlı parametreler Visual C# ' ta, yerine bkz [Office çözümlerinde kod yazma](../vsto/writing-code-in-office-solutions.md).  
  
## <a name="calling-code-in-document-level-customizations-from-vba"></a>Belge düzeyi özelleştirmelerinde VBA'dan Kod Çağırma  
 Visual Basic for Applications (VBA) kodunu belgedeki özelleştirme derlemesindeki kodu çağırmak için Word veya Excel için belge düzeyi projesi yapılandırabilirsiniz. Aşağıdaki senaryolarda kullanışlıdır:  
  
-   Varolan VBA kodu bir belgede aynı belge ile ilişkili bir belge düzeyi özelleştirme özelliklerini kullanarak genişletmek ister.  
  
-   Geliştirdiğiniz Hizmetleri belge düzeyi özelleştirmelerinde erişebilen Hizmetleri belgede VBA kodu yazarak son kullanıcıların kullanımına istiyor.  
  
 Visual Studio'da Office geliştirme araçları VSTO eklentileri için benzer bir özellik sağlar. Bir VSTO eklentisi geliştiriyorsanız, kod VSTO eklentinizi diğer Microsoft Office Çözümlerinden çağırabilirsiniz. Daha fazla bilgi için bkz: [VSTO eklentileri diğer Office Çözümlerinden gelen çağırma kodda](../vsto/calling-code-in-vsto-add-ins-from-other-office-solutions.md).  
  
> [!NOTE]  
>  Bu özellik Word şablon projelerinde kullanılamaz. Yalnızca Word belgesi, Excel çalışma kitabı veya Excel Şablonu proje kullanılabilir.  
  
## <a name="requirements"></a>Gereksinimler  
 VBA kodu özelleştirme derlemesini çağırmak etkinleştirmeden önce projeniz aşağıdaki gereksinimleri karşılaması gerekir:  
  
-   Belge aşağıdaki dosya adı uzantılarını birine sahip olmalıdır:  
  
    -   Word: .docm veya .doc  
  
    -   Excel: .xlsm, .xltm, .xls veya .xlt  
  
-   Belge zaten VBA kodu içeren bir VBA projesi içermelidir.  
  
-   VBA kodu belgedeki makroları kullanıcıya sormadan çalışmasına izin gerekir. Office proje konumunu Word veya Excel Güven Merkezi ayarlarında güvenilir konumlar listesine ekleyerek çalıştırmak için VBA kodu güvenebilirsiniz.  
  
-   Office proje için VBA gösterme bir veya daha fazla ortak üyeyi içeren en az bir ortak sınıfı içermelidir.  
  
     Yöntemler, özellikler ve olayları VBA getirebilir. Bir konak öğesi sınıfı, kullanıma sınıfı olabilir (gibi `ThisDocument` Word için veya `ThisWorkbook` ve `Sheet1` Excel için) veya projenizde tanımladığınız başka bir sınıf. Konak öğeleri hakkında daha fazla bilgi için bkz: [konak öğelerine ve denetimlerine genel bakış](../vsto/host-items-and-host-controls-overview.md).  
  
## <a name="enabling-vba-code-to-call-into-the-customization-assembly"></a>VBA kodu özelleştirme derlemesini çağırmak etkinleştirme  
 Belgedeki VBA kodu özelleştirme derlemeye üyelerinde getirebilir iki farklı yolu vardır:  
  
-   Bir konak öğesi sınıfında üyeleri getirebilir bir [!INCLUDE[vbprvb](../sharepoint/includes/vbprvb-md.md)] VBA projesi. Bunu yapmak için ayarlayın **EnableVbaCallers** konak öğesi özelliği **True** içinde **özellikleri** penceresi sırasında (diğer bir deyişle, belge, çalışma sayfası veya çalışma kitabı) konak öğesi tasarımcısında açın. Visual Studio otomatik olarak sınıf üyeleri çağırmak VBA kodu etkinleştirmek için gereken çalışma gerçekleştirir.  
  
-   Visual C# projesinde herhangi bir ortak sınıf üyeleri getirebilir veya konak olmayan üyeler sınıfta öğesi bir [!INCLUDE[vbprvb](../sharepoint/includes/vbprvb-md.md)] VBA projesi. Bu seçenek için VBA kullanımına sunma hangi sınıfların seçmek için özgürlüğü sağlar, ancak aynı zamanda daha fazla el ile adımlar gerektirir.  
  
     Bunu yapmak için aşağıdaki ana adımları gerçekleştirmeniz gerekir:  
  
    1.  COM sınıfına kullanıma sunma  
  
    2.  Geçersiz kılma **GetAutomationObject** gösterme sınıfının bir örneğini dönmek için projenizdeki konak öğesi sınıfının yöntemi.  
  
    3.  Ayarlama **ReferenceAssemblyFromVbaProject** projeye tüm konak öğesi sınıfında özelliğinin **doğru**. Bu özelleştirme derlemesinin tür kitaplığını derlemeye katıştırır ve belgedeki VBA projesine türü kitaplığına bir başvuru ekler.  
  
 Ayrıntılı yönergeler için bkz [nasıl yapılır: Visual Basic projesinde VBA'ya kodu kullanıma](../vsto/how-to-expose-code-to-vba-in-a-visual-basic-project.md) ve [nasıl yapılır: Visual C &#35; VBA'ya kodu kullanıma Proje](../vsto/how-to-expose-code-to-vba-in-a-visual-csharp-project.md).  
  
 **EnableVbaCallers** ve **ReferenceAssemblyFromVbaProject** özellikleri yalnızca **özellikleri** penceresi tasarım zamanında; çalışma zamanında kullanılamaz . Özelliklerini görüntülemek için bir konak öğesi için tasarımcıyı açın [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]. Bu özellikleri ayarladığınızda, Visual Studio gerçekleştiren belirli görevler hakkında daha fazla bilgi için bkz: [konak öğesi özellikleri tarafından gerçekleştirilen görevler](#PropertyTasks).  
  
> [!NOTE]  
>  Çalışma kitabı veya belge VBA kodu zaten içermiyor veya belgedeki VBA kodu çalıştırmak için güvenilir değilse, ayarlarken bir hata iletisi alırsınız **EnableVbaCallers** veya **ReferenceAssemblyFromVbaProject**  özelliğine **doğru**. Bu durum, bu durumda belgedeki VBA projesini Visual Studio değiştirilemiyor çünkü.  
  
## <a name="using-members-in-vba-code-to-call-into-the-customization-assembly"></a>Üyeleri özelleştirme derlemesini çağırmak için VBA kod içinde kullanma  
 VBA kodu özelleştirme derlemesini çağırmak etkinleştirmek için projenizi yapılandırdıktan sonra Visual Studio aşağıdaki üyeleri belgedeki VBA projesine ekler:  
  
-   Tüm projeleri için Visual Studio adlı genel bir yöntem ekler `GetManagedClass`.  
  
-   İçin [!INCLUDE[vbprvb](../sharepoint/includes/vbprvb-md.md)] bir ana bilgisayar üyeleri kullanıma projeleri öğe sınıfı kullanarak **EnableVbaCallers** özelliği, Visual Studio ayrıca adlı bir özellik ekler `CallVSTOAssembly` için `ThisDocument`, `ThisWorkbook`, `Sheet1`, `Sheet2`, veya `Sheet3` VBA projesinde modülü.  
  
 Kullanabileceğiniz `CallVSTOAssembly` özelliği veya `GetManagedClass` projesinde kodu VBA maruz sınıfın ortak üyelerine erişim yöntemi.  
  
> [!NOTE]  
>  Geliştirmek ve çözümünüzü dağıtmak olsa da vardır belgenin birçok kopyası VBA kodu nereye ekleyebilirsiniz. Daha fazla bilgi için bkz: [VBA kod belge ekleme yönergeleri](#Guidelines).  
  
### <a name="using-the-callvstoassembly-property-in-a-visual-basic-project"></a>Visual Basic projesinde CallVSTOAssembly özelliğini kullanma  
 Kullanım `CallVSTOAssembly` konak öğesi sınıfına eklediğiniz ortak üyelere erişmek için özellik. Örneğin, aşağıdaki VBA makrosu adlı bir yöntemi çağırır `MyVSTOMethod` içinde tanımlanan `Sheet1` Excel çalışma kitabı projesinde sınıfı.  
  
```  
Sub MyMacro()  
    Sheet1.CallVSTOAssembly.MyVSTOMethod()  
End Sub  
```  
  
 Bu özelliği kullanmaktan özelleştirme derlemesini çağırmak için daha uygun bir yoludur `GetManagedClass` doğrudan yöntemi. `CallVSTOAssembly`konak temsil eden bir nesne oluşturduğunuz öğe sınıfı için VBA döndürür. Döndürülen nesnenin yöntem parametreleri ve üyeleri IntelliSense içinde görüntülenir.  
  
 `CallVSTOAssembly` Özelliği aşağıdaki kodu benzer bir bildirime sahiptir. Bu kod, oluşturduğunuz varsayılır `Sheet1` konak adında bir Excel çalışma kitabı proje öğesi sınıfını `ExcelWorkbook1` VBA.  
  
```  
Property Get CallVSTOAssembly() As ExcelWorkbook1.Sheet1  
    Set CallVSTOAssembly = GetManagedClass(Me)  
End Property  
```  
  
### <a name="using-the-getmanagedclass-method"></a>GetManagedClass yöntemini kullanma  
 Genel kullanılacak `GetManagedClass` yöntemi, geçersiz kılınmış halini içeren konak öğesi sınıfı karşılık gelen VBA nesnesindeki geçişine **GetAutomationObject** yöntemi. Ardından, döndürülen nesne VBA için kullanıma sunulan sınıfa erişmek için kullanın.  
  
 Örneğin, aşağıdaki VBA makrosu adlı bir yöntemi çağırır `MyVSTOMethod` içinde tanımlanan `Sheet1` konak adında bir Excel çalışma kitabı proje öğesi sınıfını `ExcelWorkbook1`.  
  
```  
Sub CallVSTOMethod  
    Dim VSTOSheet1 As ExcelWorkbook1.Sheet1  
    Set VSTOSheet1 = GetManagedClass(Sheet1)  
    VSTOSheet1.MyVSTOMethod  
End Sub  
```  
  
 `GetManagedClass` Yöntemi aşağıdaki bildirime sahiptir.  
  
```  
GetManagedClass(pdispInteropObject Object) As Object  
```  
  
 Bu yöntem, kullanıma sunulan sınıfı için VBA temsil eden bir nesne döndürür. Döndürülen nesnenin yöntem parametreleri ve üyeleri IntelliSense içinde görüntülenir.  
  
##  <a name="Guidelines"></a>VBA kodu belgeye ekleme yönergeleri  
 Belge düzeyi özelleştirme çağıran VBA kodu, ekleyebileceğiniz belgenin birçok kopyası vardır.  
  
 Geliştirme ve çözümünüzü gibi hata ayıklama ya da Visual Studio (diğer bir deyişle, yapı çıkış klasöründe belge) projenizi çalıştırma açar belgede VBA kodu yazabilirsiniz. Ancak, Visual Studio ile ana proje klasöründeki belgenin bir kopyasını yapı çıktı klasörüne belgede değiştirdiğinden bu belgeye eklediğiniz herhangi VBA kodu Projeyi derlemek bir sonraki başlatılışında üzerine yazılır.  
  
 Hata ayıklama veya çözümü çalıştırırken belgeye eklemek VBA kodu kaydetmek istiyorsanız, proje klasöründeki belgeye VBA kodu kopyalayın. Yapılandırma işlemi hakkında daha fazla bilgi için bkz: [Office çözümleri oluşturma](../vsto/building-office-solutions.md).  
  
 Çözümünüzü dağıtmak hazır olduğunuzda VBA kodu ekleyebileceğiniz üç ana belge konumları vardır.  
  
### <a name="in-the-project-folder-on-the-development-computer"></a>Geliştirme bilgisayarındaki proje klasöründe  
 Bu konum, belgedeki VBA kodu ve özelleştirme kodunda üzerinde tam denetim varsa kullanışlıdır. Belge geliştirme bilgisayarınızda olduğundan özelleştirme kodunda değişiklik yaparsanız kolayca VBA kodu değiştirebilirsiniz. Bu belgenin kopyasına eklemek VBA kodu yapı, hata ayıklama ve çözümünüzü yayımlama belgede kalır.  
  
 Tasarımcıda açıkken belgeye VBA kodu ekleyemezsiniz. İlk Tasarımcısı'nda belgeyi kapatın ve sonra belgeyi doğrudan Word veya Excel'de açın.  
  
> [!CAUTION]  
>  Belge açıldığında çalışan VBA kodu eklerseniz, nadir durumlarda bu kodu belge bozuk veya açılış Tasarımcısı'nda engellemek.  
  
### <a name="in-the-publish-or-installation-folder"></a>Yayımlama ya da yükleme klasörü  
 Bazı durumlarda, belge yayımlama ya da yükleme klasöründeki VBA kodu eklemek uygun olabilir. Örneğin, VBA kodu yazılmış ve Visual Studio yüklü olmayan bir bilgisayara farklı bir geliştirici tarafından test varsa bu seçeneği belirleyebilirsiniz.  
  
 Kullanıcılar doğrudan yayımlama klasöründen çözümü yüklerse, çözümü her yayımladığınızda, belgeye VBA kodu eklemeniz gerekir. Visual Studio çözümü yayımladığınızda, yayımlama konumu belgede üzerine yazar.  
  
 Kullanıcılar yayımlama klasöründen farklı bir yükleme klasöründen çözümü yüklerse, çözümü her yayımladığınızda VBA kodu belgede ekleme önleyebilirsiniz. Yayımla güncelleştirme yükleme klasörüne yayımlama klasöründen taşınacak hazır olduğunda, tüm dosyaları belge dışında yükleme klasörüne kopyalayın.  
  
### <a name="on-the-end-user-computer"></a>Son kullanıcı bilgisayarda  
 Son kullanıcılar belge düzeyi özelleştirmelerinde sağladığınız Hizmetleri çağıran VBA geliştiriciler varsa, bunları kullanarak kodunuzu nasıl anlayabilirsiniz `CallVSTOAssembly` özelliği veya `GetManagedClass` belgenin kopyalarını yöntemi. Güncelleştirmeleri çözümü yayımladığınızda, son kullanıcı bilgisayarda belgedeki VBA kodu yazılmaz, tarafından belge değiştirilemez çünkü güncelleştirmeleri yayımlama.  
  
##  <a name="PropertyTasks"></a>Konak öğesi özellikleri tarafından gerçekleştirilen görevleri  
 Kullandığınızda **EnableVbaCallers** ve **ReferenceAssemblyFromVbaProject** özellikleri, Visual Studio farklı görev kümeleri gerçekleştirir.  
  
### <a name="enablevbacallers"></a>EnableVbaCallers  
 Ayarladığınızda **EnableVbaCallers** konak öğesi özelliği **doğru** bir Visual Basic projesinde Visual Studio aşağıdaki görevleri gerçekleştirir:  
  
1.  Ekler <xref:Microsoft.VisualBasic.ComClassAttribute> ve <xref:System.Runtime.InteropServices.ComVisibleAttribute> öznitelikleri için konak öğesi sınıfı.  
  
2.  Bu geçersiz kılmaları **GetAutomationObject** konak öğesi sınıfının yöntemi.  
  
3.  Bu ayarlar **ReferenceAssemblyFromVbaProject** konak öğesi özelliği **doğru**.  
  
 Ayarladığınızda **EnableVbaCallers** özelliğini yeniden **yanlış**, Visual Studio aşağıdaki görevleri gerçekleştirir:  
  
1.  Kaldırır <xref:Microsoft.VisualBasic.ComClassAttribute> ve <xref:System.Runtime.InteropServices.ComVisibleAttribute> özniteliklerini `ThisDocument` sınıfı.  
  
2.  Kaldırır **GetAutomationObject** konak öğesi sınıfından yöntemi.  
  
    > [!NOTE]  
    >  Visual Studio otomatik olarak ayarlamaz **ReferenceAssemblyFromVbaProject** özelliğini yeniden **False**. Bu özelliği ayarlamak **False** kullanarak el ile **özellikleri** penceresi.  
  
### <a name="referenceassemblyfromvbaproject"></a>ReferenceAssemblyFromVbaProject  
 Zaman **ReferenceAssemblyFromVbaProject** herhangi bir Visual Basic veya Visual C# projesinde konak öğesi özelliği ayarlanmış **doğru**, Visual Studio aşağıdaki görevleri gerçekleştirir:  
  
1.  Özelleştirme derlemesi için bir tür kitaplığı oluşturur ve tür kitaplığını derleme katıştırır.  
  
2.  Belge VBA projesinde aşağıdaki tür kitaplıklarına başvuru ekler:  
  
    -   Özelleştirme derlemeniz için tür kitaplığı.  
  
    -   Office yürütme için Microsoft Visual Studio Araçları Engine 9.0 tür kitaplığı. Bu tür kitaplığı dahil [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)].  
  
 Zaman **ReferenceAssemblyFromVbaProject** özelliği ayarlanmış geri **yanlış**, Visual Studio aşağıdaki görevleri gerçekleştirir:  
  
1.  Belgedeki VBA projesine tür kitaplığı başvuruları kaldırır.  
  
2.  Katıştırılmış tür kitaplığı derlemeden kaldırır.  
  
## <a name="troubleshooting"></a>Sorun giderme  
 Aşağıdaki tabloda bazı yaygın hatalar ve hataları düzeltmek için öneriler listelenmektedir.  
  
|Hata|Öneri|  
|-----------|----------------|  
|Ayarlandıktan sonra **EnableVbaCallers** veya **ReferenceAssemblyFromVbaProject** özelliği, bir hata iletisi durumlarını belge VBA proje içermiyor ve erişmek için izniniz yok Belgedeki VBA projesine.|Proje belgesinde en az bir VBA makrosu içeren, VBA projesini çalıştırmak için yeterli güvene sahip ve VBA projesi parola ile korunmuyor emin olun.|  
|Ayarlandıktan sonra **EnableVbaCallers** veya **ReferenceAssemblyFromVbaProject** özelliği, bir hata iletisi durumları <xref:System.Runtime.InteropServices.GuidAttribute> bildirimi eksik veya bozuk.|Emin <xref:System.Runtime.InteropServices.GuidAttribute> bildirimi projenizin AssemblyInfo.cs veya AssemblyInfo.vb dosyasında bulunur ve bu özniteliği için geçerli bir GUID ayarlayın.|  
|Ayarlandıktan sonra **EnableVbaCallers** veya **ReferenceAssemblyFromVbaProject** özelliği, bir hata iletisi durumları tarafından belirlenen sürüm numarasının <xref:System.Reflection.AssemblyVersionAttribute> geçerli değil.|Emin <xref:System.Reflection.AssemblyVersionAttribute> projenizin AssemblyInfo.cs veya AssemblyInfo.vb dosyasında bildirimi için geçerli bir derleme sürüm numarası ayarlanır. Geçerli bir derleme sürüm numaraları hakkında daha fazla bilgi için bkz: <xref:System.Reflection.AssemblyVersionAttribute> sınıfı.|  
|Özelleştirme derlemesini yeniden adlandırdıktan sonra özelleştirme derlemesini çağıran VBA kodu çalışmayı durdurur.|VBA kodu kullanıma sonra özelleştirme derlemesinin adını değiştirirseniz, belgedeki VBA projesi ve Özelleştirme derlemeniz arasındaki bağlantı bozuk. Bu sorunu gidermek için değiştirme **ReferenceFromVbaAssembly** projenize özelliğinde **False** ve ardından yeniden **doğru**ve ardından eski derleme için olan başvuruları değiştirin VBA kodu adı ile yeni derleme adı.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: Visual Basic projesinde VBA kodu kullanımına sunma](../vsto/how-to-expose-code-to-vba-in-a-visual-basic-project.md)   
 [Nasıl yapılır: Visual C &#35; VBA kodu kullanımına sunma Proje](../vsto/how-to-expose-code-to-vba-in-a-visual-csharp-project.md)   
 [İzlenecek yol: Visual Basic Projesinde VBA'dan Kod Çağırma](../vsto/walkthrough-calling-code-from-vba-in-a-visual-basic-project.md)   
 [İzlenecek yol: Arama Kodu VBA'dan Visual C &#35; Proje](../vsto/walkthrough-calling-code-from-vba-in-a-visual-csharp-project.md)   
 [Tasarlama ve Office çözümleri oluşturma](../vsto/designing-and-creating-office-solutions.md)   
 [VBA ve karşılaştırıldığında Visual Studio'da Office çözümleri](../vsto/vba-and-office-solutions-in-visual-studio-compared.md)   
 [Belge Düzeyi Özelleştirmelerini Programlama](../vsto/programming-document-level-customizations.md)  
  
  