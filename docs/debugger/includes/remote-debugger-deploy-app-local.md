---
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.openlocfilehash: 37963e1ee5b7eeb0d07c36e0abe42c98eb6436fe
ms.sourcegitcommit: e01ccb5ca4504a327d54f33589911f5d8be9c35c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/15/2018
---
1. İçinde **Çözüm Gezgini**, proje düğümüne sağ tıklayın ve seçin **Yayımla** (Web formları için **Web uygulaması yayımlama**).

2. İçinde **Yayımla** iletişim kutusunda **klasörü**, tıklatın **Gözat**ve yeni bir klasör oluşturun **C:\Publish**.

    ![RemoteDBG_Publish_Local](../media/remotedbg_publish_local.png "RemoteDBG_Publish_Local")

    Web Forms uygulaması için seçin **özel** Yayımla iletişim kutusunda bir profil adı girin ve seçin **Tamam**.

3. Tıklatın **yayımlama**.

    Visual Studio Proje klasöre yayımlar. İlerleme durumunu çıktı penceresinde gösterir.

4. İçinde **Yayımla** iletişim kutusu, tıklatın **ayarları** bağlamak ve ardından **ayarları** sekmesi.

5. Yapılandırma kümesi **hata ayıklama**seçin **var olan tüm dosyaları yayımlamak için önceki silin**ve ardından **kaydetmek**.

    > [!NOTE]
    > Yayın derlemesi kullanırsanız, yayımladığınızda, web.config dosyasında hata ayıklama devre dışı.

6. Tıklatın **yayımlama**.

    ![RemoteDBG_Publish_Debug_Config](../media/remotedbg_publish_debug_config.png "RemoteDBG_Publish_Debug_Config")
    
    Uygulama yayımlayan bir **hata ayıklama** projesinin yerel klasörde yapılandırma.

5. ASP.NET proje dizini, Visual Studio bilgisayardan ASP.NET uygulaması için yapılandırılan yerel dizine kopyalayın (Bu örnekte, **C:\Publish**) Windows Server bilgisayarında. Bu öğreticide, el ile kopyaladığınız ancak PowerShell, Xcopy veya Robocopy gibi diğer araçları kullanabilirsiniz varsayıyoruz.

    > [!CAUTION]
    >  Kod ya da yeniden değişiklikleri yapmanız gerekirse, yeniden yayımlamanız ve bu adımı yineleyin. Uzak makineye kopyaladığınız yürütülebilir yerel kaynağı ve simgeleri tam olarak eşleşmelidir.    Bu alırsınız yapmazsanız bir `cannot find or open the PDB file` işlemde hata ayıklamak çalıştığınızda Visual Studio'da uyarı.

6. Windows Server'da, uygulamanın doğru uygulama tarayıcınızda açarak çalıştırabilirsiniz olduğunu doğrulayın.

    Uygulamanın düzgün çalışmazsa, ASP.NET, sunucunuz ve Visual Studio makinenizin üzerinde yüklü sürüm arasında bir uyuşmazlık olabilir veya IIS veya Web sitesi yapılandırma ile ilgili bir sorun olabilir. Önceki adımlarda yeniden denetleyin.
