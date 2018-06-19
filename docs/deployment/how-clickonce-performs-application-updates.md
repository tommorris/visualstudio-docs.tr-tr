---
title: ClickOnce uygulama güncelleştirmelerini nasıl gerçekleştirir | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- updates, ClickOnce
- ClickOnce deployment, updates
- deploying applications [ClickOnce], application updates
ms.assetid: d54313c2-cf0c-420d-b151-99953a95f0bb
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: bbe09cfe546d947bf07334e9dd6468226884e9e3
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
ms.locfileid: "31557703"
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