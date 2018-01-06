---
title: "Visual Studio'da güvenlik | Microsoft Docs"
ms.custom: 
ms.date: 02/17/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- code access security, coding errors
- security [.NET Framework], about security
ms.assetid: 318c34ce-f643-468c-83a1-843196f5d845
caps.latest.revision: "20"
author: kempb
ms.author: kempb
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 995ac17cd99c395dcf1c69f0d05e1b273ac72f1d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="security-in-visual-studio"></a>Visual Studio'da Güvenlik
Uygulama geliştirme sürecinizde, tasarımdan geliştirmeye kadar her yönüyle güvenliği göz önünde bulundurmalısınız. Visual Studio mümkün olduğunca güvenli bir şekilde çalıştırarak başlayın. Bkz: [kullanıcı izinleri](../ide/user-permissions-and-visual-studio.md).  
  
 Etkin bir şekilde güvenli uygulamalar geliştirmenize yardımcı olması için, geliştirmekte olduğunuz platformların güvenlik kavramları ve güvenlik özellikleri hakkında temel bilgiye sahip olmanız gerekir. Güvenli kodlama tekniklerini de anlamanız gerekir.  
  
## <a name="understanding-security"></a>Güvenliği Anlama  
 [Güvenlik](/dotnet/standard/security/index)  
 .NET Framework kod erişim güvenliği, rol tabanlı güvenlik, güvenlik ilkesi ve güvenlik araçları açıklanmaktadır.  
  
 [Kodunuzu her geliştiricinin bilmesi gereken ilk on güvenlik ipucuyla koruyun](http://go.microsoft.com/fwlink/?LinkId=72877)  
 Verileriniz veya sisteminizin güvenliğinin tehlikeye düşmemesi için dikkat etmeniz gereken konular açıklanmaktadır.  
  
## <a name="coding-for-security"></a>Güvenlik İçin Kodlama  
 Güvenlik açıklarına neden olan çoğu kodlama hatası, geliştiricilerin kullanıcı girdisiyle çalışırken yanlış varsayımlarda bulunmaları veya uygulama geliştirdikleri platformu tam olarak anlamamaları yüzünden meydana gelir.  
  
 [Güvenli Kodlama Yönergeleri](/dotnet/standard/security/secure-coding-guidelines)  
 Güvenlik sorunlarının çözümü için bileşenlerinizin sınıflandırılmasına yönelik yönergeler sağlar.  
  
 [En iyi güvenlik uygulamaları](/cpp/top/security-best-practices-for-cpp)  
 Arabellek taşmalarını ve /GS derleme zamanı bayrağı tarafından sağlanan Microsoft Visual C++ güvenlik denetimleri özelliğinin eksiksiz bir görünümünü açıklar.

## <a name="building-for-security"></a>Güvenliği için oluşturma  
 Güvenlik de önemli bir yapı işlemine konudur.  Birkaç ek adım dağıtılmış bir uygulamayı güvenliğini artırmak ve yetkisiz ters mühendislik, yanıltma veya diğer saldırılara önlemeye yardımcı olun.

 [Dotfuscator Community Edition (CE)](dotfuscator/index.md)  
 Ayarlamak ve ücretsiz PreEmptive tarafından koruması - .NET derlemelerini (örneğin, yetkisiz hata ayıklama) ters mühendislik ve yetkisiz kullanıma karşı korumak için Dotfuscator Community Edition'ı kullanmaya başlamak açıklanmaktadır.
  
 [Derleme ve Bildirim İmzalamayı Yönetme](managing-assembly-and-manifest-signing.md)  
 Anlatılmaktadır güçlü-imzalama, yazılım bileşenleri, ad kimlik sahtekarlığı önleme benzersiz şekilde tanımlamak için kullanılan ad.