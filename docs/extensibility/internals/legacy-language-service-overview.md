---
title: "Eski dil hizmetine genel bakış | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: language services [managed package framework], about language services
ms.assetid: bb44e27b-d228-463c-b2cf-cd5c24c7c1b5
caps.latest.revision: "17"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d586851da7d02f89335a3920364e25b7f4876860
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="legacy-language-service-overview"></a>Eski dil hizmetine genel bakış
Bir dil hizmeti belirli uygulamanıza olanak tanıyan Düzenleyicisi destek sağlar [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] özellikleri. Yönetilen paket Framework (MPF) dil hizmet sınıfları, özellikleri sık kullanılan ve diğer özellikleri kısmi desteği için tam destek sağlar.  
  
## <a name="fully-supported-features-in-the-mpf"></a>MPF tam olarak desteklenen özellikler  
 MPF dil hizmet sınıfları aşağıdaki özellikleri destekler:  
  
-   söz dizimi vurgulama  
  
-   Anahat Oluşturma  
  
-   Kod blokları yorum oluşturma  
  
-   Ayraç eşleştirme  
  
-   Kod parçacıkları  
  
-   Özel belge özellikleri  
  
-   IntelliSense parametre bilgileri  
  
-   IntelliSense hızlı bilgi  
  
-   IntelliSense üye tamamlama  
  
-   IntelliSense Sözcük tamamlama  
  
## <a name="partially-supported-features-in-the-mpf"></a>MPF kısmen desteklenen özellikler  
 MPF yalnızca kısmi desteği için aşağıdaki özellikleri sağlar. Başka bir deyişle, MPF tarafından çağrılan yöntemler uygulamalıdır.  
  
-   Kod biçimlendirme. Yeniden biçimlendirme uygulayan kodunu sağlayın.  
  
-   Kesme noktaları geçerli kod belirleyerek doğrulama yayar. Kod yayılma tanımlayan kodu sağlayın.  
  
-   Hata ayıklayıcı destekleyen **otomobiller** değişkenleri görüntüleme penceresi. Ne penceresinde gösterileceğini belirler kod sağlayın.  
  
-   Destek **gezinti çubuğu** türleri ve üyeleri arasında hızlı gezinme için. Uygulama ve listelerinde dolduran bir yardımcı sınıfı dönmek **gezinti çubuğu** birleşik giriş kutuları.  
  
## <a name="implementation"></a>Uygulama  
 Dil hizmeti ve dilinizi desteklemek istediğiniz dil hizmet özellikleri uygulamak için birkaç adımları tamamlamanız gerekir. Bu adımları aşağıdaki konular ele alınmaktadır:  
  
-   [Eski dil hizmeti uygulama](../../extensibility/internals/implementing-a-legacy-language-service2.md)  
  
-   [Eski dil hizmeti kaydetme](../../extensibility/internals/registering-a-legacy-language-service1.md)  
  
-   [Eski dil hizmetinde söz dizimi renklendirme](../../extensibility/internals/syntax-colorizing-in-a-legacy-language-service.md)  
  
-   [Eski dil hizmet eşlemesi](../../extensibility/internals/brace-matching-in-a-legacy-language-service.md)  
  
-   [Eski dil hizmetinde anahat oluşturma](../../extensibility/internals/outlining-in-a-legacy-language-service.md)  
  
-   [Eski dil hizmeti yorum oluşturma kodu](../../extensibility/internals/commenting-code-in-a-legacy-language-service.md)  
  
-   [Eski dil hizmeti kodunda yeniden biçimlendirme](../../extensibility/internals/reformatting-code-in-a-legacy-language-service.md)  
  
-   [Eski dil hizmetinde özel belge özellikleri](../../extensibility/internals/custom-document-properties-in-a-legacy-language-service.md)  
  
-   [Kod parçacıkları eski dil hizmetindeki desteği](../../extensibility/internals/support-for-code-snippets-in-a-legacy-language-service.md)  
  
-   [Eski dil hizmeti gezinti çubuğunda desteği](../../extensibility/internals/support-for-the-navigation-bar-in-a-legacy-language-service.md)  
  
-   [Eski dil hizmetindeki Sözcük tamamlama](../../extensibility/internals/word-completion-in-a-legacy-language-service.md)  
  
-   [Eski dil hizmetindeki üye tamamlama](../../extensibility/internals/member-completion-in-a-legacy-language-service.md)  
  
-   [Eski dil hizmetindeki parametre bilgisi](../../extensibility/internals/parameter-info-in-a-legacy-language-service2.md)  
  
-   [Eski dil hizmetindeki hızlı bilgi](../../extensibility/internals/quick-info-in-a-legacy-language-service.md)  
  
-   [Eski dil hizmetinde otomatik değişkenler penceresi desteği](../../extensibility/internals/support-for-the-autos-window-in-a-legacy-language-service.md)  
  
-   [Kesme noktaları eski dil hizmetindeki doğrulanıyor](../../extensibility/internals/validating-breakpoints-in-a-legacy-language-service.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eski dil hizmeti uygulama](../../extensibility/internals/implementing-a-legacy-language-service1.md)   
 [Eski dil hizmeti genişletilebilirliği](../../extensibility/internals/legacy-language-service-extensibility.md)