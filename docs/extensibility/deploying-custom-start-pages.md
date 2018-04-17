---
title: Özel başlangıç sayfalarını dağıtma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- package start page
- deploy start page
ms.assetid: 4a7eb360-de83-41d5-be53-3cfb160d19f9
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 6110be404ec7de9b52aef23fc9d1d77d1ae7e2c3
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="deploying-custom-start-pages"></a>Özel başlangıç sayfalarını dağıtma
Özel başlangıç sayfaları VSIX dağıtım kullanarak veya hedef bilgisayarda doğru konumlara dosyaları kopyalayarak dağıtabilirsiniz.  
  
## <a name="vsix-deployment-by-using-the-start-page-project-template"></a>Başlangıç sayfası proje şablonunu kullanarak VSIX dağıtım  
 Başlangıç sayfası proje şablonu kullanarak bir başlangıç sayfası oluşturun ve projeyi oluşturmak, Visual Studio dağıtabileceğiniz bir .vsix dosyası oluşturur. Bir başlangıç sayfası .vsix dosyasında paketleme, hedef kitle bağlı olarak dağıtım için aşağıdaki seçenekleri sağlar:  
  
-   Bir ağ paylaşımına veya ortak bir Web sitesine .vsix dosya yerleştirebilirsiniz. Başlangıç sayfası, birisi dosya açıldığında otomatik olarak yüklenir.  
  
