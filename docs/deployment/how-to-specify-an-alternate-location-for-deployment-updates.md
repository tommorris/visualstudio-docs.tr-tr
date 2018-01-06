---
title: "Nasıl yapılır: dağıtım güncelleştirmeleri için alternatif bir konum belirtme | Microsoft Docs"
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
- ClickOnce deployment, updates
- deployment update, alternative locations
ms.assetid: 7faacd35-2638-492d-80f6-6b57e5f820de
caps.latest.revision: "15"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload: multiple
ms.openlocfilehash: 637f4517734d3a0bbf86c3894c4f0fc7dd5b5e8d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-specify-an-alternate-location-for-deployment-updates"></a>Nasıl yapılır: Dağıtım Güncelleştirmeleri için Alternatif Bir Konum Belirtme
Yükleyebilirsiniz, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulamadan başlangıçta bir CD veya bir dosya paylaşımı, ancak uygulama Web'de düzenli güncelleştirmeleri denetle gerekir. Böylece, uygulamanızın kendisini Web'den kendi ilk yüklemeden sonra güncelleştirebilirsiniz Dağıtım bildiriminizi güncelleştirmeler için alternatif bir konum belirtebilirsiniz.  
  
> [!NOTE]
>  Uygulamanızı yerel olarak bu özelliği kullanmak için yüklemeye yapılandırılmış olması gerekir. Daha fazla bilgi için bkz: [izlenecek yol: bir ClickOnce uygulamasını el ile dağıtma](../deployment/walkthrough-manually-deploying-a-clickonce-application.md). Yüklerseniz ek olarak, bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] farklı bir konuma ayarlanması neden olur, ağdan uygulama [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] bu konumu ilk yükleme ve sonraki tüm güncelleştirmeler için kullanılacak. Uygulamanızı yerel olarak (örneğin, bir CD'den) yüklerseniz, ilk yükleme özgün ortam kullanılarak gerçekleştirilir ve sonraki tüm güncelleştirmeler alternatif konumu kullanır.  
  
### <a name="specifying-an-alternate-location-for-updates-by-using-mageuiexe-windows-forms-based-utility"></a>MageUI.exe (Windows Forms tabanlı yardımcı program) kullanarak güncelleştirmeleri için alternatif bir konum belirtme  
  
1.  Bir .NET Framework komut istemini açıp türü:  
  
     **mageui.exe**  
  
2.  Üzerinde **dosya** menüsünde seçin **açmak** uygulamanızın dağıtım bildirimini açın.  
  
3.  Seçin **dağıtım seçenekleri** sekmesi.  
  
4.  Metin kutusunda adlı **başlatma konumu**, uygulama güncelleştirmeleri için dağıtım bildirimini içerecek dizine URL'sini girin.  
  
5.  Dağıtım bildirimini kaydedin.  
  
### <a name="specifying-an-alternate-location-for-updates-by-using-mageexe"></a>Mage.exe kullanarak güncelleştirmeleri için alternatif bir konum belirtme  
  
1.  .NET Framework komut istemini açın.  
  
2.  Aşağıdaki komutu kullanarak güncelleştirme konumunu ayarlayın. Bu örnekte, **HelloWorld.exe.application** yolu, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] her zaman .application uzantısına sahiptir, uygulama bildirimi ve **http://adatum.com/Update/Path** URL'si [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama güncelleştirmelerini kontrol eder.  
  
     **Mage-HelloWorld.exe.application güncelleştir - ProviderUrl http://adatum.com/Update/Path**  
  
3.  Dosyayı kaydedin.  
  
    > [!NOTE]
    >  Şimdi Mage.exe ile dosyayı yeniden oturum açmanız gerekir. Daha fazla bilgi için bkz: [izlenecek yol: bir ClickOnce uygulamasını el ile dağıtma](../deployment/walkthrough-manually-deploying-a-clickonce-application.md).  
  
## <a name="net-framework-security"></a>.NET Framework Güvenliği  
 Uygulamanızı bir CD gibi çevrimdışı bir orta yükleyin ve bilgisayar çevrimiçi ise [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] ilk tarafından belirtilen URL denetler `<deploymentProvider>` güncelleştirme konumu daha yeni bir sürümü olup olmadığını belirlemek için dağıtım bildiriminde etiketi uygulama. Aşması durumunda [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] ilk yükleme dizininden yerine doğrudan buradan uygulamayı yükler ve ortak dil çalışma zamanı (CLR) uygulamanızın güven belirler kullanarak düzey `<deploymentProvider>`. Bilgisayar çevrimdışı ise veya `<deploymentProvider>` erişilemiyor, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] CD ve CLR yükler yükleme noktasında dayalı güven verir; bir CD kurulumu için bu, uygulamanızın tam güven alması anlamına gelir. Sonraki tüm güncelleştirmeler bu güven düzeyini devralır.  
  
 Tüm [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] kullanan uygulamalar `<deploymentProvider>` böylece uygulama farklı farklı bilgisayarlarda güven düzeyleri almaz açıkça uygulama bildiriminde, ihtiyaç duydukları izinleri bildirmelidir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İzlenecek yol: Bir ClickOnce uygulamasını el ile dağıtma](../deployment/walkthrough-manually-deploying-a-clickonce-application.md)   
 [ClickOnce dağıtım bildirimi](../deployment/clickonce-deployment-manifest.md)   
 [ClickOnce uygulamalarının güvenliğini sağlama](../deployment/securing-clickonce-applications.md)   
 [ClickOnce Güncelleştirme Stratejisini Seçme](../deployment/choosing-a-clickonce-update-strategy.md)