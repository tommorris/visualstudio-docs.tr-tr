---
title: "Eski dil hizmeti genişletilebilirliği | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- language services
- Visual Studio, language services
ms.assetid: 2700cd4d-5f68-43fc-b62f-dc80c3f3aa85
caps.latest.revision: "42"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: a5072aef90e08d645bff2a1bb6800e409e7d2104
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="legacy-language-service-extensibility"></a>Eski dil hizmeti genişletilebilirliği
Bir dil hizmeti IDE kaynak kod düzenleme için dile özgü destek sağlar.  
  
 Eski dil hizmetler bir VSPackage bir parçası olarak uygulanır, ancak dil hizmet özellikleri uygulamak için daha yeni MEF uzantıları kullanmak için bir yoludur. Bir dil hizmeti uygulamak için yeni yolu hakkında daha fazla bilgi için bkz: [Düzenleyicisi ve dil hizmeti uzantılarını](../../extensibility/editor-and-language-service-extensions.md).  
  
 Bu bölümde, yapı ve eski dil hizmeti uygulaması açıklanmaktadır.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Eski dil hizmetini geçirme](../../extensibility/internals/migrating-a-legacy-language-service.md)  
 Visual Studio 2008 bir dil Hizmeti'nden en son sürüme güncelleştirmek açıklanmaktadır.  
  
 [Eski dil hizmeti temelleri](../../extensibility/internals/legacy-language-service-essentials.md)  
 Bir programlama dili Visual Studio'ya tümleştirmek için dil Hizmetleri geliştirme hakkında önemli bilgileri sağlar.  
  
 [Eski dil hizmeti geliştirme](../../extensibility/internals/developing-a-legacy-language-service.md)  
 Bir dil hizmeti oluşturmanıza yardımcı olabilir konulara bağlantılar sağlar.  
  
 [Eski dil hizmetinde renklendirme sözdizimi](../../extensibility/internals/syntax-coloring-in-a-legacy-language-service.md)  
 Bir dil hizmetinde sözdizimi vurgulama destekleme hakkında bilgi sağlar.  
  
 [Eski dil hizmeti uygulama](../../extensibility/internals/implementing-a-legacy-language-service1.md)  
 Yönetilen paket framework (MPF) tam özellikli dil hizmeti yönetilen koda uygulanması için nasıl kullanılacağı hakkında bilgi sağlar.  
  
 [Simgenin tarama araçları destekleme](../../extensibility/internals/supporting-symbol-browsing-tools.md)  
 Kitaplıkları ve IDE içinde simgelerin ağaç görünümleri Gözat sağlayan araçlar açıklanmaktadır.  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [Düzenleyici ve dil hizmeti uzantıları](../../extensibility/editor-and-language-service-extensions.md)  
 Visual Studio düzenleyicileri genel bir bakış sağlar.  
  
 [Hata ayıklama için dil hizmeti desteği](../../extensibility/internals/language-service-support-for-debugging.md)  
 Visual Studio hata ayıklama oluşturmak ve programların hatalarını ayıklamak için kullanılan hata ayıklayıcı bileşenleri özelleştirmek için gerekli olan bilgileri içeren SDK için ilgili bilgileri ve bağlantı sağlar.