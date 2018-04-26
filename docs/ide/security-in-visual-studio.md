---
title: Visual Studio'da Güvenlik
ms.date: 02/17/2017
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- code access security, coding errors
- security [.NET Framework], about security
ms.assetid: 318c34ce-f643-468c-83a1-843196f5d845
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 74e557fd0e92742f33c25d68862ae15254104963
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="security-in-visual-studio"></a>Visual Studio'da Güvenlik

Uygulama geliştirme sürecinizde, tasarımdan geliştirmeye kadar her yönüyle güvenliği göz önünde bulundurmalısınız. Visual Studio mümkün olduğunca güvenli bir şekilde çalıştırarak başlayın. Bkz: [kullanıcı izinleri](../ide/user-permissions-and-visual-studio.md).

 Etkin bir şekilde güvenli uygulamalar geliştirmenize yardımcı olması için, geliştirmekte olduğunuz platformların güvenlik kavramları ve güvenlik özellikleri hakkında temel bilgiye sahip olmanız gerekir. Güvenli kodlama tekniklerini de anlamanız gerekir.

## <a name="understand-security"></a>Güvenliği anlama
 [Güvenlik](/dotnet/standard/security/index) açıklar .NET Framework'te kod erişimi güvenliği, rol tabanlı güvenlik, güvenlik ilkesi ve güvenlik araçları.

 [Kodunuzu her geliştiricinin bilmesi gereken ilk on güvenlik ipucuyla koruyun](http://go.microsoft.com/fwlink/?LinkId=72877) için dikkat etmeniz çıkışı ve böylece verilerinizi ya da sisteminizi riske olmayan sorunlar açıklanmaktadır.

## <a name="code-for-security"></a>Kod güvenliği
 Güvenlik açıklarına neden olan çoğu kodlama hatası, geliştiricilerin kullanıcı girdisiyle çalışırken yanlış varsayımlarda bulunmaları veya uygulama geliştirdikleri platformu tam olarak anlamamaları yüzünden meydana gelir.

 [Güvenli kodlama yönergeleri](/dotnet/standard/security/secure-coding-guidelines) bileşenlerinizi güvenlik sorunları gidermek üzere sınıflandırmak için yönergeler sağlar.

 [En iyi güvenlik uygulamaları](/cpp/top/security-best-practices-for-cpp) Discusses arabellek taşmaları ve Microsoft Visual C++ güvenlik eksiksiz bir görünümünü /GS derleme zamanı bayrağı tarafından sağlanan özelliğini denetler.

## <a name="build-for-security"></a>Güvenlik için derleme
 Güvenlik de önemli bir yapı işlemine konudur.  Birkaç ek adım dağıtılmış bir uygulamayı güvenliğini artırmak ve yetkisiz ters mühendislik, yanıltma veya diğer saldırılara önlemeye yardımcı olun.

 [Dotfuscator Community Edition (CE)](dotfuscator/index.md) ayarlamak ve ücretsiz PreEmptive tarafından koruması - .NET derlemelerini (örneğin, yetkisiz hata ayıklama) ters mühendislik ve yetkisiz kullanıma karşı korumak için Dotfuscator Community Edition'ı kullanmaya başlamak açıklanmaktadır.

 [Derleme yönetmek ve bildirimlerini imzalama](managing-assembly-and-manifest-signing.md) Discusses güçlü-imzalama, yazılım bileşenleri, ad kimlik sahtekarlığı önleme benzersiz şekilde tanımlamak için kullanılan ad.