-   .Vsix dosyasını karşıya yükleyebilir [Visual Studio Galerisi](http://go.microsoft.com/fwlink/?LinkID=123847) Web sitesi kullanıcıların bunu kullanarak yükleyebilirsiniz **Uzantı Yöneticisi**.  
  
 Başlangıç sayfası proje şablonu kopyalama değiştirebilir ve özgün korumak Visual Studio Başlangıç sayfası varsayılan bir kopyasını oluşturur.  
  
 Başlangıç sayfası proje şablonu kullanarak elde edebilirsiniz **Uzantı Yöneticisi** veya Web sitesinden yükleyerek.  
  
## <a name="vsix-deployment-without-using-the-start-page-project-template"></a>Başlangıç sayfası proje şablonunu kullanarak olmadan VSIX dağıtım  
 Başarılı bir VSIX dağıtım uzantı kullanarak ve VSIX kayıt işlemi tarafından tanınan klasörlerde yüklü olmasını gerektirir **Uzantı Yöneticisi**. Başlangıç sayfası proje şablonu doğru klasörleri belirttiğinden, VSIX dağıtım için bir uzantı paketini istediğinizde bunu kullanmanızı öneririz. Ancak, şablonu kullanamıyor bir durum varsa, bunu kullanmadan VSIX dağıtım oluşturabilirsiniz.  
  
 Başlangıç sayfası proje şablonu kullanmadan VSIX dağıtımı oluşturmak için önce bu iki yöntemden biriyle başlangıç sayfası için bir .vsix dosyası oluşturun:  
  
-   Boş bir VSIX proje özel başlangıç sayfası dosyalarınızı ekleyerek. Daha fazla bilgi için bkz: [VSIX proje şablonu](../extensibility/vsix-project-template.md).  
  
-   .Vsix dosyasını el ile oluşturarak. .Vsix dosyasını el ile oluşturmak için:  
    
    1.  Extension.vsixmanifest dosyasını ve [Content_Types] .xml dosyasını yeni bir klasör oluşturun. Daha fazla bilgi için bkz: [VSIX paketi anatomisi](/visualstudio/extensibility/anatomy-of-a-vsix-package).  
  
    2.  Windows Gezgini'nde, iki XML dosyasını içeren klasörü sağ tıklatın, göndermek için tıklatın ve ardından sıkıştırılmış klasörü tıklatın. Sonuçta elde edilen .zip dosyasını Filename yükler ve paketinizi yeniden dağıtılabilir dosyasının adı olduğu Filename.vsix için yeniden adlandırın.  
  
 Bir başlangıç sayfası tanımak Visual Studio için `Content Element` VSIX bildirim içermesi gereken bir `CustomExtension Element` olan `Type` özniteliği kümesine `"StartPage"`. VSIX dağıtımı kullanarak yüklü bir başlangıç sayfası uzantısı görünür **başlangıç sayfasını özelleştirme** listesini **başlangıç** seçenekleri sayfasında olarak **[uzantısı yüklü]** *Uzantı adı*.  
  
 Başlangıç sayfası paketinizi derlemeleri içeriyorsa, böylece Visual Studio başladığında kullanılabilir olmaları bağlama yolu kayıt eklemeniz gerekir. Bunu yapmak için paketinizi aşağıdaki bilgileri içeren bir .pkgdef dosyası içerdiğinden emin olun.  
  
```  
[$RootKey$\BindingPaths\{Insert a new GUID here}]  
"$PackageFolder$"=""  
```  
  
### <a name="vsix-deployment-for-all-users"></a>Tüm kullanıcılar için VSIX dağıtım  
 Varsayılan olarak, yalnızca geçerli kullanıcı için VSIX paket dağıtılan uzantıları yükleyin. Tüm kullanıcıların dağıtım oluşturarak hedef makinenin tüm kullanıcıları için bir başlangıç sayfası yükleme yapabilirsiniz.  
  
##### <a name="to-create-an-all-users-deployment"></a>Tüm kullanıcılar dağıtımı oluşturmak için  
  
1.  Kod görünümünde extension.vsixmanifest dosyasını açın.  
  
2.  İçinde `Identifier` VSIX bildiriminin öğesi Ekle bir `AllUsers` değerine sahip olan öğe `true`.  
  
    ```  
    <AllUsers>true</AllUsers>  
    ```  
  
     Bu için yönetici izinleri ister ve ardından dosyaları için \Common7\IDE\Extensions yüklemek VSIX yükleyici neden olur.  
  
3.  .Pkgdef dosyasını açın.  
  
4.  Varsayılan başlangıç sayfası HKLM altında aşağıdakileri ekleyerek ayarlamak için .pkgdef değiştirme nerede *MyStartPage.xaml* başlangıç sayfanızı içeren .xaml dosyasının adıdır.  
  
     [$RootKey$ \StartPage\Default]  
  
     "URI"="$PackageFolder$\\*MyStartPage.xaml*"  
  
     Bu yeni başlangıç sayfası konumu aramak için görsel Stood bildirir.  
  
## <a name="file-copy-deployment"></a>Dosya kopyası dağıtımını  
 Özel bir başlangıç sayfası dağıtmak için bir .vsix dosyası oluşturmak zorunda değildir. Bunun yerine, biçimlendirme ve destekleyici dosyaları doğrudan kullanıcının \StartPages\ klasöre kopyalayabilirsiniz. **Başlangıç sayfasını özelleştirme** listesini **başlangıç** Seçenekleri sayfası listeler yolu ile birlikte o klasördeki her .xaml dosyasında — Örneğin, %USERPROFILE%\My Documents\Visual Studio  *Sürüm*\StartPages\\*dosya adı*.xaml. Başlangıç sayfası özel derlemeler başvurular içeriyorsa, onları kopyalayın ve \PrivateAssemblies\ klasöre yapıştırın.  
  
 Bir başlangıç olmadan paketleme oluşturduğunuz sayfası dağıtmak için bir .vsix dosyası içinde öneririz temel dosya kopyalama stratejiyi kullanın, örneğin, bir toplu betik ya da olanak sağlayan herhangi bir dağıtım teknolojisi gerekli dizinler dosyaları yerleştirin.  
  
#### <a name="to-manually-install-a-custom-start-page"></a>Özel bir başlangıç sayfası el ile yüklemek için  
  
1.  Derlemeler, dışındaki tüm destekleyici dosyaları ile birlikte Başlangıç sayfası biçimlendirmesini içeren .xaml dosyasını kopyalayın ve kullanıcının \StartPages\ klasöre yapıştırın.  
  
2.  Başlangıç sayfası derlemeleri gerektiriyorsa, bunları kopyalayıp bunları... \\ *Visual Studio yükleme klasörü*\Common7\IDE\PrivateAssemblies\\.  
  
3.  İçinde **başlangıç sayfasını özelleştirme** listesini **başlangıç** seçenekleri sayfasında, yeni başlangıç sayfası seçin. Daha fazla bilgi için bkz: [başlangıç sayfasını özelleştirme](../ide/customizing-the-start-page-for-visual-studio.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başlangıç sayfasını özelleştirme](../ide/customizing-the-start-page-for-visual-studio.md)   
 [Başlangıç Sayfasına Kullanıcı Denetimi Ekleme](../extensibility/adding-user-control-to-the-start-page.md)