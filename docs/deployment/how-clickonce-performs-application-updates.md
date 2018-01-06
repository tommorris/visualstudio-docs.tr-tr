---
title: "ClickOnce uygulama güncelleştirmelerini nasıl gerçekleştirir | Microsoft Docs"
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
- updates, ClickOnce
- ClickOnce deployment, updates
- deploying applications [ClickOnce], application updates
ms.assetid: d54313c2-cf0c-420d-b151-99953a95f0bb
caps.latest.revision: "9"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload: multiple
ms.openlocfilehash: 6ee199aa98c0c5b72a5693c840b892929e55477a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-clickonce-performs-application-updates"></a>ClickOnce Uygulama Güncelleştirmelerini Nasıl Gerçekleştirir
ClickOnce Uygulama dosyalarını güncelleştirmek karar vermek için bir uygulamanın dağıtım bildiriminde belirtilen dosya sürümü bilgilerini kullanır. Bir güncelleştirme başladıktan sonra ClickOnce adında bir teknik kullanır *dosya düzeltme eki uygulama* gereksiz uygulama dosyalarının yüklenmesini önlemek için.  
  
## <a name="file-patching"></a>Dosya düzeltme eki uygulama  
 Dosyaları değiştirmediğiniz sürece bir uygulama güncelleştirilirken ClickOnce tüm dosyaları uygulamanın yeni sürümü için indirmez. Bunun yerine, yeni sürümün bildiriminde imzaları karşı geçerli uygulama için uygulama bildiriminde belirtilen dosyaların karma imzaları karşılaştırır. Bir dosyanın imzası farklıysa, ClickOnce yeni sürümü indirir. İmzalar eşleşirse, dosyanın bir sürümünden sonraki değişmemiştir. Bu durumda, ClickOnce varolan dosyayı kopyalar ve uygulamanın yeni sürümü kullanır. Bu yaklaşım, yalnızca bir veya iki dosyalar değiştirilmiş olsa bile tüm uygulama yeniden indirmek zorunda ClickOnce engeller.  
  
 Dosya düzeltme eki uygulama de çalışır yüklenen derlemeler kullanarak isteğe bağlı olarak <xref:System.Deployment.Application.ApplicationDeployment.DownloadFileGroup%2A> ve <xref:System.Deployment.Application.ApplicationDeployment.DownloadFileGroupAsync%2A> yöntemleri.  
  
 Uygulamanızı derlemek için Visual Studio kullanıyorsanız tüm projeyi yeniden her tüm dosyalar için yeni karma imzaları oluşturur. Bu durumda, sadece birkaç derleme değişmesine rağmen tüm derlemeler istemciye indirilir.  
  
 Dosya düzeltme eki uygulama verileri olarak işaretlenmiş ve veri dizininde depolanan dosyalar için geçerli değildir. Bu, dosyanın karması imzasını bağımsız olarak daima yüklenir. Veri dizini hakkında daha fazla bilgi için bkz: [erişme yerel ve uzak veri ClickOnce uygulamalarında](../deployment/accessing-local-and-remote-data-in-clickonce-applications.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ClickOnce güncelleştirme stratejisini seçme](../deployment/choosing-a-clickonce-update-strategy.md)   
 [ClickOnce Dağıtım Stratejisini Seçme](../deployment/choosing-a-clickonce-deployment-strategy.md)