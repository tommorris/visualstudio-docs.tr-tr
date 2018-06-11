---
title: 'Nasıl yapılır: Visual C# projesinde kodu VBA kullanımına sunma'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Visual C# [Office development in Visual Studio], exposing code to VBA
- VBA [Office development in Visual Studio], exposing code in document-level customizations
- document-level customizations [Office development in Visual Studio], exposing code
- exposing code to VBA
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 36bdcd7360099818ac8510d9eab87d6d3dc0f0fc
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/11/2018
ms.locfileid: "35257257"
---
# <a name="how-to-expose-code-to-vba-in-a-visual-c-project"></a>Nasıl yapılır: Visual C# projesinde kodu VBA kullanımına sunma
  İki tür kod birbirleri ile etkileşim kurmak istiyorsanız, bir Visual C# projesinde Visual Basic for Applications (VBA) kodunu kodda getirebilir.  
  
 Visual C# işlemi Visual Basic işleminden farklıdır. Daha fazla bilgi için bkz: [nasıl yapılır: Visual Basic projesinde kodu VBA kullanımına sunma](../vsto/how-to-expose-code-to-vba-in-a-visual-basic-project.md).  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
## <a name="expose-code-in-a-visual-c-project"></a>Visual C# projesinde kodu kullanıma sunma  
 Visual C# projesinde kod çağırmak için VBA kodu etkinleştirmek için kodu COM görünür olacak şekilde değiştirin ve ardından **ReferenceAssemblyFromVbaProject** özelliğine **True** Tasarımcısı'nda.  
  
 Bir yöntemin bir Visual C# projesinde VBA'dan nasıl çağrılacağını izlenecek yol için bkz: [izlenecek yol: Visual C VBA'dan Kod Çağırma&#35; proje](../vsto/walkthrough-calling-code-from-vba-in-a-visual-csharp-project.md).  
  
### <a name="to-expose-code-in-a-visual-c-project-to-vba"></a>VBA Visual C# projesinde kodu kullanıma sunmak için  
  
1.  Bir Word belgesi, Excel çalışma kitabı veya makroları destekleyen ve zaten VBA kodu içeren Excel şablonu temel alan bir belge düzeyi projesi oluşturun veya açın.  
  
     Makroları destekleyen belge dosya biçimleri hakkında daha fazla bilgi için bkz: [birleştirmek VBA ve belge düzeyi özelleştirmeleri](../vsto/combining-vba-and-document-level-customizations.md).  
  
    > [!NOTE]  
    >  Bu özellik Word şablon projelerinde kullanılamaz.  
  
2.  VBA kodu belgedeki makroları kullanıcıya sormadan çalışmasına izin verildiğinden emin olun. Office proje konumunu Word veya Excel Güven Merkezi ayarlarında güvenilir konumlar listesine ekleyerek çalıştırmak için VBA kodu güvenebilirsiniz.  
  
3.  VBA için ortak bir sınıf projenizdeki kullanıma sunmak istediğiniz üye eklemek ve yeni üye olarak bildirme **ortak**.  
  
4.  Aşağıdaki uygulama <xref:System.Runtime.InteropServices.ComVisibleAttribute> ve <xref:System.Runtime.InteropServices.ClassInterfaceAttribute> öznitelikleri için VBA gösterme sınıfa. Bu öznitelikler sınıfı görünür yapmak COM, ancak bir sınıf arabirimi oluşturma olmadan.  
  
    ```csharp  
    [System.Runtime.InteropServices.ComVisible(true)]  
    [System.Runtime.InteropServices.ClassInterface(  
        System.Runtime.InteropServices.ClassInterfaceType.None)]  
    ```  
  
