---
title: "Nasıl yapılır: program aracılığıyla ClickOnce dağıtım API'sini kullanarak uygulama güncelleştirmelerini denetleme | Microsoft Docs"
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
- ClickOnce deployment, updates
- application updates
ms.assetid: 1a886310-67c8-44e5-a382-c2f0454f887d
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: 2812a12541d71d29beff453c66344f85be904f5a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-check-for-application-updates-programmatically-using-the-clickonce-deployment-api"></a>Nasıl yapılır: ClickOnce Dağıtım API'sini Kullanarak Program Aracılığıyla Uygulama Güncelleştirmelerini Denetleme
ClickOnce dağıtıldıktan sonra bir uygulamayı güncelleştirmek için iki yöntem sunar. Listedeki ilk yöntem, güncelleştirmeleri belirli aralıklarla otomatik olarak denetlemek için ClickOnce dağıtımı yapılandırabilirsiniz. İkinci yöntemde kullanan kodu yazabilirsiniz <xref:System.Deployment.Application.ApplicationDeployment> güncelleştirmeleri denetlemek için sınıf dayalı bir kullanıcı isteği gibi bir olay.  
  
 Aşağıdaki yordamları programlı bir güncelleştirme gerçekleştirmek için gereken kodu gösterir ve ayrıca program güncelleştirmesi denetimlerini etkinleştirmek için ClickOnce dağıtımını yapılandırılması anlatılmaktadır.  
  
 ClickOnce uygulaması programlı olarak güncelleştirmek için güncelleştirmeler için bir konum belirtmeniz gerekir. Bu bazen dağıtım sağlayıcısı olarak adlandırılır. Bu özelliği ayarlama konusunda daha fazla bilgi için bkz: [ClickOnce güncelleştirme stratejisini seçme](../deployment/choosing-a-clickonce-update-strategy.md).  
  
> [!NOTE]
>  Ayrıca, uygulamanızı bir konumdan dağıtmak ancak başka bir güncelleştirme için aşağıda açıklanan teknikleri kullanabilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: dağıtım güncelleştirmeleri için alternatif bir konum belirtin](../deployment/how-to-specify-an-alternate-location-for-deployment-updates.md).  
  
### <a name="to-check-for-updates-programmatically"></a>Güncelleştirmeleri programlı olarak denetlemek için  
  
1.  Tercih edilen görsel veya komut satırı araçlarını kullanarak yeni bir Windows Forms uygulaması oluşturun.  
  
2.  Güncelleştirmeleri denetlemek için seçmek için kullanıcılarınızın istediğiniz diğer kullanıcı arabirimi öğesi veya düğme, menü öğesi oluşturun. Bu öğeye ait olay işleyiciden denetlemek ve güncelleştirmeleri yüklemek için aşağıdaki yöntemi çağırın.  
  
     [!code-csharp[ClickOnceAPI#6](../deployment/codesnippet/CSharp/how-to-check-for-application-updates-programmatically-using-the-clickonce-deployment-api_1.cs)]
     [!code-cpp[ClickOnceAPI#6](../deployment/codesnippet/CPP/how-to-check-for-application-updates-programmatically-using-the-clickonce-deployment-api_1.cpp)]
     [!code-vb[ClickOnceAPI#6](../deployment/codesnippet/VisualBasic/how-to-check-for-application-updates-programmatically-using-the-clickonce-deployment-api_1.vb)]  
  
3.  Uygulamanızı derleyin.  
  
### <a name="using-mageexe-to-deploy-an-application-that-checks-for-updates-programmatically"></a>Mage.exe kullanarak güncelleştirmeleri program aracılığıyla denetleyen bir uygulamayı dağıtma  
  
-   Mage.exe açıklandığı gibi kullanarak uygulamanızı dağıtmak için yönergeleri izleyin [izlenecek yol: bir ClickOnce uygulamasını el ile dağıtma](../deployment/walkthrough-manually-deploying-a-clickonce-application.md). Dağıtım bildirimi oluşturmak için Mage.exe çağrılırken, komut satırı anahtarını kullandığınızdan emin olun `providerUrl`ve burada ClickOnce güncelleştirmeleri denetle URL'yi belirtmek için. Uygulamanızı gelen güncelleştirecekseniz [ http://www.adatum.com/MyApp ](http://www.adatum.com/MyApp), örneğin, dağıtım bildirimi oluşturmak için yapacağınız çağrı şuna benzeyebilir:  
  
    ```  
    mage -New Deployment -ToFile WindowsFormsApp1.application -Name "My App 1.0" -Version 1.0.0.0 -AppManifest 1.0.0.0\MyApp.manifest -providerUrl http://www.adatum.com/MyApp/MyApp.application  
    ```  
  
### <a name="using-mageuiexe-to-deploy-an-application-that-checks-for-updates-programmatically"></a>Güncelleştirmeleri program aracılığıyla denetleyen bir uygulamayı dağıtmak için MageUI.exe kullanma  
  
-   Mage.exe açıklandığı gibi kullanarak uygulamanızı dağıtmak için yönergeleri izleyin [izlenecek yol: bir ClickOnce uygulamasını el ile dağıtma](../deployment/walkthrough-manually-deploying-a-clickonce-application.md). Üzerinde **dağıtım seçenekleri** sekmesinde, ayarlamak **Başlat konumu** ClickOnce güncelleştirmeleri denetle uygulama bildirimi alanı. Üzerinde **Güncelleştirme Seçenekleri** sekmesi, Temizle **bu uygulama güncelleştirmeleri denetleyeceğini** onay kutusu.  
  
## <a name="net-framework-security"></a>.NET Framework Güvenliği  
 Uygulamanızı programlı güncelleştirmeyi kullanmak için tam güven izinleri olması gerekir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: dağıtım güncelleştirmeleri için alternatif bir konum belirtin](../deployment/how-to-specify-an-alternate-location-for-deployment-updates.md)   
 [ClickOnce güncelleştirme stratejisini seçme](../deployment/choosing-a-clickonce-update-strategy.md)   
 [ClickOnce Uygulamalarını Yayımlama](../deployment/publishing-clickonce-applications.md)