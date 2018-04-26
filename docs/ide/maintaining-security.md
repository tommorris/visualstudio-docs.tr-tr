---
title: Visual Studio'da Uygulama güvenliğini sağlamak
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- unauthorized access
- Baseline Security Analyzer
- Microsoft Baseline Security Analyzer
- security [.NET Framework], best practices
- MBSA (Microsoft Baseline Security Analyzer)
- security [.NET Framework], maintaining after deployment
ms.assetid: 621d10c1-842b-4902-be60-bb9719591751
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ee7a90804c2161fe927bebc2b2f1af45862b8ccd
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="maintain-security"></a>Güvenlik koru

Güvenliğin bedelinin sürekli tetikte bulunmak olduğu söylenir. Uygulamanızın tasarımı ve geliştirilmesi sırasında güvenliğe verdiğiniz büyük öneme rağmen, dağıtımdan sonra güvenlik açıkları ortaya çıkacağını varsaymalısınız. Uygulamanızı denetleyerek ve olay günlüklerini çözümleyerek, daha önceleri gizli kalmış bazı kusurları keşfedebilirsiniz.

Ayrıca, yalnızca kendi uygulamanız hakkında dikkatli olmanız yeterli olmadığı gibi, uygulamanızın çalıştığı platforma ve uygulamanızın bağımlı olduğu diğer ürünlere yönelik güvenlik tehditlerini ve açıklarını da takip etmeniz gerekir.

[Güvenlik, gizlilik ve hesapları](https://support.microsoft.com/products/microsoft-account?category=privacy#security-privacy-accounts-help=windows-8&v0h=winrttab1&v1h=win8tab1&v2h=win7tab1&v3h=winvistatab1)&mdash;güvenlik, gizlilik ve kullanıcı hesapları, virüsler, parolalar, ebeveyn denetimleri, güvenlik duvarları hakkında bilgiler dahil olmak üzere yardım alın ve Sürücü Şifrelemesi...

[Microsoft Güvenlik Bülteni güncelleştirmeleri](https://technet.microsoft.com/security/bulletins.aspx)&mdash;bu sayfada, daha önce yayınlanmış bültenleri bulmayı kolaylaştırır. BT uzmanları için tasarlanmış olan güvenlik bültenleri, güvenlik güncelleştirmeleri ile ilgili ayrıntılı bilgi sağlar.

[Microsoft Baseline Security Analyzer](https://www.microsoft.com/download/details.aspx?id=7558)&mdash;Microsoft Baseline Security Analyzer (MBSA) tek bir ev kullanıcısı, kurumsal bir kullanıcı veya yönetici bir veya daha fazla Windows tabanlı bilgisayarlar için ortak taranacak sağlayan bir araçtır güvenlik yapılandırması hataları.