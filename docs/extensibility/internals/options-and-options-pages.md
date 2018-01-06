---
title: "Seçenekleri ve seçenekleri sayfaları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Tools Options pages [Visual Studio SDK], managed package framework support
- managed package framework, Tools Options pages support
- support, Tools Options pages
- Tools Options pages [Visual Studio SDK], layouts
- Tools Options pages [Visual Studio SDK], attributes
ms.assetid: e6c0e636-5ec3-450e-b395-fc4bb9d75918
caps.latest.revision: "34"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 1177a9a4df1f07c93540fa039117c5fa81289e17
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="options-and-options-pages"></a>Seçenekleri ve seçenekleri sayfaları
Tıklatarak **seçenekleri** üzerinde **Araçları** menüsü açılır **seçenekleri** iletişim kutusu. Bu iletişim kutusundaki seçenekler topluca seçenekleri sayfaları olarak adlandırılır. Seçenekler sayfası her kategori vardır ve gezinti bölmesindeki ağaç denetimi seçenekleri kategorileri içerir. Bir sayfa seçtiğinizde, onun seçeneklerini sağ bölmede görünür. Bu sayfa bir VSPackage durumunu belirlemek seçeneklerin değerlerini değiştirmenize olanak sağlar.  
  
## <a name="support-for-options-pages"></a>Seçenekler sayfaları için destek  
 <xref:Microsoft.VisualStudio.Shell.Package> Sınıfı seçenekleri sayfaları ve seçenekleri kategoriler oluşturmak için destek sağlar. <xref:Microsoft.VisualStudio.Shell.DialogPage> Sınıfı seçenekleri sayfasında uygular.  
  
 Varsayılan uygulaması <xref:Microsoft.VisualStudio.Shell.DialogPage> özelliklerinin genel bir kılavuz olarak kullanıcıya genel özelliklerini sunar. Bu davranış, kendi kullanıcı arabirimi (UI) sahip bir özel seçenekler sayfası oluşturmak için sayfadaki çeşitli yöntemleri geçersiz kılarak özelleştirebilirsiniz. Daha fazla bilgi için bkz: [Seçenekleri sayfası oluşturma](../../extensibility/creating-an-options-page.md).  
  
 <xref:Microsoft.VisualStudio.Shell.DialogPage> Uygulayan sınıf <xref:Microsoft.VisualStudio.Shell.IProfileManager>, seçenekleri sayfalar için ve ayrıca kullanıcı ayarları için Kalıcılık sağlar. Varsayılan uygulamaları <xref:Microsoft.VisualStudio.Shell.IProfileManager.LoadSettingsFromStorage%2A> ve <xref:Microsoft.VisualStudio.Shell.IProfileManager.SaveSettingsToStorage%2A> yöntemleri kalıcı özellik değişikliklerini kayıt defterinin bir kullanıcı bölüme özelliği için ve bir dizeden dönüştürülebilir ise.  
  
