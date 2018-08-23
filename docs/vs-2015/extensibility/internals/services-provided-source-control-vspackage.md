---
title: Sağlanan hizmetler (kaynak denetimi VSPackage'ı) | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- services, source control packages
- source control packages, services
ms.assetid: 9db07d70-87d2-4401-bc88-e3a49d81e9a2
caps.latest.revision: 16
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: aff288f68f32d3850cfa92d5999febd1c65572e1
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42694933"
---
# <a name="services-provided-source-control-vspackage"></a>Sağlanan Hizmetler (Kaynak Denetimi VSPackage’ı)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [hizmetler (kaynak denetimi VSPackage'ı) sağlanan](https://docs.microsoft.com/visualstudio/extensibility/internals/services-provided-source-control-vspackage).  
  
Yönelik birincil mekanizmadır üzerinden işlevselliği Vspackage'lar arasında ve Visual Studio tümleşik geliştirme ortamı (IDE) ve kendi yüklü Vspackage'lar arasında paylaşılan hizmetlerdir. Hizmetleri ve Visual Studio IDE'de önemini ayrıntılı açıklaması için bkz:[kullanma ve sağlama Hizmetleri](../../extensibility/using-and-providing-services.md).  
  
## <a name="the-source-control-service"></a>Kaynak denetimi hizmeti  
 Visual Studio, hizmetlerin, IDE düzeyi hizmetler ve paket düzeyinde hizmetlerinin iki katman sağlar. Visual Studio IDE, IDE düzeyi Hizmetleri yerel olarak sağlar. Kaynak Denetim paketi bu hizmetlerden bazıları tüketir. VSPackage olarak kaynak denetimi paketi, kaynak denetim işlevselliğini bir özel kaynak denetimi hizmetini kendi sağlayarak paylaşır. Kaynak Denetim paketi, Visual Studio IDE tarafından kullanılabilecek bir sözleşme biçiminde tarafından uygulanan kaynak denetimi ile ilgili arabirimler kümesini yalıtır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Tasarım öğeleri](../../extensibility/internals/source-control-vspackage-design-elements.md)

