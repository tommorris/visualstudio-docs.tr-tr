---
title: Office çözümlerinde uygulama ve dağıtım bildirimleri
ms.custom: ''
ms.date: 02/02/2017
ms.technology: office-development
ms.prod: visual-studio-dev15
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- manifests [Office development in Visual Studio]
- deployment manifests [Office development in Visual Studio]
- application manifests [Office development in Visual Studio]
- assemblies [Office development in Visual Studio], updating
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: f3fba49e90bbe0f5350a5d778b8591ec473807be
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/11/2018
ms.locfileid: "35258008"
---
# <a name="application-and-deployment-manifests-in-office-solutions"></a>Office çözümlerinde uygulama ve dağıtım bildirimleri
  Bir uygulama bildirimi bulun ve onun derlemeleri güncelleştirmek için bir Office çözümü tarafından kullanılan bilgileri sağlayan bir XML dosyasıdır. Bir uygulama bildirimi derlemeler ve uygulama bildirimini en güncel sürümünü bulmak için gereken bilgileri sağlar sunucuda depolanan bir XML dosyası bir dağıtım bildirimi ile kullanılabilir.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
## <a name="manifest-structure-for-office-solutions"></a>Office çözümleri için bildirim yapısı  
 Visual Studio'da Office geliştirme araçları kullanılarak oluşturulan Microsoft Office çözümleri için tüm bildirimler standart ClickOnce şemasını temel alır. Office çözümleri dağıttığınızda, belge düzeyi ve VSTO eklentisi projelerine için uygulama bildirimleri ClickOnce önbelleğine bulunur. Dağıtım bildirimleri istemci bilgisayara kopyalanmaz.  
  
 Uygulama ve dağıtım bildirimlerini Office projeleri için içeriği hakkında bilgi için [uygulama bildirimleri Office çözümleri için](../vsto/application-manifests-for-office-solutions.md) ve [Office çözümleri için dağıtım bildirimleri](../vsto/deployment-manifests-for-office-solutions.md).  
  
## <a name="create-application-and-deployment-manifests"></a>Uygulama ve dağıtım bildirimlerini oluşturma  
 Uygulama bildirimleri yapılandırma işleminin bir parçası olarak otomatik olarak oluşturulur. Belge düzeyi projesi derleme her zaman, dağıtım bildirimi konumunu özel belge özelliği olarak belgeye katıştırılır. VSTO eklentileri için dağıtım bildirimi konumunu kayıt defterinde depolanır.  
  
 Hakkında daha fazla bilgi için **Yayımlama Sihirbazı**, bkz: [ClickOnce kullanarak Office çözümü dağıtma](../vsto/deploying-an-office-solution-by-using-clickonce.md).  
  
 Office çözümleri ile çalışma hakkında daha fazla bilgi bildirimleri için bkz: [Office çözümü dağıtma](../vsto/deploying-an-office-solution.md).  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Belge düzeyi özelleştirmeler mimarisi](../vsto/architecture-of-document-level-customizations.md)   
 [VSTO eklentileri mimarisi](../vsto/architecture-of-vsto-add-ins.md)   
 [Tasarlama ve Office çözümleri oluşturma](../vsto/designing-and-creating-office-solutions.md)   
 [Office çözümleri için uygulama bildirimleri](../vsto/application-manifests-for-office-solutions.md)   
 [Office çözümleri için dağıtım bildirimleri](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce Uygulama bildirimi](/visualstudio/deployment/clickonce-application-manifest)   
 [ClickOnce dağıtım bildirimi](/visualstudio/deployment/clickonce-deployment-manifest)  
  
  