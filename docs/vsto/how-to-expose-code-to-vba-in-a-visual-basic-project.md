---
title: 'Nasıl yapılır: Visual Basic projesinde VBA kodu kullanımına sunma | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- VBA [Office development in Visual Studio], exposing code in document-level customizations
- document-level customizations [Office development in Visual Studio], exposing code
- Visual Basic [Office development in Visual Studio], exposing code to VBA
- exposing code to VBA
- host items [Office development in Visual Studio], exposing code to VBA
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 39dc659f7c8841bcf350249332278091232a32d2
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-expose-code-to-vba-in-a-visual-basic-project"></a>Nasıl Yapılır: Visual Basic Projesinde Kodu VBA Kullanımına Sunma
  Kodda getirebilir bir [!INCLUDE[vbprvb](../sharepoint/includes/vbprvb-md.md)] iki tür kod birbirleri ile etkileşim kurmak istiyorsanız, Visual Basic for Applications (VBA) kodundaki proje.  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
 Visual Basic Visual C# işleminden farklı bir işlemdir. Daha fazla bilgi için bkz: [nasıl yapılır: Visual c VBA'ya kodu kullanıma&#35; proje](../vsto/how-to-expose-code-to-vba-in-a-visual-csharp-project.md).  
  
 Diğer sınıf kodları için farklı bir ana bilgisayar öğesi sınıf kodu için bir işlemdir:  
  