## <a name="options-page-registry-path"></a>Seçenekler sayfası kayıt defteri yolu  
 Varsayılan olarak, kayıt defteri yolunu Seçenekleri sayfası tarafından yönetilen özelliklerinin birleştirerek belirlenir <xref:Microsoft.VisualStudio.Shell.Package.UserRegistryRoot%2A>, DialogPage word ve Seçenekler sayfası sınıfı türü adı. Örneğin, bir seçenek sayfa sınıfı şu şekilde tanımlanabilir.  
  
 [!code-csharp[VSSDKSupportForOptionsPages#1](../../extensibility/internals/codesnippet/CSharp/options-and-options-pages_1.cs)]
 [!code-vb[VSSDKSupportForOptionsPages#1](../../extensibility/internals/codesnippet/VisualBasic/options-and-options-pages_1.vb)]  
  
 Varsa <xref:Microsoft.VisualStudio.Shell.Package.UserRegistryRoot%2A> özelliği ad ve değer çiftlerini HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\8.0Exp\DialogPage\ alt anahtarlarını sonra HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\8.0Exp, değil Company.OptionsPage.OptionsPageGeneral.  
  
 Seçenekler sayfası kayıt defteri yolunu birleştirerek belirlenir <xref:Microsoft.VisualStudio.Shell.Package.ApplicationRegistryRoot%2A>, word, ToolsOptionsPages ve seçenekleri sayfasında kategori ve adı. Örneğin, özel seçenekleri sayfasında kategori, My seçenek sayfaları varsa ve <xref:Microsoft.VisualStudio.Shell.Package.ApplicationRegistryRoot%2A> seçenekleri sayfasında HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ kayıt defteri anahtarına sahip HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\8.0Exp, olduğundan VisualStudio\8.0Exp\ToolsOptionsPages\My seçeneği Pages\Custom.  
  
## <a name="toolsoptions-page-attributes-and-layout"></a>Araçlar/Seçenekler sayfası öznitelikleri ve düzeni  
 <xref:Microsoft.VisualStudio.Shell.ProvideOptionPageAttribute> Özniteliği belirler özel seçenekleri sayfaları gruplandırma Gezinti ağacında kategorilere **seçenekleri** iletişim kutusu. <xref:Microsoft.VisualStudio.Shell.ProvideOptionPageAttribute> Özniteliği seçenekleri sayfasında arabirimi sağlayan VSPackage ile ilişkilendirir. Aşağıdaki kod parçası göz önünde bulundurun:  
  
 [!code-csharp[VSSDKSupportForOptionsPages#2](../../extensibility/internals/codesnippet/CSharp/options-and-options-pages_2.cs)]
 [!code-vb[VSSDKSupportForOptionsPages#2](../../extensibility/internals/codesnippet/VisualBasic/options-and-options-pages_2.vb)]  
  
 Bu, MyPackage iki seçenekleri sayfaları, OptionsPageGeneral ve OptionsPageCustom sağlar bildirir. İçinde **seçenekleri** iletişim kutusunda, her iki seçenek sayfa görünür **My seçenek sayfaları** kategori olarak **genel** ve **özel**sırasıyla.  
  
## <a name="option-attributes-and-layout"></a>Seçenek öznitelikleri ve düzeni  
 Sayfa sağlayan kullanıcı arabirimi (UI) bir özel seçenekler sayfası seçeneklerinde görünümünü belirler. Düzen, etiketleme ve bir genel seçenekleri sayfasında seçeneklerinin açıklaması aşağıdaki özniteliklere göre belirlenir:  
  
-   <xref:System.ComponentModel.CategoryAttribute>seçenek kategorisini belirler.  
  
-   <xref:System.ComponentModel.DisplayNameAttribute>seçenek görünen adını belirler.  
  
-   <xref:System.ComponentModel.DescriptionAttribute>seçenek açıklaması belirler.  
  
    > [!NOTE]
    >  Eşdeğer öznitelikleri, SRCategory, LocDisplayName ve SRDescription, yerelleştirme için dize kaynaklarını kullanın ve içinde tanımlanan [yönetilen projenin örnek](http://go.microsoft.com/fwlink/?LinkId=122774).  
  
 Aşağıdaki kod parçası göz önünde bulundurun:  
  
 [!code-csharp[VSSDKSupportForOptionsPages#3](../../extensibility/internals/codesnippet/CSharp/options-and-options-pages_3.cs)]
 [!code-vb[VSSDKSupportForOptionsPages#3](../../extensibility/internals/codesnippet/VisualBasic/options-and-options-pages_3.vb)]  
  
 OptionInteger seçeneği seçenekleri sayfasında görünür **tamsayı seçeneği** içinde **My seçenekleri** kategorisi. Seçeneğini belirlediyseniz, açıklama **benim tamsayı seçeneğini**, Açıklama kutusuna görüntülenir.  
  
## <a name="accessing-options-pages-from-another-vspackage"></a>Başka bir VSPackage erişilirken seçenekleri sayfaları  
 Barındıran ve Seçenekler sayfası yöneten bir VSPackage, otomasyon modeli kullanarak başka bir VSPackage programlı olarak erişilebilir. Örneğin, aşağıdaki kodda bir VSPackage bir seçenek sayfası barındırma olarak kayıtlı.  
  
 [!code-csharp[VSSDKSupportForOptionsPages#4](../../extensibility/internals/codesnippet/CSharp/options-and-options-pages_4.cs)]
 [!code-vb[VSSDKSupportForOptionsPages#4](../../extensibility/internals/codesnippet/VisualBasic/options-and-options-pages_4.vb)]  
  
 Aşağıdaki kod parçası, MyOptionPage OptionInteger değerini alır:  
  
 [!code-csharp[VSSDKSupportForOptionsPages#5](../../extensibility/internals/codesnippet/CSharp/options-and-options-pages_5.cs)]
 [!code-vb[VSSDKSupportForOptionsPages#5](../../extensibility/internals/codesnippet/VisualBasic/options-and-options-pages_5.vb)]  
  
 Zaman <xref:Microsoft.VisualStudio.Shell.ProvideOptionPageAttribute> özniteliği kaydeder seçenekleri sayfasında, sayfanın altında AutomationProperties anahtar IF kayıtlı `SupportsAutomation` öznitelik bağımsız değişkeni `true`. Otomasyon ilişkili VSPackage ve Otomasyon bulmak için bu kayıt defteri girdisi inceler sonra barındırılan seçenekler sayfası, bu durumda, kılavuz sayfam özelliğe erişir.  
  
 Kayıt defteri yolunu Otomasyon özelliğinin birleştirerek belirlenir <xref:Microsoft.VisualStudio.Shell.Package.ApplicationRegistryRoot%2A>, word, AutomationProperties ve seçenekleri sayfasında kategori ve adı. Seçenekler sayfası My kategorisi kategori, kılavuz sayfam adı varsa, örneğin ve <xref:Microsoft.VisualStudio.Shell.Package.ApplicationRegistryRoot%2A>, HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\8.0Exp sonra Otomasyon özelliğine sahip HKEY_LOCAL_MACHINE\SOFTWARE\ bir kayıt defteri anahtarı Microsoft\VisualStudio\8.0Exp\AutomationProperties\My Category\My kılavuz sayfası.  
  
> [!NOTE]
>  Kurallı Category.My kılavuz sayfam, bu anahtarın adı alt anahtarının değerini adıdır.