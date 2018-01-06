---
title: "Saklı yazı tipi ve renk ayarlarını erişme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- fonts, accessing stored settings
- font and color control [Visual Studio SDK], persistence
- colors, accessing stored settings
ms.assetid: beba7174-e787-45c2-b6ff-a60f67ad4998
caps.latest.revision: "26"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: e4dec66fca6061601c4bc02389605d140ee3bb81
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="accessing-stored-font-and-color-settings"></a>Saklı yazı tipi ve renk ayarlarını erişme
[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Tümleşik geliştirme ortamı (IDE) yazı tipleri için değiştirilmiş ayarları depolar ve kayıt defterinde renkleri. Kullanabileceğiniz <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage> bu ayarlara erişmek için arabirim.  
  
## <a name="to-initiate-state-persistence-of-fonts-and-colors"></a>Yazı tipleri ve renkler durum kalıcılığı başlatmak için  
 Yazı tipi ve renk bilgileri aşağıdaki kayıt defteri konumda kategoriye göre depolanır: [HKCU\SOFTWARE\Microsoft \Visual Studio\\*\<Visual Studio sürümü >*\FontAndColors\\  *\<CategoryGUID >*] burada  *\<CategoryGUID >* GUID kategorisi.  
  
 Bu nedenle, Kalıcılık başlatmak için bir VSPackage gerekir:  
  
-   Elde bir <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage> çağırarak arabirim `QueryService` karşı genel hizmet sağlayıcısı.  
  
     `QueryService`bir hizmet kimliği bağımsız değişkeni kullanarak çağrılmalıdır `SID_SVsFontAndColorStorage` ve arabirim kimliği bağımsız değişkeninin `IID_IVsFontAndColorStorage`.  
  
-   Kullanım <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage.OpenCategory%2A> kategorinin GUID ve modu bayrağını bağımsız değişken olarak kullanarak kalıcı için bir kategori açmak için yöntem.  
  
     Tarafından belirtilen modu `fFlags` değerlerinden bağımsız değişkeni, oluşturulan <xref:Microsoft.VisualStudio.Shell.Interop.__FCSTORAGEFLAGS> numaralandırması. Bu modu denetler:  
  
    -   Üzerinden erişilen ayarları <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage> arabirimi.  
  
    -   Tüm ayarları veya yalnızca kullanıcıları değiştiren ve aracılığıyla alınabilir olan <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage> arabirimi.  
  
    -   Kullanıcı ayarlarında yapılan değişiklikler yayılıyor şekli.  
  
    -   Kullanılan renk değerleri biçimi.  
  
## <a name="to-use-state-persistence-of-fonts-and-colors"></a>Yazı tipleri ve renkler durum kalıcılığı kullanmak için  
 Kalıcı yazı tiplerini ve renkleri içerir:  
  
-   Kayıt defterinde depolanan ayarlarla IDE ayarları eşitleniyor.  
  
-   Kayıt defteri değişikliği bilgilerini yayılıyor.  
  
-   Ayarlama ve kayıt defterinde depolanan ayarları alınıyor.  
  
 Depolama ayarı ile IDE ayarları eşitleniyor büyük ölçüde saydamdır. Temel alınan IDE ayarları güncelleştirildi otomatik olarak Yazar **öğeleri görüntüleme** kayıt defteri girişleri kategoriler.  
  
 Birden çok VSPackages belirli bir kategoriye paylaşıyorsanız, bir VSPackage olaylar oluşturulur gerektirmelidir zaman yöntemlerini <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage> arabirimi depolanmış kayıt defteri ayarlarını değiştirmek için kullanılır.  
  
 Varsayılan olarak, olay oluşturma etkin değil. Olay oluşturma etkinleştirmek için bir kategori kullanarak açılmalıdır <xref:Microsoft.VisualStudio.Shell.Interop.__FCSTORAGEFLAGS>. Bu uygun çağırmak IDE neden <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorEvents> bir VSPackage uygulayan yöntemi.  
  
> [!NOTE]
>  Değişiklikleri aracılığıyla **yazı tipi ve renk** özellik sayfası oluşturma olayları bağımsız olarak <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage>. Kullanabileceğiniz <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorCacheManager> önbelleğe alınmış yazı tipi ve renk ayarlarını yönelik bir güncelleştirme yöntemleri çağrılmadan önce gerekli olup olmadığını belirlemek için arabirimi <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage> sınıfı.  
  
### <a name="storing-and-retrieving-information"></a>Depolama ve bilgileri alınıyor  
 Edinmek veya açık bir kategori adlandırılmış görüntü öğesi için bir kullanıcı değiştirebilir bilgi yapılandırmak için VSPackages çağrısı <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage.GetItem%2A> ve <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage.SetItem%2A> yöntemleri.  
  
 Yazı tipi hakkında bilgi öznitelikleri kullanarak belirli bir kategoriye elde için <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage.GetFont%2A> ve <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage.SetFont%2A> yöntemleri.  
  
> [!NOTE]
>  `fFlags` İçin geçirilen bağımsız değişken <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage.OpenCategory%2A> kategoriye açıldığında yöntemi davranışını tanımlar <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage.GetItem%2A> ve <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage.GetFont%2A> yöntemleri. Varsayılan olarak, bu yöntem yalnızca bilgisidir aboutdisplay itemsthat değişti. Ancak, bir kategori kullanarak açtıysanız <xref:Microsoft.VisualStudio.Shell.Interop.__FCSTORAGEFLAGS> bayrak, hem güncelleştirilir ve değişmeden görünen öğeleri tarafından erişilebilir <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage.GetItem%2A> ve <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage.GetFont%2A>.  
  
 Varsayılan olarak, yalnızca değiştirilen **öğeleri görüntüleme** bilgileri, kayıt defterinde tutulur. <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage> Arabirimi, yazı tipleri ve renkler için tüm ayarları almak için kullanılamaz.  
  
> [!NOTE]
>  <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage.GetItem%2A> Ve <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage.GetFont%2A> yöntemleri REGDB_E_KEYMISSING, (bilgi almak için kullanıldıklarında 0x80040152L) hakkında değişmeden döndürür **öğeleri görüntüleme**.  
  
 Tüm ayarları **öğeleri görüntüleme** belirli bir **kategori** yöntemlerini kullanarak elde edilebilir `T:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorDefaults` arabirimi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage>   
 <xref:Microsoft.VisualStudio.Shell.Interop.__FCSTORAGEFLAGS>   
 [Uygulama özel kategoriler ve öğeleri görüntüleme](../extensibility/implementing-custom-categories-and-display-items.md)