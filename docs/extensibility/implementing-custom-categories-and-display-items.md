---
title: "Özel kategoriler ve öğeleri görüntüleme uygulama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- font and color control [Visual Studio SDK], categories
- custom categories
ms.assetid: 99311a93-d642-4344-bbf9-ff6e7fa5bf7f
caps.latest.revision: "25"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: f03dbae8b320161705c50da06d605cfc335074cc
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="implementing-custom-categories-and-display-items"></a>Uygulama özel kategoriler ve öğeleri görüntüleme
Bir VSPackage denetim yazı tiplerini ve renkleri, metin sağlayabilir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] özel kategoriler ve öğeleri görüntüleme aracılığıyla tümleşik geliştirme ortamı (IDE).  
  
 Özel alanlar ve görüntü öğeler olan **yazı tiplerini ve renkleri** özellik sayfası. Açmak için **yazı tiplerini ve renkleri** özellik sayfasında **Araçları** menüsünde tıklatın **seçenekleri**. Genişletme **ortam** ve ardından **yazı tiplerini ve renkleri**.  
  
 Bu mekanizma kullanırken, VSPackages uygulamalıdır <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorDefaultsProvider> ve onun ilişkili arabirim.  
  
 Var olan tüm değiştirmek için bu düzenek kullanılabilir temelde **görüntülemek öğeleri** ve **kategorileri** bunları içeren. Ancak, bunu değiştirmek için kullanılmamalıdır **metin EditorCategory** veya kendi **görüntülemek öğeleri**. Daha fazla bilgi için bkz: [yazı tipi ve renk genel bakış](../extensibility/font-and-color-overview.md).  
  
 Özel uygulamak için **kategorileri** veya **görüntülemek öğeleri**, bir VSPackage gerekir:  
  
-   Oluşturun veya kayıt defterinde kategorileri belirleyin.  
  
     IDE'nin uyarlamasını **yazı tiplerini ve renkleri** özellik sayfasında belirtilen kategori destekleyen hizmeti için doğru bir şekilde sorgulamak için bu bilgileri kullanır.  
  
-   Oluşturma veya kayıt defterinde grupları (isteğe bağlı) tanımlama.  
  
     İki veya daha fazla kategoriye birleşimi temsil eden bir grup tanımlamak yararlı olabilir. Bir grup tanımlanırsa, IDE otomatik olarak alt kategorileri birleştirir ve grup içindeki öğeleri görüntüleme dağıtır.  
  
-   IDE desteği uygulayın.  
  
-   Yazı tipi ve renk değişiklikleri işleyin.  
  
 Bilgi için bkz: [erişme depolanan yazı tipi ve renk ayarlarını](../extensibility/accessing-stored-font-and-color-settings.md).  
  
## <a name="to-create-or-identify-categories"></a>Oluşturma veya kategorileri tanımlamak için  
  
-   Özel türde bir kategori kayıt defteri girişi altında oluşturmak [HKLM\SOFTWARE\Microsoft \Visual Studio\\*\<Visual Studio sürümü >*\FontAndColors\\`<Category>`]  
  
     *\<Kategori >* kategorisi yerelleştirilmemiş adıdır.  
  
-   Kayıt defteri iki değerlerle doldurun:  
  
    |Ad|Tür|Veri|Açıklama|  
    |----------|----------|----------|-----------------|  
    |Kategori|REG_SZ|GUID|Kategori tanımlamak için oluşturulmuş bir GUID.|  
    |Paket|REG_SZ|GUID|Kategori destekleyen VSPackage hizmet GUID.|  
  
 Kayıt defterinde belirtilen hizmet uygulaması sağlamalısınız <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorDefaults> karşılık gelen bir kategorisi için.  
  
## <a name="to-create-or-identify-groups"></a>Gruplar oluşturma veya tanımlamak için  
  
-   Özel türde bir kategori kayıt defteri girişi altında oluşturmak [HKLM\SOFTWARE\Microsoft \Visual Studio\\*\<Visual Studio sürümü >*\FontAndColors\\  *\<grup >*]  
  
     *\<Grup >* yerelleştirilmemiş grubunun adıdır.  
  
-   Kayıt defteri iki değerlerle doldurun:  
  
    |Ad|Tür|Veri|Açıklama|  
    |----------|----------|----------|-----------------|  
    |Kategori|REG_SZ|GUID|Grubu tanımlamak için oluşturulmuş bir GUID.|  
    |Paket|REG_SZ|GUID|Kategori destekleyen hizmet GUID.|  
  
 Kayıt defterinde belirtilen hizmet uygulaması sağlamalısınız `T:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorGroup` ilgili grup.  
  
