---
title: Oluşturma seçenekleri sayfaları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- managed package framework, creating Tools Options pages
- Tools Options pages [Visual Studio SDK], creating using managed package framework
ms.assetid: 1bf11fec-dece-4943-8053-6de1483c43eb
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 51e05c5f2660adfe8d7a35c816e5f94706631c8f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="creating-options-pages"></a>Seçenekler sayfası oluşturma
İçinde [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] yönetilen paket framework türetilmiş sınıfları <xref:Microsoft.VisualStudio.Shell.DialogPage> genişletmek [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ekleyerek IDE **seçenekleri** altında sayfaları **Araçları** menüsü.  
  
 Bir nesne uygulama bir verilen **araçları seçeneğini** sayfasıdır tarafından belirli VSPackages ilişkilendirilmiş <xref:Microsoft.VisualStudio.Shell.ProvideOptionPageAttribute> nesnesi.  
  
 Belirli bir uygulama nesnesi ortamı başlatır çünkü **Araçlar Seçenekler** sayfasında belirli bu sayfa tarafından IDE görüntülendiğinde:  
  
-   A **araçları seçeneğini** sayfa uygulanan kendi nesnesi ve bir VSPackage uygulama nesnesi değil.  
  
-   Bir nesne birden çok uygulayamaz **Araçlar Seçenekler** sayfaları.  
  
## <a name="registering-as-a-tools-options-page-provider"></a>Araçlar Seçenekler sayfası sağlayıcısı kaydetme  
 Bir VSPackage destekleyen kullanıcı yapılandırması üzerinden **Araçlar Seçenekler** sayfaları bu sağlama nesneleri gösterir **Araçlar Seçenekler** örneklerini uygulayarak sayfaları <xref:Microsoft.VisualStudio.Shell.ProvideOptionPageAttribute> uygulanan<xref:Microsoft.VisualStudio.Shell.Package>uygulaması.  
  
 Bir örneği olmalıdır <xref:Microsoft.VisualStudio.Shell.ProvideOptionPageAttribute> için her <xref:Microsoft.VisualStudio.Shell.DialogPage>-uygulayan tür türetilmiş bir **Araçlar Seçenekler** sayfası.  
  
 Her örneği <xref:Microsoft.VisualStudio.Shell.ProvideOptionPageAttribute> uygulayan bir tür kullanıyor **Araçlar Seçenekler** sayfası, kategori ve tanımlamak için kullanılan alt kategori içeren dizeleri bir **Araçlar Seçenekler** sayfası ve kaynak bilgi türü sağlayarak olarak kaydetmek için bir **Araçlar Seçenekler** sayfası.  
  
## <a name="persisting-tools-options-page-state"></a>Kalıcı Araçlar Seçenekler Sayfa durumu  
 Varsa bir **Araçlar Seçenekler** sayfa uygulaması Otomasyon desteğinin etkinleştirildiği kayıtlı, diğer tüm birlikte sayfanın durumu IDE devam **Araçlar Seçenekler** sayfaları.  
  
 Bir VSPackage kullanarak kendi Kalıcılık yönetebilirsiniz <xref:Microsoft.VisualStudio.Shell.ProvideProfileAttribute>. Yalnızca bir ya da kalıcılığı diğer yöntemi kullanılmalıdır.  
  
## <a name="implementing-dialogpage-class"></a>Uygulama DialogPage sınıfı  
 VSPackage'nın uyarlamasını sağlayan bir nesne bir <xref:Microsoft.VisualStudio.Shell.DialogPage>-türetilen tür yararlanabilir aşağıdaki devralınan özellikler:  
  
-   Varsayılan kullanıcı arabirimi penceresi.  
  
-   Bir varsayılan Kalıcılık mekanizması kullanılabilir ya da Eğer <xref:Microsoft.VisualStudio.Shell.ProvideProfileAttribute> sınıfına uygulanan veya <xref:Microsoft.VisualStudio.Shell.ProvideOptionPageAttribute.SupportsProfiles%2A> özelliği ayarlanmış `true` için <xref:Microsoft.VisualStudio.Shell.ProvideOptionPageAttribute> sınıfa uygulanır.  
  
-   Otomasyon desteği.  
  
 Bir nesne uygulamak için en düşük gereksinim bir **Araçlar Seçenekler** kullanarak sayfa <xref:Microsoft.VisualStudio.Shell.DialogPage> ortak özellikler ektir.  
  
 Sınıf düzgün olarak kayıtlı bir **Araçlar Seçenekler** ortak özelliklerini kullanılabilir sonra sağlayıcısı, sayfa **seçenekleri** bölümünü **Araçları** menü biçiminde bir Özellik Kılavuzu.  
  
 Bu varsayılan özellikleri geçersiz kılınabilir. Örneğin, daha karmaşık bir kullanıcı oluşturmak için arabirimi yalnızca varsayılan uygulamasını geçersiz kılma gerektirir <xref:Microsoft.VisualStudio.Shell.DialogPage.Window%2A>.  
  
## <a name="example"></a>Örnek  
 Aşağıda bir basit "hello world" Seçenekler sayfası uygulamasıdır. Visual Studio Paketi şablonla tarafından oluşturulan varsayılan projeye aşağıdaki kod ekleme **menü komutu** seçeneğe yeterli seçeneği sayfası işlevselliğini göstermektedir.  
  
### <a name="description"></a>Açıklama  
 Aşağıdaki sınıf en az bir "hello world" Seçenekler sayfası tanımlar. Açıldığında, kullanıcının ortak ayarlayıp `HelloWorld` özelliği bir özellik kılavuzunda.  
  
### <a name="code"></a>Kod  
 [!code-csharp[UI_UserSettings_ToolsOptionPages#11](../../extensibility/internals/codesnippet/CSharp/creating-options-pages_1.cs)]
 [!code-vb[UI_UserSettings_ToolsOptionPages#11](../../extensibility/internals/codesnippet/VisualBasic/creating-options-pages_1.vb)]  
  
### <a name="description"></a>Açıklama  
 Paket yüklediğinde, aşağıdaki öznitelik paketi sınıfına uygulayarak sayfasında seçenekleri kullanılabilir hale getirir. Kategori ve sayfa için rasgele kaynak kimlikleri numaralarıdır ve sonunda Boole değeri sayfa Otomasyon destekleyip desteklemediğini belirtir.  
  
### <a name="code"></a>Kod  
 [!code-csharp[UI_UserSettings_ToolsOptionPages#07](../../extensibility/internals/codesnippet/CSharp/creating-options-pages_2.cs)]
 [!code-vb[UI_UserSettings_ToolsOptionPages#07](../../extensibility/internals/codesnippet/VisualBasic/creating-options-pages_2.vb)]  
  
### <a name="description"></a>Açıklama  
 Aşağıdaki olay işleyicisini seçenekleri sayfasında özellik değerine bağlı olarak sonucunu görüntüler. Kullandığı <xref:Microsoft.VisualStudio.Shell.Package.GetDialogPage%2A> sonucu yöntemiyle açıkça cast sayfa tarafından kullanıma sunulan özelliklere erişmek için özel seçeneği sayfa türü.  
  
 Paket şablon tarafından oluşturulan proje söz konusu olduğunda, bu işlevden çağırma `MenuItemCallback` işlevi için varsayılan komut eklemek için eklenen **Araçları** menüsü.  
  
### <a name="code"></a>Kod  
 [!code-csharp[UI_UserSettings_ToolsOptionPages#08](../../extensibility/internals/codesnippet/CSharp/creating-options-pages_3.cs)]
 [!code-vb[UI_UserSettings_ToolsOptionPages#08](../../extensibility/internals/codesnippet/VisualBasic/creating-options-pages_3.vb)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Genişletme kullanıcı ayarları ve seçenekleri](../../extensibility/extending-user-settings-and-options.md)   
 [Seçenekler Sayfaları için Otomasyon Desteği](../../extensibility/internals/automation-support-for-options-pages.md)