---
title: 'Nasıl yapılır: özel metin işaretçileri oluşturun | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - custom text markers
ms.assetid: 6e32ed81-c604-4a32-9012-8db3bec7c846
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: f5c44a507cc291b203fc9ba330b248a854f61b81
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31132279"
---
# <a name="how-to-create-custom-text-markers"></a>Nasıl yapılır: özel metin işaretçileri oluşturma
Vurgulamak veya kod düzenlemek için bir özel metin işaretçisi oluşturmak istiyorsanız, aşağıdaki adımları izlemelisiniz:  
  
-   Diğer araçları erişebilmesi yeni metin işaretçisi kaydetme  
  
-   Bir varsayılan uygulama ve metin işaretçisi yapılandırılmasını sağlayın  
  
-   Yapmak için başka işlemler tarafından kullanılan bir hizmet oluşturma metin işaret kullanın  
  
 Bir metin işaretçisi bir bölge kodu uygulamak nasıl hakkında daha fazla bilgi için bkz: [nasıl yapılır: kullanım metin işaretçileri](../extensibility/how-to-use-text-markers.md).  
  
### <a name="to-register-a-custom-marker"></a>Özel işaret kaydetmek için  
  
1.  Bir kayıt defteri girdisi gibi oluşturun:  
  
     HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\\*\<sürüm >* \Text Editor\External işaretçileri\\*\<MarkerGUID >*  
  
     *\<MarkerGUID >* olan bir `GUID` eklenmekte olan işaret tanımlamak için kullanılan  
  
     *\<Sürüm >* sürümü [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], örneğin 8.0  
  
     *\<PackageGUID >* Otomasyon nesnesi uygulama VSPackage GUID'dir.  
  
    > [!NOTE]
    >  HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio kök yolunu\\*\<sürüm >* Visual Studio Kabuğu'nu başlatıldığında daha fazla bilgi için bkz, alternatif bir kök ile geçersiz kılınabilir [Komut satırı anahtarları](../extensibility/command-line-switches-visual-studio-sdk.md).  
  
2.  HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio altına dört değerleri oluşturmak\\*\<sürüm >* \Text Editor\External işaretçileri\\*\<MarkerGUID >*  
  
    -   (Varsayılan)  
  
    -   Hizmet  
  
    -   Görünen adı  
  
    -   Paket  
  
    -   `Default` türü REG_SZ isteğe bağlı bir giriştir. Ayarlandığında, giriş bazı yararlı tanımlayıcı bilgileri, örneğin "özel metin işaretçisi" içeren bir dize değeridir.  
  
    -   `Service` olan bir giriş türü REG_SZ içeren özel metin işaretçisi proffering tarafından sağlayan hizmeti GUID dizesi <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerTypeProvider>. {XXXXXX XXXX XXXX XXXX XXXXXXXXX} biçimindedir.  
  
    -   `DisplayName` bir giriş türü REG_SZ özel metin işaretçisi adını kaynak Kimliğini içeren. #YYYY biçimidir.  
  
    -   `Package` Giriş türü REG_SZ içeren `GUID` hizmeti sağlayan VSPackage hizmeti altında listelenir. {XXXXXX XXXX XXXX XXXX XXXXXXXXX} biçimindedir.  
  
### <a name="to-create-a-custom-text-marker"></a>Özel metin işaretçisi oluşturmak için  
  
1.  Uygulama <xref:Microsoft.VisualStudio.TextManager.Interop.IVsPackageDefinedTextMarkerType> arabirimi.  
  
     Bu arabirim, uygulamanızı özel işaret türünüz görünümünü ve davranışını tanımlar.  
  
     Bu arabirim aldığında çağrılan  
  
    1.  Bir kullanıcı ilk kez IDE başlatır.  
  
    2.  Bir kullanıcının seçtiği **Varsayılanlara Sıfırla** altında düğmesini **yazı tiplerini ve renkleri** özellik sayfasında **ortam** soldaki bölmede bulunan klasöründen  **Seçenekler** iletişim kutusu elde **Araçları** IDE menüsü.  
  
2.  Uygulama <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerTypeProvider.GetTextMarkerType%2A> yöntemi, hangi belirtme `IVsPackageDefinedTextMarkerType` uygulaması döndürülüp döndürülmediğini tabanlı işaret türündeki yöntemi çağrısında belirtilen GUID.  
  
     Ortam özel işaret türü oluşturulur ve özel işaret türünü tanımlayan bir GUID belirtir bu yöntem ilk kez çağırır.  
  
### <a name="to-proffer-your-marker-type-as-a-service"></a>İşaret türü bir hizmet olarak proffer için  
  
1.  Çağrı <xref:Microsoft.VisualStudio.OLE.Interop.IOleComponentManager.QueryService%2A> yöntemi <xref:Microsoft.VisualStudio.Shell.Interop.SProfferService>.  
  
     Bir işaretçi <xref:Microsoft.VisualStudio.Shell.Interop.IProfferService> döndürülür.  
  
2.  Çağrı <xref:Microsoft.VisualStudio.Shell.Interop.IProfferService.ProfferService%2A> yöntemi, özel işaret türü hizmetinizi tanımlayan ve uygulamanızı gösteren bir işaretçi sağlayarak GUID belirtilmesi <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider> arabirimi. <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider> Uygulaması, uygulamanız için bir işaretçi döndürmelidir <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerTypeProvider> arabirimi.  
  
     Hizmetinizi döndürdüğünü tanımlayan benzersiz bir tanımlama bilgisi. Daha sonra bu tanımlama bilgisi çağırarak özel işaret türü hizmetinizi iptal etmek için kullanabileceğiniz <xref:Microsoft.VisualStudio.Shell.Interop.IProfferService.RevokeService%2A> yöntemi <xref:Microsoft.VisualStudio.Shell.Interop.IProfferService> bu tanımlama bilgisi değeri belirterek arabirimi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Metin işaretçileri eski API ile kullanma](../extensibility/using-text-markers-with-the-legacy-api.md)   
 [Nasıl yapılır: standart metin işaretleyicileri ekleyin](../extensibility/how-to-add-standard-text-markers.md)   
 [Nasıl yapılır: uygulama hata işaretçileri](../extensibility/how-to-implement-error-markers.md)   
 [Nasıl yapılır: metin işaretçileri kullanın](../extensibility/how-to-use-text-markers.md)