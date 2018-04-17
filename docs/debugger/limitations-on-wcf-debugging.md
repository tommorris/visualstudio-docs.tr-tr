---
title: WCE hata ayıklamasında sınırlamalar | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging, WCF
- WCF, debugging limitations
ms.assetid: 8e0333c4-1ddc-4abe-8f1c-d19bf6a2a07a
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 7696afd789753b85facf44dfeadf1f3f30c1596b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="limitations-on-wcf-debugging"></a>WCE Hata Ayıklamasında Sınırlamalar
Bir WCF Hizmeti hata ayıklama başlayabilirsiniz üç yolu vardır:  
  
-   Bir hizmeti çağıran bir istemci işlemi ayıkladığınız. Hata ayıklayıcı adımları hizmete. Hizmet istemci uygulamanızı olarak aynı çözüme olması gerekmez.  
  
-   Bir hizmete istekte bir istemci işlemi ayıkladığınız. Hizmet, çözümün bir parçası olması gerekir.  
  
-   Kullandığınız **ekleme işlemi için** şu anda çalışan bir hizmete eklemek için. Hata ayıklama içinde hizmeti başlar.  
  
 Bu konuda bu senaryoları sınırlamaları açıklar.  
  
## <a name="limitations-on-stepping-into-a-service"></a>Bir hizmete atlama sınırlamalar  
 Hata ayıklama yaptığınız istemci uygulamalarından bir hizmete adım için aşağıdaki koşullar karşılanmalıdır:  
  
-   İstemci, eşzamanlı istemci nesnesi kullanarak hizmet çağırmanız gerekir.  
  
-   Sözleşme işlemi tek yönlü olamaz.  
  
-   Zaman uyumsuz sunucusuysa, hizmet içinde kod yürütme sırasında tam çağrı yığını görüntüleyemezsiniz.  
  
-   Hata ayıklama app.config veya Web.config dosyasında aşağıdaki kodla etkinleştirilmiş olmalıdır:  
  
    ```  
    <system.web>  
      <compilation debug="true" />  
    </system.web>  
    ```  
  
     Bu kod yalnızca bir kez eklenmesi gerekiyor. Bu kodu .config dosyasını düzenleyerek ya da hizmete kullanarak ekleyerek ekleyebilirsiniz **ekleme işlemi için**. Kullandığınızda **ekleme işlemi için** bir hizmette hata ayıklama kodu otomatik olarak .config dosyasına eklenir. Bundan sonra hata ayıklama ve .config dosyası düzenlemek zorunda kalmadan hizmete adım.  
  
## <a name="limitations-on-stepping-out-of-a-service"></a>Bir hizmet dışı atlama sınırlamalar  
 Bir hizmet dışına ve istemciye geri atlama bir hizmete atlama için açıklanan aynı sınırlamalara sahiptir. Ayrıca, hata ayıklayıcı istemciye bağlı olması gerekir. Bir istemci ve hizmet adımla ayıkladığınız hata ayıklayıcı hizmete bağlı olarak kalır. Bu olup olmadığını kullanılarak istemci başlatılan geçerlidir **hata ayıklamayı Başlat** veya kullanarak istemciye bağlı **ekleme işlemi için**. Hizmete ekleyerek hata ayıklama başladıysa, hata ayıklayıcı istemciye henüz eklenmemiş. Bu durumda, hizmet dışına adıma ve istemciye geri varsa, ilk kullanmalısınız **ekleme işlemi için** istemciye el ile eklemek için.  
  
## <a name="limitations-on-automatic-attach-to-a-service"></a>Bir hizmete otomatik sınırlamalar ekleme  
 Otomatik olarak bir hizmete ekleme aşağıdaki sınırlamalara sahiptir:  
  
-   Hizmetin bir parçası olması [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ayıkladığınız çözümü.  
  
-   Hizmet barındırılması gerekir. Bir Web sitesi projesini (dosya sistemi ve HTTP), Web uygulama projesi (dosya sistemi ve HTTP) veya WCF Hizmeti kitaplığı proje parçası olabilir. WCF hizmet kitaplık projeleri, hizmet kitaplıkları veya iş akışı hizmeti kitaplıkları olabilir.  
  
-   Hizmet bir WCF istemciden çağrılması gerekir.  
  
-   Hata ayıklama app.config veya Web.config dosyasında aşağıdaki kodla etkinleştirilmiş olmalıdır:  
  
    ```  
    <system.web>  
      <compilation debug="true" />  
    <system.web>  
    ```  
  
## <a name="self-hosting"></a>Kendi kendine barındırma  
 A *kendi kendini barındıran hizmete* WCF hizmet ana bilgisayarı, IIS içinde çalışmaz bir WCF hizmeti veya [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] geliştirme sunucusu. Kendini barındıran hizmet hata ayıklama hakkında daha fazla bilgi için bkz: [nasıl yapılır: bir Self-Hosted WCF hizmetinde hata ayıklama](../debugger/how-to-debug-a-self-hosted-wcf-service.md).  
  
## <a name="self-hosting"></a>Kendi kendine barındırma  
 Hata ayıklamayı etkinleştirmek için [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 3.0 veya 3.5 uygulamaları [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 3.0 veya 3.5 yüklü olmalıdır önce [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)] yüklenir. Varsa [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)] önce yüklü [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 3.0 veya 3.5, bir hata oluştuğunda, hata ayıklama çalıştığınızda bir [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 3.0 veya 3.5 uygulama. Hata iletisi olduğundan, "Unable to otomatik olarak sunucuya adım." Bu sorunu gidermek için Windows kullanma **Denetim Masası** > **programlar ve Özellikler** onarmak için [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)] yükleme.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [WCF hizmetlerinde hata ayıklama](../debugger/debugging-wcf-services.md)   
 [Nasıl yapılır: kendini barındıran WCF hizmetinde hata ayıklama](../debugger/how-to-debug-a-self-hosted-wcf-service.md)