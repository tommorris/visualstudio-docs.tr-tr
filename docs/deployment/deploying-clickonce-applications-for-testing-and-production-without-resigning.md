---
title: Test etmek için ClickOnce uygulamaları dağıtma ve üretim sunucuları teslim etmeden | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
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
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 57b4761ed7f0b223e459fc1ac77ad93c546e02dc
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/17/2018
ms.locfileid: "34266195"
---
# <a name="deploying-clickonce-applications-for-testing-and-production-servers-without-resigning"></a>Sınama ve Üretim Sunucuları için Teslim Etmeden ClickOnce Uygulamaları Dağıtma
Bu makalede .NET Framework sürüm 3.5 yeniden imzalama veya ClickOnce değiştirmeden birden çok ağ konumundan ClickOnce uygulamalarının dağıtımını sağlayan bildirimleri sunulan ClickOnce özelliğidir.  
  
> [!NOTE]
>  Bildirimin hala uygulamaların yeni sürümleri dağıtmak için tercih edilen yöntemdir. Mümkün olduğunda, resigning yöntemini kullanın. Daha fazla bilgi için bkz: [Mage.exe (bildirim üretme ve düzenleme aracı)](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool).  
  
 Üçüncü taraf geliştiriciler ve ISV'ler, bu özellik için kendi uygulamalarını güncelleştirmelerini müşterilerine kolaylaştırma seçebilirsiniz. Bu özellik, aşağıdaki durumlarda kullanılabilir:  
  
-   Bir uygulamanın ilk yüklenmesi için bir uygulama güncelleştirilirken.  
  
-   Uygulamanın bir bilgisayarda yalnızca bir yapılandırma olduğunda. Örneğin, bir uygulama iki farklı veritabanlarına işaret edecek şekilde yapılandırdıysanız, bu özelliği kullanamazsınız.  
  
## <a name="excluding-deploymentprovider-from-deployment-manifests"></a>Dağıtım bildirimleri deploymentProvider hariç  
 .NET Framework 2.0 ve .NET Framework 3. 0'çevrimdışı kullanılabilirlik için sisteme yüklenen herhangi bir ClickOnce uygulaması listelenmelidir bir `deploymentProvider` kendi dağıtım bildiriminde. `deploymentProvider` Güncelleştirme konumu olarak; genellikle adlandırılır, burada ClickOnce uygulama güncelleştirmelerini denetler konumdur. Dağıtımlarını imzalamak uygulama yayımcıları gereksinimini yanı sıra bu gereksinim bir satıcıdan veya diğer üçüncü taraf bir ClickOnce uygulamasını güncelleştirmek için bir şirket zor hale. Ayrıca, aynı uygulama aynı ağ üzerinde birden fazla konumdan dağıtmak daha zor kılar.  
  
 .NET Framework 3. 5'te ClickOnce yapılan değişikliklerle kendi ağı üzerinde uygulamayı sonra dağıtabileceğiniz başka bir kuruluştaki bir ClickOnce uygulamasını sağlamak bir üçüncü taraf mümkündür.  
  
 Bu özelliğin avantajlarından yararlanmak için ClickOnce uygulaması geliştiricileri içermemelidir `deploymentProvider` dağıtım bildirimlerinden. Bu gereksinim, içermemelidir anlamına gelir `-providerUrl` dağıtımı oluşturduğunuzda, bağımsız değişken bildirimlerini Mage.exe ile. Veya MageUI.exe ile dağıtım bildirimleri oluşturma, emin olmanız gerekir **başlatma konumu** metin kutusunda **uygulama bildirimi** sekmesini boş bırakılır.  
  
## <a name="deploymentprovider-and-application-updates"></a>deploymentProvider ve uygulama güncelleştirmeleri  
 .NET Framework 3.5 ile başlayarak, artık belirtmek elinizde bir `deploymentProvider` hem çevrimiçi hem de çevrimdışı kullanım için ClickOnce uygulaması dağıtmak için dağıtım bildiriminizin. Bu değişiklik, paket ve dağıtım kendiniz oturum ancak uygulamayı kendi ağları üzerinden dağıtmak diğer şirketlerin izin gerek burada senaryoyu destekler.  
  
 Anımsaması önemli olan nokta olan hariç tutan uygulamalar bir `deploymentProvider` içeren bir güncelleştirme Sevk edene kadar yükleme konumlarını güncelleştirme sırasında değiştiremez `deploymentProvider` yeniden etiketi.  
  
 Aşağıda, bu noktayı açıklığa kavuşturmak için iki örnek verilmiştir. İlk örnekte sahip olmayan bir ClickOnce uygulaması yayımlama `deploymentProvider` etiketini ve buradan yüklemek için kullanıcılar isteyin http://www.adatum.com/MyApplication/. Uygulamayı bir sonraki güncelleştirmesine yayımlamak istediğiniz kullanmaya karar verirseniz http://subdomain.adatum.com/MyApplication/, bu dağıtım bildiriminde bulunur gösterir hiçbir şekilde http://www.adatum.com/MyApplication/. İkisinden birini yapabilirsiniz:  
  
-   Önceki sürümünü kaldırmak için kullanıcılarınıza söylemeniz ve yeni konumdan yeni sürümü yükleyin.  
  
-   Bir güncelleştirme içerir http://www.adatum.com/MyApplication/ içeren bir `deploymentProvider` işaret eden http://www.adatum.com/MyApplication/. Ardından, daha sonra başka bir güncelleştirme sürüm `deploymentProvider` işaret eden http://subdomain.adatum.com/MyApplication/.  
  
 İkinci örnekte belirten bir ClickOnce uygulaması yayımlama `deploymentProvider`, ve ardından bunu kaldırmaya karar verirsiniz. Bir kez yeni sürümü olmadan `deploymentProvider` indirilir, istemcilere sahip olan uygulamanızın bir sürümü kullanıma kadar güncelleştirmeler için kullanılan yolu yönlendirilemiyor `deploymentProvider` geri. İlk örnek olarak, `deploymentProvider` başlangıçta yeni konumunuzu değil de geçerli güncelleştirme konumunu işaret etmelidir. Eklemeye çalışırsanız, bu durumda, bir `deploymentProvider` , başvurduğu http://subdomain.adatum.com/MyApplication/, sonra da sonraki güncelleştirme başarısız.  
  
## <a name="creating-a-deployment"></a>Bir dağıtımı oluşturma  
 Farklı ağ konumlardan dağıtılabilir dağıtımları oluşturma konusunda adım adım yönergeler için bkz: [izlenecek yol: ClickOnce uygulaması bu mu değil gerektiren Re-Signing'el ile dağıtma ve bu korur markalama bilgileri](../deployment/walkthrough-manually-deploying-a-clickonce-app-no-re-signing-required.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Mage.exe (bildirim üretme ve düzenleme aracı)](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool)   
 [MageUI.exe (Bildirim Oluşturma ve Düzenleme Aracı, Grafik İstemci)](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client)