## <a name="to-implement-ide-support"></a>IDE desteği uygulamak için  
  
-   Uygulama <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorDefaultsProvider.GetObject%2A>, ya da döndüren bir <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorDefaults> arabirimi veya bir `T:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorGroup` IDE her arabirime **kategori** veya GUID sağlanmış grup.  
  
-   İçin her **kategori** destekliyorsa, ayrı bir örneğini bir VSPackage uygulayan <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorDefaults> arabirimi.  
  
-   Yöntemleri aracılığıyla uygulanan <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorDefaults> IDE ile sağlamanız gerekir:  
  
    -   Listesini **görüntülemek öğeleri** içinde **kategorisi.**  
  
    -   Yerelleştirilebilir adlarını **görüntülemek öğeleri**.  
  
    -   Her bir üyesi için görüntüleme bilgileri **kategori**.  
  
    > [!NOTE]
    >  Her **kategori** en az birini içermelidir **görüntü öğesi**.  
  
-   IDE kullanan `T:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorGroup` birkaç kategorisi birleşimini tanımlamak için arabirim.  
  
     Kendi uygulama ile bir IDE sağlar:  
  
    -   Listesini **kategorileri** verilen bir grup oluşturur.  
  
    -   Örneklerini erişimi <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorDefaults> her destekleyen **kategori** grup içinde.  
  
    -   Yerelleştirilebilir grup adları.  
  
-   IDE güncelleştiriliyor:  
  
     IDE hakkında bilgileri önbelleğe alır **yazı tipi ve renk** ayarlar. Bu nedenle, herhangi bir değişikliği IDE sonra **yazı tipi ve renk** yapılandırması, bu önbelleği güncel olduğundan emin olmak için önerilir.  
  
 Önbelleği güncelleştiriliyor aracılığıyla yapılır <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorCacheManager> arabirim ve gerçekleştirilen genel olarak veya yalnızca üzerinde seçili öğeleri olabilir.  
  
## <a name="to-handle-font-and-color-changes"></a>Yazı tipi ve renk işlemek için değiştirir  
 Düzgün bir VSPackage görüntülenen metin renklendirme desteklemek için VSPackage destekleyen renklendirme hizmeti aracılığıyla kullanıcı tarafından başlatılan değişikliklerinin yanıt gerekir **yazı tiplerini ve renkleri** Özellikler sayfası. Bir VSPackage bunu şu şekilde yapar:  
  
-   Uygulayarak IDE tarafından oluşturulan olayları işleme <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorEvents> arabirimi.  
  
     IDE kullanıcı değişiklik aşağıdaki uygun yöntemi çağırır **yazı tiplerini ve renkleri** sayfası. Örneğin, çağıran <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorEvents.OnFontChanged%2A> yeni bir yazı tipi seçtiyseniz yöntemi.  
  
     veya  
  
-   IDE değişiklikleri için yoklanıyor.  
  
     Bu sistem uygulanan yapılabilir <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage> arabirimi. Öncelikle desteği için Kalıcılık, ancak <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage.GetItem%2A> yöntemi, yazı tipi ve renk bilgilerini elde etmek için kullanılabilir **görüntülemek öğeleri**. Daha fazla bilgi için bkz: [erişme depolanan yazı tipi ve renk ayarlarını](../extensibility/accessing-stored-font-and-color-settings.md).  
  
    > [!NOTE]
    >  Yoklama tarafından elde edilen sonuçlar doğru, kullanmak yararlı olabilir emin olmak için <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorCacheManager> önbellek temizleme ve güncelleştirme alma yöntemlerini çağırmadan önce gerekli olup olmadığını belirlemek için arabirimi <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage> arabirimi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider.QueryService%2A>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorDefaults>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorEvents>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorGroup>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorDefaultsProvider>   
 [Yazı tipi ve metin renklendirme için renk bilgilerini alma](../extensibility/getting-font-and-color-information-for-text-colorization.md)   
 [Saklı yazı tipi ve renk ayarlarını erişme](../extensibility/accessing-stored-font-and-color-settings.md)   
 [Nasıl yapılır: yerleşik yazı tipleri ve renk düzenini erişim](../extensibility/how-to-access-the-built-in-fonts-and-color-scheme.md)   
 [Yazı tipi ve renk genel bakış](../extensibility/font-and-color-overview.md)