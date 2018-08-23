---
title: 'Nasıl yapılır: tasarımcıyı kullanarak ClickOnce uygulamalarında URL etkinleştirmeyi devre dışı | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-deployment
ms.tgt_pltfrm: ''
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
caps.latest.revision: 18
author: mikejo5000
ms.author: mikejo
manager: wpickett
ms.openlocfilehash: 6cc5571dffba9daa3ac1f5f78e354487cbc654fe
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42691959"
---
# <a name="how-to-disable-url-activation-of-clickonce-applications-by-using-the-designer"></a>Nasıl yapılır: Tasarımcıyı Kullanarak ClickOnce Uygulamalarında URL Etkinleştirmeyi Devre Dışı Bırakma
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [nasıl yapılır: devre dışı URL etkinleştirme ClickOnce Tasarımcısını kullanarak uygulama](https://docs.microsoft.com/visualstudio/deployment/how-to-disable-url-activation-of-clickonce-applications-by-using-the-designer).  
  
Genellikle, bir [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] uygulama bir Web sunucusundan yükledikten hemen sonra otomatik olarak başlayacak. Güvenlik nedeniyle, bu davranışı devre dışı bırakmak ve uygulamayı başlatmak için kullanıcılar karar verebilir **Başlat** menü yerine. Aşağıdaki yordam, URL etkinleştirmeyi devre dışı bırakmak açıklar.  
  
 Bu teknik yalnızca kullanılabilir [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] kullanıcının bilgisayarında bir Web sunucusundan yüklenen uygulamalar. Yalnızca kendi URL'yi kullanarak başlatılabilir, yalnızca çevrimiçi uygulamalar için kullanılamaz. Yalnızca çevrimiçi ve yüklü uygulamaları arasındaki fark hakkında daha fazla bilgi için bkz: [ClickOnce dağıtım stratejisini seçme](../deployment/choosing-a-clickonce-deployment-strategy.md).  
  
 Bu yordamı kullanır [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]. Bu görevi kullanarak da gerçekleştirebilirsiniz [!INCLUDE[winsdklong](../includes/winsdklong-md.md)]. Daha fazla bilgi için [nasıl yapılır: ClickOnce Uygulama URL etkinleştirmeyi devre dışı](../deployment/how-to-disable-url-activation-of-clickonce-applications.md).  
  
## <a name="procedure"></a>Yordam  
  
#### <a name="to-disable-url-activation-for-your-application"></a>Uygulamanız için URL etkinleştirmeyi devre dışı bırakmak için  
  
1.  İçinde proje adınıza sağ **Çözüm Gezgini**, tıklatıp **özellikleri**.  
  
2.  Üzerinde **özellikleri** sayfasında **Yayımla** sekmesi.  
  
3.  Tıklayın **seçenekleri**.  
  
4.  Tıklayın **bildirimlerini**.  
  
5.  Etiketli onay kutusunu seçin **engelleyecek bir URL ile etkinleştirilmekte olan uygulamanın**.  
  
6.  Uygulamanızı dağıtın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ClickOnce Uygulamalarını Yayımlama](../deployment/publishing-clickonce-applications.md)



