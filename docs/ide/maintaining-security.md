---
title: Visual Studio'da Uygulama güvenliğini sağlama | Microsoft Docs
ms.date: 11/04/2016
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
ms.openlocfilehash: 6fb75bfe3c9e479e67c766137ee84e919f9a6710
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="maintaining-security"></a>Güvenliğini Sağlama

Güvenliğin bedelinin sürekli tetikte bulunmak olduğu söylenir. Uygulamanızın tasarımı ve geliştirilmesi sırasında güvenliğe verdiğiniz büyük öneme rağmen, dağıtımdan sonra güvenlik açıkları ortaya çıkacağını varsaymalısınız. Uygulamanızı denetleyerek ve olay günlüklerini çözümleyerek, daha önceleri gizli kalmış bazı kusurları keşfedebilirsiniz.

Ayrıca, yalnızca kendi uygulamanız hakkında dikkatli olmanız yeterli olmadığı gibi, uygulamanızın çalıştığı platforma ve uygulamanızın bağımlı olduğu diğer ürünlere yönelik güvenlik tehditlerini ve açıklarını da takip etmeniz gerekir.

[Güvenlik, gizlilik ve hesapları](https://support.microsoft.com/products/microsoft-account?category=privacy#security-privacy-accounts-help=windows-8&v0h=winrttab1&v1h=win8tab1&v2h=win7tab1&v3h=winvistatab1)&mdash;güvenlik, gizlilik ve kullanıcı hesapları, virüsler, parolalar, ebeveyn denetimleri, güvenlik duvarları hakkında bilgiler dahil olmak üzere yardım alın ve Sürücü Şifrelemesi...

[Microsoft güvenlik güncelleştirmeleri bültenleri](https://technet.microsoft.com/security/bulletins.aspx)&mdash;bu sayfada, daha önce yayınlanmış bültenleri bulmayı kolaylaştırır. BT uzmanları için tasarlanmış olan güvenlik bültenleri, güvenlik güncelleştirmeleri ile ilgili ayrıntılı bilgi sağlar.

[Microsoft Baseline Security Analyzer](https://www.microsoft.com/download/details.aspx?id=7558)&mdash;Microsoft Baseline Security Analyzer (MBSA) tek bir ev kullanıcısı, kurumsal bir kullanıcı veya yönetici bir veya daha fazla Windows tabanlı bilgisayarlar için ortak taranacak sağlayan bir araçtır güvenlik yapılandırması hataları.