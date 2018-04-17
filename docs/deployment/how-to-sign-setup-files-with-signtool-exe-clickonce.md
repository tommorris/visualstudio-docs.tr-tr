---
title: 'Nasıl yapılır: Kurulum dosyalarını SignTool.exe (ClickOnce) ile | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce applications, signtool.exe
- deploying applications [ClickOnce], re-signing setup.exe
- ClickOnce deployment, signtool.exe
- ClickOnce applications, re-signing setup.exe
- ClickOnce deployment, re-signing setup.exe
ms.assetid: 545a4005-d283-4110-9821-c78a9833c250
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: 4be6438f16ddf86afdc8139491d081bcd2fce7a8
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-sign-setup-files-with-signtoolexe-clickonce"></a>Nasıl yapılır: Kurulum Dosyalarını SignTool.exe ile İmzalama (ClickOnce)
Kurulum programını (setup.exe) imzalamak için SignTool.exe kullanabilirsiniz. Bu işlem, son kullanıcı bilgisayarlarında değiştirilen dosyaların yüklü değil sağlamaya yardımcı olur.  
  
 Varsayılan olarak, bildirimler ve imzalı bir Kurulum programı ClickOnce imzaladığı. Ancak, daha sonra Kurulum programının parametrelerini değiştirmek istiyorsanız, Kurulum programı daha sonra oturum açmalısınız. Kurulum programını imzaladıktan sonra parametreleri değiştirirseniz, imza bozulur.  
  
 Aşağıdaki yordam imzalanmamış bildirimler ve imzalanmamış bir Kurulum programı oluşturur. Ardından, ClickOnce imzalama Visual Studio'da imzalı bildirimleri üretmek için etkinleştirilir. Müşteri, kendi sertifika ile yürütülebilir imzalamak program sol Kurulum imzalanmamış.  
  
### <a name="to-generate-an-unsigned-setup-program-and-sign-later"></a>İmzalanmamış bir Kurulum programı oluşturmak ve daha sonra imzalamak için  
  
1.  Geliştirme bilgisayarınızda oturum bildirimleri istediğiniz sertifikayı yükleme ile.  
  
2.  Projede seçin **Çözüm Gezgini**.  
  
3.  Üzerinde **proje** menüsünde tıklatın *ProjectName* **özellikleri**.  
  
4.  İçinde **imzalama** sayfasında, Temizle **ClickOnce bildirimlerini imzalayacak**.  
  
5.  İçinde **Yayımla** sayfasında, **Önkoşullar**.  
  
6.  Tüm Önkoşullar seçilir ve ardından doğrulamak **Tamam**.  
  
7.  İçinde **Yayımla** sayfasında, yayımlama ayarlarını doğrulayın ve ardından **Şimdi Yayımla**.  
  
     Çözüm imzalanmamış uygulama bildirimini, imzalanmamış dağıtım bildirimi, sürüme özgü dosyaları ve imzalanmamış bir Kurulum programı yayımlama klasör konumuna yayımlar.  
  
8.  İçinde **Yayımla** sayfasında, **Önkoşullar**.  
  
9. İçinde **Önkoşullar** iletişim kutusu, Temizle **Önkoşul bileşenlerini yüklemek için Kurulum programını oluşturun**.  
  
10. İçinde **Yayımla** sayfasında, yayımlama ayarlarını doğrulayın ve ardından **Şimdi Yayımla**.  
  
     Çözüm imzalı uygulama bildirimini, imzalı dağıtım bildirimini ve sürüme özgü dosyaları yayımlama klasörü konumu yayımlar. İmzalanmamış bir Kurulum programı yayımlama işlemi tarafından geçersiz kılınmaz.  
  
11. Müşteri sitesinde bir komut istemi açın.  
  
12. .Exe dosyasının bulunduğu dizine geçin.  
  
13. Aşağıdaki komutla .exe dosyasını imzalayın:  
  
    ```  
    signtool sign /sha1 CertificateHash Setup.exe  
    signtool sign /f CertFileName Setup.exe  
    ```  
  
     Örneğin, Kurulum programını imzalamak için aşağıdaki komutlardan birini kullanın:  
  
    ```  
    signtool sign /sha1 CCB... Setup.exe  
    signtool sign /f CertFileName Setup.exe  
    ```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: Uygulama ve Dağıtım Bildirimlerini Yeniden İmzalama](../deployment/how-to-re-sign-application-and-deployment-manifests.md)