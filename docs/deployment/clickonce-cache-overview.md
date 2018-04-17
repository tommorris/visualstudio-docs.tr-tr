---
title: ClickOnce önbelleğine genel bakış | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- Windows applications, ClickOnce deployemtn
- ClickOnce applications, cache
- ClickOnce deployment, cache
ms.assetid: e379921e-9ef1-4326-bbf3-53ba67925526
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: 847e6cc7e84dcda2efdbaac630ce8589ff959180
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="clickonce-cache-overview"></a>ClickOnce Önbelleğine Genel Bakış
Tüm [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulamaları, yerel olarak yüklenmiş veya çevrimiçi barındırılan depolanır istemci bilgisayarda bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]uygulama *önbellek*. A [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] önbelleğidir geçerli kullanıcının belgeler ve ayarlar klasörünü yerel ayarları dizini altındaki gizli dizinler ailesidir. Bu önbellek derlemeleri, yapılandırma dosyalarını, uygulama ve kullanıcı ayarlarını ve veri dizini de dahil olmak üzere tüm uygulama dosyalarını barındırır. Önbellek, uygulamanın veri dizininin en son sürüme geçirmek için sorumludur. Veri geçişi hakkında daha fazla bilgi için bkz: [erişme yerel ve uzak veri ClickOnce uygulamalarında](../deployment/accessing-local-and-remote-data-in-clickonce-applications.md).  
  
 Uygulama depolama alanı için tek bir konum sağlayarak [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] kullanıcıdan bir uygulamanın fiziksel yüklenmesini yönetme görevini devralır. Derlemeler ve veri dosyalarının tüm uygulamalar için tutarak uygulamalarını yalıtmak önbellek da yardımcı olur ve farklı sürümlerine birbirinden ayırın. Örneğin, yükseltme yaptığınızda bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama, sürüm ve veri kaynaklarını önbelleğinde kendi dizinleriyle birlikte sağlanır.  
  
## <a name="cache-storage-quota"></a>Önbellek depolama kotası  
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] çevrimiçi olarak barındırılan uygulamalar kaplar boşluk boyutunu kısıtlayan bir kota tarafından kısıtlı [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] önbelleği. Önbellek boyutu kullanıcının tüm çevrimiçi uygulamalar için geçerlidir; tek bir kısmen güvenilen, çevrimiçi uygulama yarısı kota alanı kaplayan sınırlıdır. Yüklü uygulamalar önbellek boyutuyla sınırlı değildir ve önbellek sınırınızı sayılmaz. Tüm [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulamalar, önbelleğe yalnızca geçerli sürümü ve daha önce yüklü olan sürümü korur.  
  
 Depolama için 250 MB istemci bilgisayarlarında varsayılan olarak, çevrimiçi olması [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulamalar. Veri dosyaları bu sınırında sayılmaz. Bir Sistem Yöneticisi genişletmek veya bir DWORD değeri HKEY_CURRENT_USER\Software\Classes\Software\Microsoft\Windows\CurrentVersion\Deployment\OnlineAppQuotaInKB kayıt defteri anahtarını değiştirerek belirli bir istemci bilgisayar üzerinde bu kotayı azaltın Bu önbellek boyutu kilobayt cinsinden ifade eder. Örneğin, 50 MB önbellek boyutunu azaltmak için bu değer 51200 yapmanız gerekir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ClickOnce Uygulamalarında Yerel ve Uzak Veri Erişimi](../deployment/accessing-local-and-remote-data-in-clickonce-applications.md)