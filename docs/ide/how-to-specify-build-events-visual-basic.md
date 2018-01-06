---
title: "Nasıl yapılır: derleme olayları belirtme (Visual Basic) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pre-build events
- events [Visual Studio], builds
- post-build events
- build events [Visual Studio]
- builds [Visual Studio], events
ms.assetid: 40dc83bf-a7c5-4a14-816a-fa0980b6e4c3
caps.latest.revision: "26"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 42d412e576ddf9ca53f79b7349d99b87b9ef3238
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-specify-build-events-visual-basic"></a>Nasıl Yapılır: Derleme Olayları Belirtme (Visual Basic)
Derleme olayları Visual Basic komut dosyaları, makroları veya başka eylemler derlemeyi işleminin bir parçası olarak çalıştırmak için kullanılabilir. Oluşturma öncesi olaylar derleme önce oluşur; derleme sonrası olayları derleme sonra oluşur.  
  
 Derleme olayları belirtilir **yapı olayları** iletişim kutusu, kullanılabilir **derleme** sayfasında **Proje Tasarımcısı**.  
  
> [!NOTE]
>  Visual Basic Express yapı olayların girişini desteklemez. Bu, yalnızca tam Visual Studio ürün içinde desteklenir.  
  
## <a name="how-to-specify-pre-build-and-post-build-events"></a>Oluşturma öncesi ve sonrası derleme olayları belirtme  
  
#### <a name="to-specify-a-build-event"></a>Derleme olayının belirtmek için  
  
1.  Seçili bir proje ile **Çözüm Gezgini**, **proje** menüsünde tıklatın **özellikleri**.  
  
2.  Tıklatın **derleme** sekmesi.  
  
3.  Tıklatın **yapı olayları** açmak için düğmeye **yapı olayları** iletişim kutusu.  
  
4.  Oluşturma öncesi veya sonrası derleme eylemleriniz için komut satırı bağımsız değişkenleri girin ve ardından **Tamam**.  
  
    > [!NOTE]
    >  Ekleme bir `call` .bat dosyaları çalıştıran tüm sonrası derleme komutları önce deyim. Örneğin, `call C:\MyFile.bat` veya `call C:\MyFile.bat call C:\MyFile2.bat`.  
  
    > [!NOTE]
    >  Oluşturma öncesi veya oluşturma sonrası olay başarıyla tamamlanmazsa, başarılı bir eylem gösteren bir ile dışında sıfır (0), çıkış kodu olay eyleminizi sağlayarak yapı sonlandırabilir.  
  
## <a name="example-how-to-change-manifest-information-using-a-post-build-event"></a>Örnek: bir oluşturma sonrası olay kullanarak bildirim bilgisinin nasıl değiştirileceği  
 Aşağıdaki yordam en düşük işletim sistemi sürümünün bir oluşturma sonrası olay adlı bir .exe komutunu kullanarak uygulama bildiriminde nasıl ayarlanacağını gösterir (. proje dizininde exe.manifest dosyası). En düşük işletim sistemi sürümünü 4.10.0.0 gibi dört bölümden oluşan bir sayıdır. Bunu yapmak için komut değişir `<dependentOS>` bildirim bölümünü:  
  
```  
<dependentOS>  
   <osVersionInfo>  
      <os majorVersion="4" minorVersion="10" buildNumber="0" servicePackMajor="0" />  
   </osVersionInfo>  
</dependentOS>  
```  
  
#### <a name="to-create-an-exe-command-to-change-the-application-manifest"></a>Uygulama bildirimini değiştirmek için bir .exe komut oluşturmak için  
  
1.  Komutu için bir konsol uygulaması oluşturun. Gelen **dosya** menüsünde tıklatın **yeni**ve ardından **proje**.  
  
2.  İçinde **yeni proje** iletişim kutusunda **Visual Basic** düğümü, select **Windows** ve ardından **konsol uygulaması** şablonu. Proje adı `ChangeOSVersionVB`.  
  
3.  Module1.vb içinde aşağıdaki satırı ekleyin `Imports` dosyanın en üstüne deyimlerini:  
  
    ```  
    Imports System.Xml  
    ```  
  
