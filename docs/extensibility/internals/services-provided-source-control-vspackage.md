---
title: "Sağlanan hizmetlerin (kaynak denetimi VSPackage) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- services, source control packages
- source control packages, services
ms.assetid: 9db07d70-87d2-4401-bc88-e3a49d81e9a2
caps.latest.revision: "15"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: c30c374756578fd71dd344393b58f38cacadeb19
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="services-provided-source-control-vspackage"></a>Sağlanan hizmetlerin (kaynak denetimi VSPackage)
Hizmetleri üzerinden işlevselliği VSPackages arasında ve Visual Studio tümleşik geliştirme ortamı (IDE) ve yüklü VSPackages arasında paylaşılan birincil sistemdir. Hizmetler ve önemine Visual Studio IDE içinde ayrıntılı açıklaması için bkz:[kullanma ve servisleri](../../extensibility/using-and-providing-services.md).  
  
## <a name="the-source-control-service"></a>Kaynak denetimi hizmeti  
 Visual Studio iki katmandan Hizmetleri, IDE düzeyi Hizmetleri ve paket düzeyi hizmetler sağlar. Visual Studio IDE yerel IDE düzeyi hizmetleri sağlar. Kaynak denetimi paketi bu hizmetlerden bazılarını kullanır. Kaynak denetimi paketi bir VSPackage olarak kendi özel kaynak denetimi hizmeti sağlayarak kaynak denetim işlevselliğini paylaşır. Kaynak denetimi paketi, Visual Studio IDE tarafından kullanılan bir sözleşme biçiminde tarafından uygulanan kaynak denetimi ile ilgili arabirimler kümesi yalıtır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Tasarım öğeleri](../../extensibility/internals/source-control-vspackage-design-elements.md)