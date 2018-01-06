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
ms.workload: vssdk
ms.openlocfilehash: 05805e5cf4b21f4c7d233cab7dd8421ee76f626f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
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
  
-   [Eski Dil Hizmetinde Söz Dizimi Renklendirmesi](../../extensibility/internals/syntax-colorizing-in-a-legacy-language-service.md)  
  
-   [Eski Dil Hizmetinde Ayraç Eşleştirme](../../extensibility/internals/brace-matching-in-a-legacy-language-service.md)  
  
-   [Eski Dil Hizmetinde Ana Hat Oluşturma](../../extensibility/internals/outlining-in-a-legacy-language-service.md)  
  
-   [Eski Dil Hizmetinde Koda Açıklama Ekleme](../../extensibility/internals/commenting-code-in-a-legacy-language-service.md)  
  
-   [Eski Dil Hizmetinde Kodu Yeniden Biçimlendirme](../../extensibility/internals/reformatting-code-in-a-legacy-language-service.md)  
  
-   [Eski Dil Hizmetinde Özel Belge Özellikleri](../../extensibility/internals/custom-document-properties-in-a-legacy-language-service.md)  
  
-   [Eski Dil Hizmetinde Kod Parçacıkları için Destek](../../extensibility/internals/support-for-code-snippets-in-a-legacy-language-service.md)  
  
-   [Eski Dil Hizmetinde Otomatik Değişkenler Penceresi için Destek](../../extensibility/internals/support-for-the-navigation-bar-in-a-legacy-language-service.md)  
  
-   [Eski Dil Hizmetinde Sözcük Tamamlama](../../extensibility/internals/word-completion-in-a-legacy-language-service.md)  
  
-   [Eski Dil Hizmetinde Üye Tamamlama](../../extensibility/internals/member-completion-in-a-legacy-language-service.md)  
  
-   [Eski dil hizmetindeki parametre bilgisi](../../extensibility/internals/parameter-info-in-a-legacy-language-service2.md)  
  
-   [Eski Dil Hizmetinde Hızlı Bilgiler](../../extensibility/internals/quick-info-in-a-legacy-language-service.md)  
  
-   [Eski Dil Hizmetinde Otomatik Değişkenler Penceresi için Destek](../../extensibility/internals/support-for-the-autos-window-in-a-legacy-language-service.md)  
  
-   [Eski Dil Hizmetinde Kesme Noktalarını Doğrulama](../../extensibility/internals/validating-breakpoints-in-a-legacy-language-service.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eski dil hizmeti uygulama](../../extensibility/internals/implementing-a-legacy-language-service1.md)   
 [Eski Dil Hizmeti Genişletilebilirliği](../../extensibility/internals/legacy-language-service-extensibility.md)