-   [Konak öğesi sınıf kodu gösterme](#HostItemCode)  
  
-   [Bir konak öğesi sınıfında değil kodu gösterme](#NonHostItem)  
  
 ![video bağlantı](../vsto/media/playvideo.gif "video bağlantı") ilgili video gösterimi için bkz: [nasıl yapmak I: çağrı VSTO Kodu VBA'dan?](http://go.microsoft.com/fwlink/?LinkId=136757).  
  
##  <a name="HostItemCode"></a> Konak öğesi sınıf kodu gösterme  
 Visual Basic kodu bir konak öğesi sınıfında çağırmak VBA kodu etkinleştirmek için ayarlanmış **EnableVbaCallers** konak öğesi özelliği **doğru**.  
  
 Konak öğesi sınıf yöntemi göstermek ve VBA'dan çağırmak nasıl izlenecek yol için bkz: [izlenecek yol: Visual Basic Projesinde VBA'dan Kod Çağırma](../vsto/walkthrough-calling-code-from-vba-in-a-visual-basic-project.md). Konak öğeleri hakkında daha fazla bilgi için bkz: [konak öğelerine ve denetimlerine genel bakış](../vsto/host-items-and-host-controls-overview.md).  
  
#### <a name="to-expose-code-in-a-host-item-to-vba"></a>Konak öğesi VBA kodu kullanıma sunmak için  
  
1.  Belge düzeyi oluşturun veya açın [!INCLUDE[vbprvb](../sharepoint/includes/vbprvb-md.md)] Word belgesi, Excel çalışma kitabı veya makroları destekleyen ve zaten VBA kodu içeren Excel şablonu göre projesi.  
  
     Makroları destekleyen belge dosya biçimleri hakkında daha fazla bilgi için bkz: [birleştirme VBA ve belge düzeyi özelleştirmeleri](../vsto/combining-vba-and-document-level-customizations.md).  
  
    > [!NOTE]  
    >  Bu özellik Word şablon projelerinde kullanılamaz.  
  
2.  VBA kodu belgedeki makroları kullanıcıya sormadan çalışmasına izin verildiğinden emin olun. Office proje konumunu Word veya Excel Güven Merkezi ayarlarında güvenilir konumlar listesine ekleyerek çalıştırmak için VBA kodu güvenebilirsiniz.  
  
3.  Özelliği, yöntemi veya bir ana bilgisayar öğesi sınıflarının projenizdeki VBA kullanıma sunmak istediğiniz olay eklemek ve yeni üye olarak bildirme **ortak**. Sınıfın adı uygulamaya bağlıdır:  
  
    -   Proje, konak öğesi sınıfı bir sözcük adlı `ThisDocument` varsayılan olarak.  
  
    -   Excel projesinde konak öğesi sınıfı adlı `ThisWorkbook`, `Sheet1`, `Sheet2`, ve `Sheet3` varsayılan olarak.  
  
4.  Ayarlama **EnableVbaCallers** konak öğesi özelliği **doğru**. Bu özellik kullanılabilir **özellikleri** konak öğesi tasarımcıda açık olduğu zaman penceresi.  
  
     Bu özellik ayarlandıktan sonra Visual Studio otomatik olarak ayarlar **ReferenceAssemblyFromVbaProject** özelliğine **doğru**.  
  
    > [!NOTE]  
    >  Çalışma kitabı veya belge VBA kodu zaten içermiyor veya belgedeki VBA kodu çalıştırmak için güvenilir değilse, ayarlarken bir hata iletisi alırsınız **EnableVbaCallers** özelliğine **doğru**. Bu durum, bu durumda belgedeki VBA projesini Visual Studio değiştirilemiyor çünkü.  
  
5.  Tıklatın **Tamam** iletisi görüntülenir. Bu ileti çalışma kitabına veya belgeye VBA kodu eklerseniz projeden çalıştırıyorsanız anımsatır [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], VBA kodunu projeyi derleme başlatıldığında kaybolacak. Projeyi derlemek her zaman yapı çıktı klasörüne belgede üzerine olmasıdır.  
  
     Bu noktada, Visual Studio Proje VBA projesini derlemeye çağırabilirsiniz şekilde yapılandırır. Visual Studio ayrıca adlı bir özellik ekler `CallVSTOAssembly` için `ThisDocument`, `ThisWorkbook`, `Sheet1`, `Sheet2`, veya `Sheet3` VBA projesinde modülü. VBA için kullanıma sunulan sınıfın ortak üyelerine erişmek için bu özelliği kullanın.  
  
6.  Projeyi oluşturun.  
  
##  <a name="NonHostItem"></a> Bir konak öğesi sınıfında değil kodu gösterme  
 Bir konak öğesi sınıfında değil Visual Basic kodu çağırmak VBA kodu etkinleştirmek için kodu VBA için görünür olacak şekilde değiştirin.  
  
#### <a name="to-expose-code-that-is-not-in-a-host-item-class-to-vba"></a>VBA konak öğesi sınıfına değil kod kullanıma sunmak için  
  
1.  Belge düzeyi oluşturun veya açın [!INCLUDE[vbprvb](../sharepoint/includes/vbprvb-md.md)] Word belgesi, Excel çalışma kitabı veya makroları destekleyen ve zaten VBA kodu içeren Excel şablonu göre projesi.  
  
     Makroları destekleyen belge dosya biçimleri hakkında daha fazla bilgi için bkz: [birleştirme VBA ve belge düzeyi özelleştirmeleri](../vsto/combining-vba-and-document-level-customizations.md).  
  
    > [!NOTE]  
    >  Bu özellik Word şablon projelerinde kullanılamaz.  
  
2.  VBA kodu belgedeki makroları kullanıcıya sormadan çalışmasına izin verildiğinden emin olun. Office proje konumunu Word veya Excel Güven Merkezi ayarlarında güvenilir konumlar listesine ekleyerek çalıştırmak için VBA kodu güvenebilirsiniz.  
  
3.  VBA için ortak bir sınıf projenizdeki kullanıma sunmak istediğiniz üye eklemek ve yeni üye olarak bildirme **ortak**.  
  
4.  Aşağıdaki uygulama <xref:System.Runtime.InteropServices.ComVisibleAttribute> ve <xref:Microsoft.VisualBasic.ComClassAttribute> öznitelikleri için VBA gösterme sınıfa. Bu öznitelikler sınıfı VBA görünür kılar.  
  
    ```vb  
    <Microsoft.VisualBasic.ComClass()> _  
    <System.Runtime.InteropServices.ComVisibleAttribute(True)> _  
    ```  
  
5.  Geçersiz kılma **GetAutomationObject** gösterme sınıfının bir örneğini dönmek için projenizdeki konak öğesi sınıfının yöntemi. Aşağıdaki kod örneğinde adlı bir sınıf gösterme varsayar `DocumentUtilities` VBA.  
  
    ```vb  
    Protected Overrides Function GetAutomationObject() As Object  
        Return New DocumentUtilities()  
    End Function  
    ```  
  
6.  Belge (Word) veya çalışma sayfası (Excel) Tasarımcısı'nda açmak [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
7.  İçinde **özellikleri** penceresinde, seçin **ReferenceAssemblyFromVbaProject** özelliği ve değerini değiştirin **doğru**.  
  
    > [!NOTE]  
    >  Çalışma kitabı veya belge VBA kodu zaten içermiyor veya belgedeki VBA kodu çalıştırmak için güvenilir değilse, ayarlarken bir hata iletisi alırsınız **ReferenceAssemblyFromVbaProject** özelliğine **True** . Bu durum, bu durumda belgedeki VBA projesini Visual Studio değiştirilemiyor çünkü.  
  
8.  Tıklatın **Tamam** iletisi görüntülenir. Bu ileti çalışma kitabına veya belgeye VBA kodu eklerseniz projeden çalıştırıyorsanız anımsatır [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], VBA kodunu projeyi derleme başlatıldığında kaybolacak. Projeyi derlemek her zaman yapı çıktı klasörüne belgede üzerine olmasıdır.  
  
     Bu noktada, Visual Studio Proje VBA projesini derlemeye çağırabilirsiniz şekilde yapılandırır. Visual Studio adlı bir yöntem de ekler `GetManagedClass` VBA projesine. Bu yöntem herhangi bir yerden çağırabilir VBA için kullanıma sunulan sınıfa erişmek için VBA projesindeki.  
  
9. Projeyi oluşturun.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: Visual Studio'da Office projeleri oluşturma](../vsto/how-to-create-office-projects-in-visual-studio.md)   
 [Tasarlama ve Office çözümleri oluşturma](../vsto/designing-and-creating-office-solutions.md)   
 [VBA ve belge düzeyi özelleştirmelerini birleştirme](../vsto/combining-vba-and-document-level-customizations.md)   
 [İzlenecek yol: Visual Basic Projesinde VBA'dan Kod Çağırma](../vsto/walkthrough-calling-code-from-vba-in-a-visual-basic-project.md)   
 [Nasıl yapılır: Visual c VBA kodu kullanımına sunma&#35; proje](../vsto/how-to-expose-code-to-vba-in-a-visual-csharp-project.md)  
  
  