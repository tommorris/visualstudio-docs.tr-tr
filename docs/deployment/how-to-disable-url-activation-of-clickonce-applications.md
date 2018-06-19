---
title: 'Nasıl yapılır: ClickOnce uygulamalarında URL etkinleştirmeyi devre dışı bırakma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- disallowUrlActivation
- URL activation, ClickOnce applications
- ClickOnce deployment, URL activation
ms.assetid: db31a16b-960f-4264-91d7-c7c40f876068
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 652060d639f5e516500cdc2b9de9fa7a4a45ee9f
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
ms.locfileid: "31557950"
---
# <a name="how-to-disable-url-activation-of-clickonce-applications"></a>Nasıl yapılır: ClickOnce Uygulamalarında URL Etkinleştirmeyi Devre Dışı Bırakma
Genellikle, bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama bir Web sunucusundan yüklendikten hemen sonra otomatik olarak başlar. Güvenlik nedeniyle, bu davranışı devre dışı bırakabilir ve uygulamayı başlatmak için kullanıcılara söyleyin karar verebilir **Başlat** menü yerine. Aşağıdaki yordam, URL etkinleştirmeyi devre dışı bırakmak açıklar.  
  
 Bu yöntem yalnızca kullanılabilir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] bir Web sunucusundan kullanıcının bilgisayarda yüklü olan uygulamalar. Yalnızca kendi URL'yi kullanarak başlatılabilir çevrimiçi uygulamalar için kullanılamaz. Yalnızca çevrimiçi ve yüklü uygulamaları arasındaki fark hakkında daha fazla bilgi için bkz: [ClickOnce dağıtım stratejisini seçme](../deployment/choosing-a-clickonce-deployment-strategy.md).  
  
 Bu yordamı kullanır [! DAHİL[winsdklong](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client). Bu yordamı kullanarak da gerçekleştirebilirsiniz [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
## <a name="procedure"></a>Yordam  
  
#### <a name="to-disable-url-activation-for-your-application"></a>Uygulamanız için URL etkinleştirmeyi devre dışı bırakmak için  
  
1.  Dağıtım bildiriminizi MageUI.exe açın. Henüz bir oluşturmadıysanız, adımları [izlenecek yol: bir ClickOnce uygulamasını el ile dağıtma](../deployment/walkthrough-manually-deploying-a-clickonce-application.md).  
  
2.  Seçin **dağıtım seçenekleri** sekmesi.  
  
3.  Clear **yüklendikten sonra uygulamayı otomatik olarak çalıştırmak** onay kutusu.  
  
4.  Kaydedin ve bildirimini imzalayın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ClickOnce Uygulamalarını Yayımlama](../deployment/publishing-clickonce-applications.md)