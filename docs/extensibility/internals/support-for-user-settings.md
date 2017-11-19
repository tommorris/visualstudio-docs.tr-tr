---
title: "Kullanıcı ayarları desteği | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Custom Settings Points
- user settings [Visual Studio SDK], registering persistence support
- persistence, registering settings
ms.assetid: ad9beac3-4f8d-4093-ad0e-6fb00444a709
caps.latest.revision: "26"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 8d25243c82cbb1facc4029e1a770113a7b1fca57
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="support-for-user-settings"></a>Kullanıcı ayarları desteği
Bir VSPackage grupları bir kullanıcı seçtiğinde kalıcı durum değişkenleri, bir veya daha fazla ayarları kategorileri tanımlayabilir **içeri/dışarı aktarma ayarları** komutunu **Araçları** menüsü. Bu Kalıcılık etkinleştirmek için ayarları API'leri kullanın, [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)].  
  
 İçin bir özel ayarlar ve bir GUID adlandırılan bir kayıt defteri girdisi VSPackage'nın ayarları kategorisi tanımlar. Bir VSPackage birden çok ayar kategorileri destekleyebilen, her bir özel ayarları noktası tarafından tanımlanan.  
  
-   Birlikte çalışma derlemelerini temel ayarları uygulamaları (kullanarak <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserSettings> arabirimi) özel ayarları noktası kayıt defterini düzenleme veya Kaydedici betik (.rgs dosyası) kullanarak oluşturmanız gerekir. Daha fazla bilgi için bkz: [oluşturma Kaydedici betikleri](/cpp/atl/creating-registrar-scripts).  
  
-   Yönetilen paket Framework (MPF) kullanan kodu oluşturmak özel ayarları noktaları ekleyerek bir <xref:Microsoft.VisualStudio.Shell.ProvideProfileAttribute> her özel ayarları noktası VSPackage için.  
  
     Her özel ayarları noktası ayrı bir sınıf tarafından uygulanır ve her benzersiz bir örneği tarafından kaydedilen çeşitli özel ayarları noktalar tek VSPackage destekliyorsa <xref:Microsoft.VisualStudio.Shell.ProvideProfileAttribute> sınıfı. Sonuç olarak, sınıf uygulama ayarlarını birden fazla ayarları kategorisi destekleyebilir.  
  
## <a name="custom-settings-point-registry-entry-details"></a>Özel ayarlar noktası kayıt defteri girişi ayrıntıları  
 Özel ayarlar noktaları bir kayıt defteri girişi aşağıdaki konumda oluşturulur: HKLM\Software\Microsoft\VisualStudio\\*\<sürüm >*\UserSettings\\`<CSPName>`, burada `<CSPName>` VSPackage destekler özel ayarları noktası adıdır ve  *\<sürüm >* sürümü [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], örneğin 8.0.  
  
> [!NOTE]
>  HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio kök yolunu\\*\<sürüm >* alternatif ile geçersiz kılınabilir ne zaman kök [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] tümleşik geliştirme ortamı (IDE) başlatıldı. Daha fazla bilgi için bkz: [komut satırı anahtarları](../../extensibility/command-line-switches-visual-studio-sdk.md).  
  
 Kayıt defteri girdisinin yapısı aşağıda gösterilmiştir:  
  
 HKLM\Software\Microsoft\VisualStudio\\*\<sürüm >*\UserSettings\  
  
 `<CSPName`> = '#12345' s  
  
 Paket '{XXXXXX XXXX XXXX XXXX XXXXXXXXX}' =  
  
 Kategori = '{YYYYYY YYYY YYYY YYYY YYYYYYYYY}'  
  
 ResourcePackage = '{ZZZZZZ ZZZZ ZZZZ ZZZZ ZZZZZZZZZ}'  
  
 AlternateParent CategoryName =  
  
|Ad|Tür|Veri|Açıklama|  
|----------|----------|----------|-----------------|  
|(Varsayılan)|REG_SZ|Özel ayarlar noktasının adı|Anahtarın adı `<CSPName`>, özel ayarları noktası yerelleştirilmemiş adıdır.<br /><br /> Üzerinde MPF tabanlı uygulamalar için anahtarın adı birleştirerek elde edilen `categoryName` ve `objectName` bağımsız <xref:Microsoft.VisualStudio.Shell.ProvideProfileAttribute> oluşturucuya `categoryName_objectName`.<br /><br /> Anahtar boş olabilir veya bir uydu DLL yerelleştirilmiş dize başvuru Kimliğine içerebilir. Bu değer elde edilir `objectNameResourceID` bağımsız değişkeni <xref:Microsoft.VisualStudio.Shell.ProvideProfileAttribute> Oluşturucusu.|  
|Paket|REG_SZ|GUID|Özel ayarlar noktası uygulayan VSPackage GUID.<br /><br /> Uygulamaları dayalı MPF kullanarak <xref:Microsoft.VisualStudio.Shell.ProvideProfileAttribute> sınıfı, oluşturucu 's kullanın `objectType` VSPackage's içeren bağımsız değişkeni <xref:System.Type> ve bu değeri elde etmek için yansıma.|  
|Kategori|REG_SZ|GUID|Ayarları kategorisini tanımlayan GUID.<br /><br /> Birlikte çalışma derlemelerini tabanlı uygulamalar için bu değer rastgele seçilen olabilir GUID, hangi [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE geçtiği <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserSettings.ExportSettings%2A> ve <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserSettings.ImportSettings%2A> yöntemleri. Bu iki yöntem, tüm uygulamaları, kendi GUID bağımsız değişkenleri doğrulamanız gerekir.<br /><br /> Üzerinde MPF tabanlı uygulamalar için bu GUID'i tarafından elde edilen <xref:System.Type> sınıfı uygulama [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ayarları mekanizması.|  
|ResourcePackage|REG_SZ|GUID|İsteğe bağlı.<br /><br /> Uygulama VSPackage bunları sağlayamıyorsa DLL içeren uydu yolu dizeleri yerelleştirilmiş.<br /><br /> MPF VSPackage, doğru kaynak edinme yansıma kullanan böylece <xref:Microsoft.VisualStudio.Shell.ProvideProfileAttribute> sınıfı bu bağımsız değişken ayarlı değil.|  
|AlternateParent|REG_SZ|Bu özel ayarları noktasını içeren Araçlar Seçenekler sayfası altında bir klasör adı.|İsteğe bağlı.<br /><br /> Yalnızca bir ayarlarının uygulanması destekliyorsa, bu değer ayarlamanız gerekir **Araçlar Seçenekler** Kalıcılık mekanizması kullanan sayfaları [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] durumunu kaydetmek için otomasyon modeli mekanizma yerine.<br /><br /> Bu durumlarda, AlternateParent anahtar değeri `topic` bölümünü `topic.sub-topic` belirli tanımlamak için kullanılan dize **ToolsOptions** sayfası. Örneğin, **ToolsOptions** sayfa `"TextEditor.Basic"` AlternateParent değeri olacaktır `"TextEditor"`.<br /><br /> Zaman <xref:Microsoft.VisualStudio.Shell.ProvideProfileAttribute> özel ayarları noktası oluşturur kategori adı ile aynı değil.|