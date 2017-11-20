---
title: "Nasıl yapılır: tasarımcıyı kullanarak ClickOnce uygulamalarında URL etkinleştirmeyi devre dışı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- disallowURLActivation
- URL activation, ClickOnce applications
- ClickOnce deployment, URL activation
ms.assetid: a337a582-e67c-409a-b52e-607cd1a8fc57
caps.latest.revision: "16"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.openlocfilehash: f694b7bf80d15fa3674d64bb7d062cdf0953c14b
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="how-to-disable-url-activation-of-clickonce-applications-by-using-the-designer"></a>Nasıl yapılır: Tasarımcıyı Kullanarak ClickOnce Uygulamalarında URL Etkinleştirmeyi Devre Dışı Bırakma
Genellikle, bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama bir Web sunucusundan yüklendikten hemen sonra otomatik olarak başlayacak. Güvenlik nedeniyle, bu davranışı devre dışı bırakabilir ve uygulamayı başlatmak için kullanıcılara söyleyin karar verebilir **Başlat** menü yerine. Aşağıdaki yordam, URL etkinleştirmeyi devre dışı bırakmak açıklar.  
  
 Bu yöntem yalnızca kullanılabilir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] bir Web sunucusundan kullanıcının bilgisayarda yüklü olan uygulamalar. Yalnızca kendi URL'yi kullanarak başlatılabilir çevrimiçi uygulamalar için kullanılamaz. Yalnızca çevrimiçi ve yüklü uygulamaları arasındaki fark hakkında daha fazla bilgi için bkz: [ClickOnce dağıtım stratejisini seçme](../deployment/choosing-a-clickonce-deployment-strategy.md).  
  
 Bu yordamı kullanır [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Kullanarak bu görevi gerçekleştirebilirsiniz [!INCLUDE[winsdklong](../deployment/includes/winsdklong_md.md)]. Daha fazla bilgi için bkz: [nasıl yapılır: devre dışı URL etkinleştirme, ClickOnce uygulamaları](../deployment/how-to-disable-url-activation-of-clickonce-applications.md).  
  
## <a name="procedure"></a>Yordam  
  
#### <a name="to-disable-url-activation-for-your-application"></a>Uygulamanız için URL etkinleştirmeyi devre dışı bırakmak için  
  
1.  ' Nde proje adına sağ tıklayın **Çözüm Gezgini**, tıklatıp **özellikleri**.  
  
2.  Üzerinde **özellikleri** sayfasında, **Yayımla** sekmesi.  
  
3.  Tıklatın **seçenekleri**.  
  
4.  Tıklatın **bildirimleri**.  
  
5.  Etiketli onay kutusunu seçin **engelleme URL aracılığıyla etkinleştirilmekte olan uygulamanın**.  
  
6.  Uygulamanızı dağıtın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ClickOnce uygulamalarını yayımlama](../deployment/publishing-clickonce-applications.md)