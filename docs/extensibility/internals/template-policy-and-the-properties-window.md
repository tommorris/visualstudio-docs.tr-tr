---
title: Şablon ilke ve Özellikler penceresini | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- Properties window, template policy
ms.assetid: 1d8019d3-5e57-47ba-b358-526b0796a63b
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 759864533aa5bd3455a4e01c6642817107abb1a3
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31130048"
---
# <a name="template-policy-and-the-properties-window"></a>Şablon ilke ve Özellikler penceresi
Proje içinde Kurumsal Şablonu proje içerdiğinde bu kurumsal Şablonu proje ilkesini zorunlu kılabilir. Şablon ilke özelliklerinin varsayılan değerlerini ayarlamak, özelliklerini Gizle, özellikleri ekleyin ve benzeri için kullanılan kısıtlayan bir sistem olur.  
  
 Bilgileri görünümünü denetlemek için Şablon ilke kullanarak **özellikleri** penceredir uygulama öğesinden farklı <xref:Microsoft.VisualStudio.Shell.Interop.IVsPerPropertyBrowsing>. <xref:Microsoft.VisualStudio.Shell.Interop.IVsPerPropertyBrowsing> nesne özellikleri çözüm veya proje düzeyinde sınırlamak için Şablon ilke kullanılabilse de bileşen düzeyinde nesne özellikleri işler. Diğer bir deyişle  
  
-   Üzerinde yöntemleri uygulamak <xref:Microsoft.VisualStudio.Shell.Interop.IVsPerPropertyBrowsing> içinde görüntüleneceğini belirlemek için **özellikleri** belirli nesneler için Pencere  
  
-   Şablon ilke içinde görüntüleneceğini belirlemek için çözüm ve proje düzeyinde kullanın **özellikleri** daha önce belirtilen nesneler için Pencere  
  
 Seçmeli olarak belirli özelliklerinde sınırlamak için Şablon ilke kullanarak **özellikleri** bir proje öğesi belirtilen türde penceresinde seçili **Çözüm Gezgini** tüm üyeleri için yararlı olabilir bir proje üzerinde çalışan geliştirme ekibi. Örneğin, şablonu İlkesi'ni kullanarak, bağlantı dizesi için tüm bilgileri bir veritabanında, geliştiricilerin ayarlayın ve salt okunur bağlantı dizesi yapın. Bu şekilde, veri erişimi için doğru yolu, her geliştirici güvence altına almak için basit bir yol kullanır sağlayabilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPerPropertyBrowsing>   
 [Özellikleri Genişletme](../../extensibility/internals/extending-properties.md)