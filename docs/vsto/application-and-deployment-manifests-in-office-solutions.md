---
title: "Office çözümlerinde uygulama ve dağıtım bildirimlerini | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- manifests [Office development in Visual Studio]
- deployment manifests [Office development in Visual Studio]
- application manifests [Office development in Visual Studio]
- assemblies [Office development in Visual Studio], updating
ms.assetid: 4e9abc7c-ef9f-4cb2-a7a9-c95c5f4a1fb7
caps.latest.revision: "45"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 83bf3b48d562e5acf24fedd27954c10505454b86
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="application-and-deployment-manifests-in-office-solutions"></a>Office Çözümlerinde Uygulama ve Dağıtım Bildirimleri
  Bir uygulama bildirimi bulun ve onun derlemeleri güncelleştirmek için bir Office çözümü tarafından kullanılan bilgileri sağlayan bir XML dosyasıdır. Bir uygulama bildirimi derlemeler ve uygulama bildirimini en güncel sürümünü bulmak için gereken bilgileri sağlar sunucuda depolanan bir XML dosyası bir dağıtım bildirimi ile kullanılabilir.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
## <a name="manifest-structure-for-office-solutions"></a>Office çözümleri için bildirim yapısı  
 Visual Studio'da Office geliştirme araçları kullanılarak oluşturulan Microsoft Office çözümleri için tüm bildirimler standart ClickOnce şemasını temel alır. Office çözümleri dağıttığınızda, belge düzeyi ve VSTO eklentisi projelerine için uygulama bildirimleri ClickOnce önbelleğine bulunur. Dağıtım bildirimleri istemci bilgisayara kopyalanmaz.  
  
 Uygulama ve dağıtım bildirimlerini Office projeleri için içeriği hakkında bilgi için [uygulama bildirimleri Office çözümleri için](../vsto/application-manifests-for-office-solutions.md) ve [dağıtım bildirimleri Office çözümleri için](../vsto/deployment-manifests-for-office-solutions.md).  
  
## <a name="creating-application-and-deployment-manifests"></a>Uygulama ve dağıtım bildirimlerini oluşturma  
 Uygulama bildirimleri yapılandırma işleminin bir parçası olarak otomatik olarak oluşturulur. Belge düzeyi projesi derleme her zaman, dağıtım bildirimi konumunu özel belge özelliği olarak belgeye katıştırılır. VSTO eklentileri için dağıtım bildirimi konumunu kayıt defterinde depolanır.  
  
 Hakkında daha fazla bilgi için **Yayımlama Sihirbazı**, bkz: [tarafından ClickOnce kullanarak Office çözümü dağıtma](../vsto/deploying-an-office-solution-by-using-clickonce.md).  
  
 Office çözümleri ile çalışma hakkında daha fazla bilgi bildirimleri için bkz: [Office çözümü dağıtma](../vsto/deploying-an-office-solution.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Belge düzeyi özelleştirmeler mimarisi](../vsto/architecture-of-document-level-customizations.md)   
 [VSTO eklentileri mimarisi](../vsto/architecture-of-vsto-add-ins.md)   
 [Tasarlama ve Office çözümleri oluşturma](../vsto/designing-and-creating-office-solutions.md)   
 [Office çözümleri için uygulama bildirimleri](../vsto/application-manifests-for-office-solutions.md)   
 [Office çözümleri için dağıtım bildirimleri](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce Uygulama bildirimi](/visualstudio/deployment/clickonce-application-manifest)   
 [ClickOnce Dağıtım Bildirimi](/visualstudio/deployment/clickonce-deployment-manifest)  
  
  