5.  Geçersiz kılma **GetAutomationObject** gösterme sınıfının bir örneğini dönmek için projenizdeki konak öğesi sınıfının yöntemi:  
  
    -   Konak öğesi sınıfını gösterme, geçersiz kılma **GetAutomationObject** metodun bu sınıfın ait olduğu ve sınıfının geçerli örneği döndürür.  
  
        ```csharp  
        protected override object GetAutomationObject()  
        {  
            return this;  
        }  
        ```  
  
    -   VBA konak öğesi olmayan bir sınıf gösterme, geçersiz kılma **GetAutomationObject** yöntemi herhangi bir konak öğesi projenizde ve konak öğesi olmayan sınıfının bir örneğini döndürür. Örneğin, aşağıdaki kod adlı bir sınıf gösterme varsayar `DocumentUtilities` VBA.  
  
        ```csharp  
        protected override object GetAutomationObject()  
        {  
            return new DocumentUtilities();  
        }  
        ```  
  
     Konak öğeleri hakkında daha fazla bilgi için bkz: [konak öğelerini ve konak denetimlerine genel bakış](../vsto/host-items-and-host-controls-overview.md).  
  
6.  VBA için gösterme sınıfından bir arabirim ayıklayın. İçinde **arayüz** iletişim kutusunda, arabirim bildiriminde dahil etmek istediğiniz ortak üyeleri seçin. Daha fazla bilgi için bkz: [arabirimi yeniden düzenleme ayıklamak](../ide/reference/extract-interface.md).
  
7.  Ekleme **ortak** arabirim bildiriminde anahtar sözcük.  
  
8.  Aşağıdakileri ekleyerek arabirimi COM görünür hale <xref:System.Runtime.InteropServices.ComVisibleAttribute> özniteliği için arabirim.  
  
    ```csharp  
    [System.Runtime.InteropServices.ComVisible(true)]  
    ```  
  
9. Belge (Word) veya çalışma sayfası (Excel) Tasarımcısı'nda açmak [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
10. İçinde **özellikleri** penceresinde, seçin **ReferenceAssemblyFromVbaProject** özelliği ve değerini değiştirin **doğru**.  
  
    > [!NOTE]  
    >  Çalışma kitabı veya belge VBA kodu zaten içermiyor veya belgedeki VBA kodu çalıştırmak için güvenilir değilse, ayarlarken bir hata iletisi alırsınız **ReferenceAssemblyFromVbaProject** özelliğine **True**. Bu durum, bu durumda belgedeki VBA projesini Visual Studio değiştirilemiyor çünkü.  
  
11. Tıklatın **Tamam** iletisi görüntülenir. Bu ileti eklerseniz VBA kodunu çalışma kitabına veya belge projeden çalıştırırken, anımsatır [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], VBA kodunu projeyi açtığınızda kaybolacak. Klasör projeyi her zaman üzerine belgenin yapı çıktı olmasıdır.  
  
     Bu noktada, Visual Studio Proje VBA projesini derlemeye çağırabilirsiniz şekilde yapılandırır. Visual Studio adlı bir yöntem de ekler `GetManagedClass` VBA projesine. Bu yöntem herhangi bir yerden çağırabilir VBA için kullanıma sunulan sınıfa erişmek için VBA projesindeki.  
  
12. Projeyi oluşturun.  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Nasıl yapılır: Visual Studio'da Office projeleri oluşturma](../vsto/how-to-create-office-projects-in-visual-studio.md)   
 [Tasarlama ve Office çözümleri oluşturma](../vsto/designing-and-creating-office-solutions.md)   
 [VBA ve belge düzeyi özelleştirmelerini birleştirme](../vsto/combining-vba-and-document-level-customizations.md)   
 [İzlenecek yol: Visual C VBA'dan Kod Çağırma&#35; proje](../vsto/walkthrough-calling-code-from-vba-in-a-visual-csharp-project.md)   
 [Nasıl yapılır: Visual Basic projesinde kodu VBA kullanımına sunma](../vsto/how-to-expose-code-to-vba-in-a-visual-basic-project.md)  
  
  