---
title: 'İzlenecek yol: Web formunda hata ayıklama | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- Web pages [.NET Framework], debugging
- Web sites [.NET Framework], debugging
- ASP.NET, debugging Web applications
- Web applications [.NET Framework], debugging
- ASP.NET Web sites, debugging
- ASP.NET Web pages, debugging
- debugging ASP.NET Web applications, Web Forms
- debugging [Visual Studio], Web Forms
ms.assetid: e2b4fa14-8f5b-444d-a903-54070b784bd4
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 22fd6f033dd76e15311912256bc0597dfc3260c6
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
ms.locfileid: "31480338"
---
# <a name="walkthrough-debugging-a-web-form"></a>İzlenecek Yol: Web Formunda Hata Ayıklama
Bu izlenecek adımları hata ayıklamak nasıl Göster bir [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] Web uygulaması, Web formu olarak da bilinir. Bunu başlatmak ve yürütme durdurmak, kesme noktalarını ayarlayın ve değişkenleri incelemek nasıl gösterir **izleme** penceresi.  
  
> [!NOTE]
>  Bu izlenecek yolu tamamlamak için sunucu bilgisayarında yönetici ayrıcalıkları olmalıdır. Varsayılan olarak, [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] işleme, aspnet_wp.exe veya w3wp.exe olarak çalışan bir [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] işlemi. Hata ayıklamak için [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)], bilgisayarda yönetici ayrıcalıklarına sahip olduğu [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] çalıştırır. Daha fazla bilgi için bkz: [sistem gereksinimleri](../debugger/aspnet-debugging-system-requirements.md).  
  
 İletişim kutuları ve menü komutlarını gördüğünüz açıklanana Yardım'da etkin ayarlarınıza veya sürümünüze bağlı olarak farklı olabilir. Ayarlarınızı değiştirmek için tercih **içeri ve dışarı aktarma ayarları** üzerinde **Araçları** menüsü. Daha fazla bilgi için bkz: [Visual Studio IDE'yi kişiselleştirme](../ide/personalizing-the-visual-studio-ide.md).  
  
### <a name="to-create-the-web-form"></a>Web Form oluşturmak için  
  
1.  Zaten açık bir çözüm varsa, kapatın.  
  
2.  Üzerinde **dosya** menüsünde tıklatın **yeni**ve ardından **Web sitesi**.  
  
     **Yeni Web sitesi** iletişim kutusu görüntülenir.  
  
3.  İçinde **şablonları** bölmesinde tıklatın **ASP.NET Web sitesi**.  
  
4.  Üzerinde **konumu** satır, tıklatın **HTTP** listesinden ve metin kutusuna yazın **http://localhost/WebSite**.  
  
5.  İçinde **dil** tıklatın **Visual C#** veya **Visual Basic**.  
  
