---
title: Özel oluşturma başlangıç sayfasının | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
ms.assetid: d67e0c53-9f5a-45fb-a929-b9d2125c3c82
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 71892262d98b175b111218068a02d03ad3d04caa
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="creating-a-custom-start-page"></a>Özel bir başlangıç sayfası oluşturma
Bu belgedeki adımları izleyerek, özel bir başlangıç sayfası oluşturabilirsiniz.  
  
## <a name="creating-a-blank-start-page"></a>Boş başlangıç sayfası oluşturma  
 Öncelikle, boş bir başlangıç sayfası, Visual Studio tanıyacağı bir etiket yapısı .xaml dosyasında oluşturarak olun. Ardından, biçimlendirme ve istediğiniz işlevselliği ve görünüm üretmek için arka plan kodu ekleyin.  
  
#### <a name="to-create-a-blank-start-page"></a>Boş bir başlangıç sayfası oluşturmak için  
  
1.  Yeni bir proje türü oluşturma **WPF uygulaması** (**Visual C# / Windows Masaüstü**.  
  
2.  Bir başvuru ekleyin `Microsoft.VisualStudio.Shell.14.0`.  
  
3.  XAML dosyasını XML düzenleyicisinde açın ve üst düzey değiştirme \<penceresi > öğesine bir \<UserControl > herhangi bir ad alanı bildirimleri kaldırma olmadan öğesi.  
  
4.  Kaldırma `x:Class` en üst düzey öğesi bildiriminden. Bu XAML içeriği başlangıç sayfasını barındıran Visual Studio araç penceresi ile uyumlu hale getirir.  
  
5.  Aşağıdaki ad alanı bildirimleri için üst düzey ekleme \<UserControl > öğesi.  
  
    ```  
    xmlns:vs="clr-namespace:Microsoft.VisualStudio.PlatformUI;assembly=Microsoft.VisualStudio.Shell.14.0"  
    xmlns:vsfx="clr-namespace:Microsoft.VisualStudio.Shell;assembly=Microsoft.VisualStudio.Shell.14.0"  
    ```  
  
     Bu ad alanları, Visual Studio komutları, denetimleri ve UI ayarlarını erişim sağlar. Daha fazla bilgi için bkz: [bir başlangıç sayfası için Visual Studio komutları ekleme](../extensibility/adding-visual-studio-commands-to-a-start-page.md).  
  
     Aşağıdaki örnek, boş bir başlangıç sayfası .xaml dosyasında işaretleme gösterir. Herhangi bir özel içerik iç gitmesi gereken <xref:System.Windows.Controls.Grid> öğesi.  
  
    ```vb  
    <UserControl  
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"  
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
        xmlns:MyNamespace="clr-namespace:ManualStartPage;assembly=ManualStartPage"  
        xmlns:vs="clr-namespace:Microsoft.VisualStudio.PlatformUI;assembly=Microsoft.VisualStudio.Shell.14.0"  
                xmlns:vsfx="clr-namespace:Microsoft.VisualStudio.Shell;assembly=Microsoft.VisualStudio.Shell.14.0"  
        xmlns:local="clr-namespace:StartPageHost"  
        mc:Ignorable="d"  
         Height="350" Width="525">  
        <Grid>  
        <!--Add content here.-->  
        </Grid>  
    </UserControl>  
    ```  
  
6.  Boş denetimleri ekleme \<UserControl > özel başlangıç sayfası doldurmak için öğesi. Visual Studio için belirli işlevselliği ekleme hakkında daha fazla bilgi için bkz: [bir başlangıç sayfası için Visual Studio komutları ekleme](../extensibility/adding-visual-studio-commands-to-a-start-page.md).  
  
## <a name="testing-and-applying-the-custom-start-page"></a>Test etme ve özel uygulama başlangıç sayfası  
 Visual Studio kilitleniyor değil doğrulayana kadar özel başlangıç sayfası çalıştırmak için Visual Studio birincil örneğini ayarlı değil. Bunun yerine, deneysel örneğinde sınayın.  
  
#### <a name="to-test-a-manually-created-custom-start-page"></a>El ile oluşturulan özel bir başlangıç sayfası test etmek için  
  
1.  XAML dosyanızı ve destekleyici metin dosyaları veya işaretleme dosyaları, çok kopya **%USERPROFILE%\My Documents\Visual Studio 2015\StartPages\\**  klasör.  
  
2.  Başlangıç sayfanızı herhangi bir denetimleri veya Visual Studio tarafından yüklenmemiş derlemelerindeki başvuruyorsa, derlemeler kopyalayıp sonra bunları * Visual Studio yükleme klasörü ***\Common7\IDE\PrivateAssemblies\\** .  
  
3.  Bir Visual Studio komut isteminde **devenv /rootsuffix Exp** Visual Studio deneysel örneği açın.  
  
4.  Deneysel örneğinde Git **Araçlar / Seçenekler / ortamı / başlangıç** sayfasında ve XAML dosyanızdan seçin **başlangıç sayfasını özelleştirme** açılır.  
  
5.  Üzerinde **Görünüm** menüsünde tıklatın **başlangıç sayfası**.  
  
     Özel başlangıç sayfanızı görüntülenmesi gerekir. Tüm dosyaları değiştirmek istiyorsanız, gerekir deneysel örneği kapatın, değişiklik, kopyalamak ve değişen dosyaları yapıştırın ve değişiklikleri görmek için deneysel örneği yeniden açın.  
  
#### <a name="to-apply-the-custom-start-page-in-the-primary-instance-of-visual-studio"></a>Özel uygulamak için Visual Studio birincil örneğinde sayfa Başlat  
  
-   Başlangıç sayfası test ve kararlı buldu sonra kullanın **başlangıç sayfasını özelleştirme** seçeneğini **seçenekleri** birincil örneğindeki Visual Studio Başlangıç sayfası olarak seçmek için iletişim kutusu  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İzlenecek yol: Özel XAML başlangıç sayfasına ekleme](../extensibility/walkthrough-adding-custom-xaml-to-the-start-page.md)   
 [Kullanıcı denetimi için başlangıç sayfası ekleme](../extensibility/adding-user-control-to-the-start-page.md)   
 [Başlangıç sayfası için Visual Studio komut ekleme](../extensibility/adding-visual-studio-commands-to-a-start-page.md)   
 [İzlenecek yol: Bir başlangıç sayfasında kullanıcı ayarlarını kaydetme](../extensibility/walkthrough-saving-user-settings-on-a-start-page.md)   
 [Özel Başlangıç Sayfaları Dağıtma](../extensibility/deploying-custom-start-pages.md)