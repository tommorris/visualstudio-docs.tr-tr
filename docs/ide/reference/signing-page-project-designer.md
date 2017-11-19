---
title: "İmzalama sayfası, Proje Tasarımcısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.AddNewStrongNameKey
- ResolveKeySource.KeyFileForSignAssemblyNotImported
- vb.ProjectPropertiesSigning.ChangePasswordDialog
- ResolveKeySource.KeyFileForManifestNotImported
- vb.ProjectPropertiesSigning
- vb.ProjectPropertiesSigning.PasswordNeededDialog
- vb.ProjectPropertiesSigning.PfxPasswordDialog
helpviewer_keywords:
- Project Designer, Signing page
- Signing page in Project Designer
ms.assetid: dab3ba13-2f92-4827-92bd-1be3c35bc48b
caps.latest.revision: "34"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: d193b8927019354244d6d80032ed0c761f584f83
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="signing-page-project-designer"></a>İmzalama Sayfası, Proje Tasarımcısı
Kullanım **imzalama** sayfasında **Proje Tasarımcısı** uygulama ve dağıtım bildirimlerini imzalama ve (tanımlayıcı ad imzası) derlemeyi imzalamak için.  
  
 Her iki görevi üzerinde gerçekleştirilen olsa da uygulama ve dağıtım bildirimlerini imzalama imzalama bütünleştirilmiş farklı bir işlem fark **imzalama** sayfası.  
  
 Ayrıca, anahtar dosyası bilgilerinin depolanmasını bildirim imzalama ve derleme imzalama için farklıdır. Bildirim imzalamak için anahtar bilgiler bilgisayarınızın şifreleme depolama veritabanı ve geçerli kullanıcının Windows sertifika deposunda saklanır. Derleme imzalama için anahtar bilgileri yalnızca, bilgisayarınızın şifreleme depolama veritabanında depolanır.  
  
 Erişim için **imzalama** sayfası, proje düğümü seçin **Çözüm Gezgini**ve ardından **proje** menüsünde tıklatın **özellikleri**. Zaman **Proje Tasarımcısı** görünen tıklatın **imzalama** sekmesi.  
  
## <a name="application-and-deployment-manifest-signing"></a>Uygulama ve dağıtım bildirimlerini imzalama  
 **ClickOnce bildirimlerini imzalayacak** onay kutusu  
 Bir ortak/özel anahtar çifti ile uygulama ve dağıtım bildirimlerini imzalamak için bu onay kutusunu seçin. Bunun nasıl yapılacağı hakkında daha fazla bilgi için bkz: [nasıl yapılır: oturum uygulama ve dağıtım bildirimlerini](../../ide/how-to-sign-application-and-deployment-manifests.md).  
  
 **Select deposundan** düğmesi  
 Geçerli kullanıcının kişisel sertifika depolama alanından mevcut bir sertifika seçmenize izin verir. Uygulama ve dağıtım bildirimlerini imzalamak için Bu sertifikalardan birini seçebilirsiniz.  
  
 Tıklatarak **deposundan seçmek** açılır **bir sertifika seçin** (dolmamış) şu anda geçerli olan sertifikalar, kişisel sertifika deposunda listeler ve özel anahtarları olan iletişim kutusu. Seçtiğiniz sertifikanın amacı, kod imzalama içermesi gerekir.  
  
 Tıklatırsanız **sertifika özellikleri görüntüle**, **sertifika ayrıntıları** iletişim kutusu görüntülenir. Bu iletişim kutusunu sertifika ile ilgili ayrıntılı bilgiler içerir ve ek seçenekleri içerir. Tıklayabilirsiniz **sertifikalar hakkında daha fazla bilgi** Ek Yardım bilgilerini görüntülemek için.  
  
 **Dosyadan Select** düğmesi  
 Var olan bir anahtar dosyasından bir sertifika seçmenize izin verir.  
  
 Tıklatarak **dosyasından seçin** açılır **Dosya Seç** iletişim kutusu, bir sertifika anahtarı (.pfx) dosyası seçmenize olanak sağlar. Dosya, parola korumalı ve kişisel sertifika deposunda zaten bulunamıyor olmalıdır.  
  
 İçinde **dosyayı açmak için parola gir** iletişim kutusunda, sertifika anahtarı (.pfx) dosyasını açmak için parola girin. Parola bilgilerini kişisel anahtar kapsayıcısı listenizi ve kişisel sertifika depolama alanınızda depolanır.  
  
 **Sınama sertifikası oluşturmanızı** düğmesi  
 Test etmek için bir sertifika oluşturmanıza olanak sağlar. Sınama sertifikası ClickOnce Uygulama ve dağıtım bildirimlerini imzalama için kullanılır.  
  
 Tıklatarak **Test sertifikası oluşturma** açılır **Test sertifikası oluşturma** iletişim kutusu, hangi yazabilirsiniz sınama sertifikası için güçlü ad anahtar dosyası için bir parola. Dosya adında *projectname*_TemporaryKey.pfx. Tıklatırsanız **Tamam** bir parola yazmadan .pfx dosyasını şifrelenmiş parola değil.  
  
 **Zaman damgası sunucu URL'si** kutusu  
 O zaman damgaları bir sunucu adresini belirtir imzanız. Bir sertifika sağladığınızda, bu dış site uygulamanın imzalandığı zaman doğrular.  
  