6.  **Tamam**'ı tıklatın.  
  
     [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Yeni bir proje oluşturur ve varsayılan HTML kaynak kodunu görüntüler. Ayrıca adlı yeni bir sanal dizin oluşturur **Web sitesi** altında **varsayılan Web sitesi** IIS'de.  
  
7.  Tıklatın **tasarım** alt kenar boşluğu sekmesinde.  
  
8.  Tıklatın **araç** sekmesinde sol kenar boşluğu veya üzerinde seçin **Görünüm** menüsü.  
  
     **Araç** açar.  
  
9. İçinde **araç**, tıklatın **düğmesini** denetlemek ve ana tasarım yüzeyi Default.aspx ekleyin.  
  
10. İçinde **araç**, tıklatın **Textbox** denetlemek ve denetimi Default.aspx ana tasarım yüzeyine sürükleyin.  
  
11. Bıraktığınız düğme denetimi çift tıklatın.  
  
     Bu kod sayfasına götürür: C# veya Default.aspx.vb için Default.aspx.cs [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]. İmleç işlevinde olmalıdır `Button1_Click`.  
  
12. İçinde `Button1_Click` işlev, aşağıdaki kodu ekleyin:  
  
    ```  
    ' Visual Basic  
    TextBox1.Text = "Button was clicked!"  
  
    // C#  
    TextBox1.Text = "Button was clicked!";  
    ```  
  
13. Üzerinde **yapı** menüsünde tıklatın **yapı çözümü**.  
  
     Proje derleme hataları.  
  
     Şimdi, hata ayıklama başlatmaya hazırsınız.  
  
### <a name="to-debug-the-web-form"></a>Web formunda hata ayıklamak için  
  
1.  Default.aspx.cs veya Default.aspx.vb penceresinde sol kenar boşluğu eklediğiniz metin olarak aynı satıra tıklayın:  
  
    ```  
    ' Visual Basic  
    TextBox1.Text = "Button was clicked!"  
  
    // C#  
    textBox1.Text = "Button was clicked!";  
    ```  
  
     Kırmızı bir nokta belirir ve satırdaki metin kırmızıyla vurgulanır. Kırmızı nokta bir kesme noktası temsil eder. Uygulamayı hata ayıklayıcısı altında çalıştırdığınızda, hata ayıklayıcısı koda ulaşıldığında, yürütmeyi o konumda keser. Ardından uygulamanızın durumunu görüntüleyebilir ve ona hata ayıklama yapabilirsiniz. Daha fazla bilgi için bkz: [kesme noktaları](http://msdn.microsoft.com/en-us/fe4eedc1-71aa-4928-962f-0912c334d583).  
  
2.  Üzerinde **hata ayıklama** menüsünde tıklatın **hata ayıklamayı Başlat**.  
  
3.  **Hata ayıklama etkin** iletişim kutusu görüntülenir. Seçin **hata ayıklamayı etkinleştirmek üzere Web.config dosyasında değişiklik** seçeneğini ve tıklayın **Tamam**.  
  
     Internet Explorer başlatır ve yalnızca tasarlanmış sayfasını görüntüler.  
  
4.  Internet Explorer'da düğmesini tıklatın.  
  
     İçinde [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], bu, satırı için kod sayfası Default.aspx.cs veya Default.aspx.vb isabetini belirlendiği alır. Bu satır, sarı ile vurgulanmış olmalıdır. Şimdi, uygulamanızda değişkenleri görüntüleyebilir ve yürütülmesini denetleyebilirsiniz. Uygulamanız yürütülmesi durdurulur ve, bir komutu bekler.  
  
5.  Üzerinde **hata ayıklama** menüsünde tıklatın **Windows**, ardından **izleme**ve ardından **Watch1**.  
  
6.  İçinde **izleme** penceresinde, türü **TextBox1.Text**.  
  
     **İzleme** penceresi gösterir değişkenin değeri olarak `TextBox1.Text`:  
  
    ```  
    ""  
    ```  
  
7.  Üzerinde **hata ayıklama** menüsünde tıklatın **Step Over**.  
  
     Değeri `TextBox1.Text` değişiklikleri **izleme** penceresi okumak için:  
  
    ```  
    "Button was clicked!"  
    ```  
  
8.  Üzerinde **hata ayıklama** menüsünde tıklatın **devam**.  
  
9. Internet Explorer'da yeniden düğmesini tıklatın.  
  
     Yürütme kesme noktasında yeniden durur.  
  
10. Default.aspx.cs veya Default.aspx.vb pencerede, sol kenar boşluğunda kırmızı noktaya tıklayın.  
  
     Kesme noktası kaldırır.  
  
11. Üzerinde **hata ayıklama** menüsünde tıklatın **durdurma hata ayıklama**.  
  
### <a name="to-attach-to-the-web-form-for-debugging"></a>Hata ayıklama için Web formu iliştirmek için  
  
1.  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] içinde, hata ayıklayıcısını çalışan bir işleme ekleyebilirsiniz. En etkili hata ayıklama için yürütülebilir dosya simge (PDB) dosyaları ile hata ayıklama sürümü derler.  
  
2.  Default.aspx.cs veya Default.aspx.vb penceresinde tekrar eklediğiniz satırında bir kesme noktası ayarlamak için sol kenar boşluğu'ı tıklatın:  
  
    ```  
    ' Visual Basic  
    TextBox1.Text = "Button was clicked!"  
  
    // C#  
    textBox1.Text = "Button was clicked!";  
    ```  
  
3.  Üzerinde **hata ayıklama** menüsünde tıklatın **hata ayıklama olmadan Başlat**.  
  
     Internet Explorer altında çalıştırmak için Web formu başlar, ancak hata ayıklayıcı iliştirilmemiş.  
  
4.  Ekleme [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] işlemi. Daha fazla bilgi için bkz: [dağıtılmış Web uygulamalarında hata ayıklama](../debugger/debugging-deployed-web-applications.md).  
  
5.  Internet Explorer'da formunuzda düğmesini tıklatın.  
  
     İçinde [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], Default.aspx.cs, Default.aspx.vb veya Default.aspx kesme noktası isabet.  
  
6.  İşiniz bittiğinde hata ayıklama, üzerinde **hata ayıklama** menüsünde tıklatın **durdurma hata ayıklama**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ASP.NET uygulamalarında hata ayıklama](../debugger/how-to-enable-debugging-for-aspnet-applications.md)