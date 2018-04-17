---
title: Güvenlik ve yerleştirilmiş yardımcı derlemeler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- key pairs for strong-named assemblies
- strong-named assemblies, security considerations
- satellite assemblies, localized
- code signing, assemblies
- security [Visual Studio], assemblies
- strong-named assemblies, localized
- assemblies [Visual Studio], security
- localization, satellite assemblies
ms.assetid: 6d953840-b301-47d5-8d34-30c1b29b5071
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ca89e842b6e5229890e93c06b7ca83658f6dbf7c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="security-and-localized-satellite-assemblies"></a>Güvenlik ve Yerleştirilmiş Yardımcı Derlemeler

Ana derleme güçlü adlandırma kullanıyorsa, uydu derlemeleri ana derlemeyle aynı özel anahtar ile imzalanmalıdır. Ortak/özel anahtar çifti eşleşmiyor ana ve uydu derlemelerini, kaynaklarınız arasında yüklü değil İmzalama derlemeler hakkında daha fazla bilgi için bkz: [nasıl yapılır: bir derlemeyi tanımlayıcı adla oturum](/dotnet/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name).  
  
 Genel olarak, kuruluşunuzun imzalama grubu veya özel anahtar ile oturum açma dış imzalama kuruluş olması gerekebilir. Özel anahtarı hassas yapısı nedeniyle budur: erişim kısıtlıdır genellikle birkaç kişi. Geliştirme sırasında Gecikmeli imzalama kullanabilirsiniz. Daha fazla bilgi için bkz: [Gecikmeli bir derleme imzalama](/dotnet/framework/app-domains/delay-sign-assembly).  
  
## <a name="see-also"></a>Ayrıca bkz.

- [Derleme güvenliği konuları](/dotnet/framework/app-domains/assembly-security-considerations)  - [anahtar güvenlik kavramları](/dotnet/standard/security/key-security-concepts)   
- [.NET Framework Tabanlı Uluslararası Uygulamalara Giriş](../ide/introduction-to-international-applications-based-on-the-dotnet-framework.md)   
- [Uygulamaları Yerelleştirme](../ide/localizing-applications.md)   
- [Uygulamaları Genelleştirme ve Yerelleştirme](../ide/globalizing-and-localizing-applications.md)