4.  Aşağıdaki kodu ekleyin `Sub Main`:  
  
    ```  
    Sub Main()  
       Dim applicationManifestPath As String  
       applicationManifestPath = My.Application.CommandLineArgs(0)  
       Console.WriteLine("Application Manifest Path: " & applicationManifestPath.ToString)  
  
       'Get version name  
       Dim osVersion As Version  
       If My.Application.CommandLineArgs.Count >= 2 Then  
          osVersion = New Version(My.Application.CommandLineArgs(1).ToString)  
       Else  
          Throw New ArgumentException("OS Version not specified.")  
       End If  
       Console.WriteLine("Desired OS Version: " & osVersion.ToString())  
  
       Dim document As XmlDocument  
       Dim namespaceManager As XmlNamespaceManager  
       namespaceManager = New XmlNamespaceManager(New NameTable())  
       With namespaceManager  
          .AddNamespace("asmv1", "urn:schemas-microsoft-com:asm.v1")  
          .AddNamespace("asmv2", "urn:schemas-microsoft-com:asm.v2")  
       End With  
  
       document = New XmlDocument()  
       document.Load(applicationManifestPath)  
  
       Dim baseXPath As String  
       baseXPath = "/asmv1:assembly/asmv2:dependency/asmv2:dependentOS/asmv2:osVersionInfo/asmv2:os"  
  
       'Change minimum required OS Version.  
       Dim node As XmlNode  
       node = document.SelectSingleNode(baseXPath, namespaceManager)  
       node.Attributes("majorVersion").Value = osVersion.Major.ToString()  
       node.Attributes("minorVersion").Value = osVersion.Minor.ToString()  
       node.Attributes("buildNumber").Value = osVersion.Build.ToString()  
       node.Attributes("servicePackMajor").Value = osVersion.Revision.ToString()  
  
       document.Save(applicationManifestPath)  
    End Sub  
    ```  
  
     Komut iki bağımsız değişkeni alır. İlk bağımsız değişken uygulama bildirimi yoludur (diğer bir deyişle, klasör oluşturma işlemi genellikle Projectname.publish bildirimi oluşturur). İkinci bağımsız değişkeni yeni bir işletim sistemi sürümüdür.  
  
5.  Üzerinde **yapı** menüsünde tıklatın **yapı çözümü**.  
  
6.  .Exe dosyası gibi bir dizine kopyalayın `C:\TEMP\ChangeOSVersionVB.exe`.  
  
 Ardından, uygulama bildirimi değiştirmek için bu komutu bir oluşturma sonrası olay çağırma.  
  
#### <a name="to-invoke-a-post-build-event-to-change-the-application-manifest"></a>Uygulama bildirimini değiştirmek için bir oluşturma sonrası olay çağırmak için  
  
1.  Yayımlanacak projeyi için bir Windows uygulaması oluşturun. Gelen **dosya** menüsünde tıklatın **yeni**ve ardından **proje**.  
  
2.  İçinde **yeni proje** iletişim kutusunda **Visual Basic** düğümü, select **Windows Klasik Masaüstü** ve ardından **Windows Forms uygulaması** Şablon. Proje adı `VBWinApp`.  
  
3.  Seçili proje ile **Çözüm Gezgini**, **proje** menüsünde tıklatın **özellikleri**.  
  
4.  Proje Tasarımcısı'nda Git **Yayımla** sayfasında ve ayarlama **konum yayımlama** için `C:\TEMP\`.  
  
5.  Tıklayarak projeyi yayımlama **Şimdi Yayımla**.  
  
     Bildirim dosyası oluşturulur ve koyun `C:\TEMP\VBWinApp_1_0_0_0\VBWinApp.exe.manifest`. Bildirim görüntülemek için dosyaya sağ tıklayın ve **birlikte Aç**, ardından **programı listeden seçin.**ve ardından **not defteri**.  
  
     Arama için dosyasında `<osVersionInfo>` öğesi. Örneğin, sürüm olabilir:  
  
    ```  
    <os majorVersion="4" minorVersion="10" buildNumber="0" servicePackMajor="0" />  
    ```  
  
6.  Proje Tasarımcısı'nda Git **derleme** sekmesinde **yapı olayları** açmak için düğmeye **yapı olayları** iletişim kutusu.  
  
7.  İçinde **oluşturma sonrası olay komut satırı** kutusunda, aşağıdaki komutu girin:  
  
     `C:\TEMP\ChangeOSVersionVB.exe "$(TargetPath).manifest" 5.1.2600.0`  
  
     Projesi derlerken, bu komut uygulama bildiriminde en düşük işletim sistemi sürümü için 5.1.2600.0 değiştirin.  
  
     `$(TargetPath)` Makrosu oluşturulan yürütülebilir dosyanın tam yolunu ifade eder. Bu nedenle, $(TargetPath) .manifest depo Directory'de oluşturulan uygulama bildirimi belirtmeniz gerekecektir. Yayımlama, daha önce belirlediğiniz yayımlama konumu için bu bildirimi kopyalayacak.  
  
8.  Projeyi yeniden yayımlayın. Git **Yayımla** sayfasında ve tıklayın **Şimdi Yayımla**.  
  
     Bildirim yeniden görüntüleyin. Bildirim görüntülemek için Yayımla dizinine dosyasını sağ tıklatın ve gidin **birlikte Aç** ve ardından **programı listeden seçin.**ve ardından **not defteri**.  
  
     Sürüm şimdi şöyle olmalıdır:  
  
    ```  
    <os majorVersion="5" minorVersion="1" buildNumber="2600" servicePackMajor="0" />  
    ```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleme özelliklerini yönetme](http://msdn.microsoft.com/en-us/94308881-f10f-4caf-a729-f1028e596a2c)   
 [Derle sayfası, Proje Tasarımcısı (Visual Basic)](../ide/reference/compile-page-project-designer-visual-basic.md)   
 [Yayımla Sayfası, Proje Tasarımcısı](../ide/reference/publish-page-project-designer.md)   
 [Derleme öncesi olay/derleme sonrası olay komut satırı iletişim kutusu](../ide/reference/pre-build-event-post-build-event-command-line-dialog-box.md)   
 [Nasıl Yapılır: Derleme Olayları Belirtme (C#)](../ide/how-to-specify-build-events-csharp.md)