## <a name="assembly-signing"></a>Derleme imzalama  
 **Derleme imzalama** onay kutusu  
 Derlemeyi imzalamak ve kesin adlandırılmış bir anahtar dosyası oluşturmak için bu onay kutusunu seçin. Kullanarak derleme imzalama hakkında daha fazla bilgi için **Proje Tasarımcısı**, bkz: [nasıl yapılır: derleme (Visual Studio) oturum](../managing-assembly-and-manifest-signing.md#how-to-sign-an-assembly-in-visual-studio).  
  
 Bu seçenek tarafından sağlanan Al.exe aracını kullanır [! DAHİL[winsdklong](/dotnet/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name).  
  
 **Güçlü ad anahtar dosyası seçin** listesi  
 Derlemeyi imzalamak için kullanılan bir yeni veya var olan kesin adlandırılmış bir anahtar dosyası belirtmenize olanak sağlar. Seçin  **\<Gözat... >** var olan bir anahtar dosyası seçin.  
  
 Seçin  **\<yeni... >** hangi derlemeyi imzalamak yeni bir anahtar dosyası oluşturmak için. **Güçlü ad anahtarı oluştur** iletişim kutusu görüntülenirse, hangi bir anahtar dosya adı belirtin ve bir parolayla anahtarı dosyasını korumak için kullanabilirsiniz. Parola en az 6 karakter uzunluğunda olmalıdır. Parola belirtirseniz, kişisel bilgi değişimi (.pfx) dosyası oluşturulur. bir parola belirtmezseniz, kesin adlandırılmış anahtarı (.snk) dosyası oluşturulur.  
  
 **Parola Değiştir** düğmesi  
 Derlemeyi imzalamak için kullanılan kişisel bilgi değişimi (.pfx) anahtar dosyası için parolayı değiştirir.  
  
 Tıklatarak **parola değiştirme** açılır **anahtar parolasını değiştirme** iletişim kutusu. Bu iletişim kutusunda **eski parola** anahtar dosyası için geçerli bir paroladır. **Yeni parola** en az 6 karakterden uzun olmalıdır. Parola bilgileri, geçerli kullanıcının Windows sertifika deposunda depolanır.  
  
 **Gecikme yalnızca oturum** onay kutusu  
 Gecikme imzalamayı etkinleştirmek için bu onay kutusunu seçin.  
  
 Gecikme imzalı bir projeyi çalışmaz ve hata ayıklaması olamaz unutmayın. Ancak, kullanabilirsiniz [Sn.exe (tanımlayıcı ad aracı)](/dotnet/framework/tools/sn-exe-strong-name-tool) ile `-Vr` doğrulama geliştirme sırasında Atla seçeneği.  
  
> [!NOTE]
>  Bütünleştirilmiş oturum açtığınızda, her zaman özel anahtarına erişime sahip olmayabilir. Örneğin, bir kuruluş geliştiriciler günlük olarak erişim yok yakından korumalı bir anahtar çifti olabilir. Ortak anahtar kullanılamaz durumda olabilir, ancak özel anahtar erişimi için birkaç kişi sınırlıdır. Böyle bir durumda, kullandığınız *Gecikmeli* veya *kısmi imzalama* derleme kapalı karmalayan kadar özel anahtarı eklenmesi ertelemeyi ortak anahtar sağlamak için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Proje Özellikleri başvurusu](../../ide/reference/project-properties-reference.md)   
 [Derleme ve bildirim imzalamayı yönetme](../../ide/managing-assembly-and-manifest-signing.md)   
 [Tanımlayıcı ad yönetilen uygulamalar için imzalama](http://msdn.microsoft.com/en-us/5fef3490-c519-4363-94fd-8b1ad260dab5)   
 [Nasıl yapılır: uygulama ve dağıtım bildirimlerini imzalama](../../ide/how-to-sign-application-and-deployment-manifests.md)   
 [Nasıl yapılır: derleme (Visual Studio) oturum açın](../managing-assembly-and-manifest-signing.md#how-to-sign-an-assembly-in-visual-studio)   
 [Nasıl yapılır: bir derlemeyi tanımlayıcı adla imzalama](/dotnet/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name)   
 [Tanımlayıcı adlı derlemeler](/dotnet/framework/app-domains/strong-named-assemblies)   