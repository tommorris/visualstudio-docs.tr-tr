---
title: "Test etmek için ClickOnce uygulamaları dağıtma ve üretim sunucuları teslim etmeden | Microsoft Docs"
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
- ClickOnce applications, deploying without resigning
- ClickOnce deployment, without resigning
- application updates, ClickOnce
- update location [ClickOnce]
- deploymentProvider tag
- manifests [ClickOnce]
ms.assetid: 1218a98d-1ad5-4eef-95dd-0e0b3c44168c
caps.latest.revision: "10"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.openlocfilehash: 91261e0bb70092861f216333bd73a11dc07790ba
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="deploying-clickonce-applications-for-testing-and-production-servers-without-resigning"></a>Sınama ve Üretim Sunucuları için Teslim Etmeden ClickOnce Uygulamaları Dağıtma
Bu konuda, .NET Framework sürüm 3.5 yeniden imzalama veya ClickOnce değiştirmeden birden çok ağ konumundan ClickOnce uygulamalarının dağıtımını sağlayan bildirimleri sunulan ClickOnce yeni bir özellik açıklanmaktadır.  
  
> [!NOTE]
>  Bildirimin hala uygulamaların yeni sürümleri dağıtmak için tercih edilen yöntemdir. Mümkün olduğunda, resigning yöntemini kullanın. Daha fazla bilgi için bkz: [Mage.exe (bildirim üretme ve düzenleme aracı)](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool).  
  
 Üçüncü taraf geliştiriciler ve ISV'ler bu özellik için kendi uygulamalarını güncelleştirmelerini müşterilerine kolaylaştırma katılımı. Bu özellik, aşağıdaki durumlarda kullanılabilir:  
  
-   Bir uygulama, ilk yükleme haricinde bir uygulama güncelleştirilirken.  
  
-   Uygulamanın bir bilgisayarda yalnızca bir yapılandırma olduğunda. Örneğin, bir uygulama iki farklı veritabanlarına işaret edecek şekilde yapılandırdıysanız, bu özelliği kullanamazsınız.  
  
## <a name="excluding-deploymentprovider-from-deployment-manifests"></a>Dağıtım bildirimleri deploymentProvider hariç  
 .NET Framework 2.0 ve .NET Framework 3. 0'çevrimdışı kullanılabilirlik için sisteme yüklenen herhangi bir ClickOnce uygulaması belirtmelisiniz bir `deploymentProvider` kendi dağıtım bildiriminde. `deploymentProvider` Güncelleştirme konumu olarak; genellikle adlandırılır ClickOnce uygulama güncelleştirmelerini denetleyecek konum değil. Dağıtımlarını imzalamak uygulama yayımcıları gereksinimini ile birlikte bu gereksinim, bir satıcıdan veya diğer üçüncü taraf bir ClickOnce uygulamasını güncelleştirmek için bir şirket zor hale. Ayrıca, aynı uygulama aynı ağ üzerinde birden fazla konumdan dağıtmak daha zor kılar.  
  
 .NET Framework 3. 5'te ClickOnce yapılan değişikliklerle kendi ağı üzerinde uygulamayı sonra dağıtabileceğiniz başka bir kuruluştaki bir ClickOnce uygulamasını sağlamak bir üçüncü taraf mümkündür.  
  
 Bu özelliğin avantajlarından yararlanmak için ClickOnce uygulaması geliştiricileri içermemelidir `deploymentProvider` dağıtım bildirimlerinden. Bu hariç anlamına gelir `-providerUrl` dağıtımı oluşturduğunuzda, bağımsız değişken bildirimlerini Mage.exe veya emin **başlatma konumu** metin kutusunda **uygulama bildirimi** sekmesini boş bırakılır varsa, dağıtım bildirimleri MageUI.exe ile oluşturuluyor.  
  
## <a name="deploymentprovider-and-application-updates"></a>deploymentProvider ve uygulama güncelleştirmeleri  
 .NET Framework 3.5 ile başlayarak, artık belirtmek elinizde bir `deploymentProvider` hem çevrimiçi hem de çevrimdışı kullanım için ClickOnce uygulaması dağıtmak için dağıtım bildiriminizin. Bu paket ve dağıtım kendiniz oturum ancak uygulamayı kendi ağları üzerinden dağıtmak diğer şirketlerin izin gerek burada senaryoyu destekler.  
  
 Anımsaması anahtar noktası olan hariç tutan uygulamalar bir `deploymentProvider` içeren bir güncelleştirme Sevk edene kadar yükleme konumlarını güncelleştirme sırasında değiştiremez `deploymentProvider` yeniden etiketi.  
  
 Aşağıda, bu noktayı açıklığa kavuşturmak için iki örnek verilmiştir. İlk örnekte sahip olmayan bir ClickOnce uygulaması yayımlama `deploymentProvider` etiketini ve http://www.adatum.com/MyApplication/ adresinden yükleme kullanıcılara isteyin. Sonraki güncelleştirme http://subdomain.adatum.com/MyApplication/ adresinden uygulamasının yayımlamak istediğiniz karar verirseniz, bu http://www.adatum.com/MyApplication/ içinde bulunan dağıtım bildiriminde gösterir hiçbir şekilde gerekir. İkisinden birini yapabilirsiniz:  
  
-   Önceki sürümünü kaldırmak için kullanıcılarınıza söylemeniz ve yeni konumdan yeni sürümü yükleyin.  
  
-   Bir güncelleştirme, http://www.adatum.com/MyApplication/ üzerinde içeren bir `deploymentProvider` http://www.adatum.com/MyApplication/ adresine işaret. Ardından, daha sonra başka bir güncelleştirme sürüm `deploymentProvider` http://subdomain.adatum.com/MyApplication/ adresine işaret eden.  
  
 İkinci örnekte belirten bir ClickOnce uygulaması yayımlama `deploymentProvider`, ve ardından bunu kaldırmaya karar verirsiniz. Bir kez yeni sürümü olmadan `deploymentProvider` indirildi istemciler için sahip olan uygulamanızın bir sürümü kullanıma kadar güncelleştirmeler için kullanılan yolu yeniden yönlendirmek mümkün olmaz `deploymentProvider` geri. İlk örnek olarak, `deploymentProvider` başlangıçta yeni konumunuzu değil de geçerli güncelleştirme konumunu işaret etmelidir. Eklemeye çalışırsanız, bu durumda, bir `deploymentProvider` http://subdomain.adatum.com/MyApplication/ adresine başvuruyor ve ardından sonraki güncelleştirme başarısız olur.  
  
## <a name="creating-a-deployment"></a>Bir dağıtımı oluşturma  
 Farklı ağ konumlardan dağıtılabilir dağıtımları oluşturma konusunda adım adım yönergeler için bkz: [izlenecek yol: ClickOnce uygulaması bu mu değil gerektiren Re-Signing'el ile dağıtma ve bu korur markalama bilgileri](../deployment/walkthrough-manually-deploying-a-clickonce-application-that-does-not-require-re-signing-and-that-preserves-branding-information.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Mage.exe (bildirim üretme ve düzenleme aracı)](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool)   
 [MageUI.exe (bildirim üretme ve düzenleme aracı, grafik istemci)](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client)