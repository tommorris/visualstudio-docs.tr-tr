---
title: Şablon İlkesi ve Özellikler penceresinde | Microsoft Docs
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
- Properties window, template policy
ms.assetid: 1d8019d3-5e57-47ba-b358-526b0796a63b
caps.latest.revision: 16
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 9f8b2085818c539fe0e751a63562496363b43555
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42691264"
---
# <a name="template-policy-and-the-properties-window"></a>Şablon İlkesi ve Özellikler Penceresi
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [Şablon İlkesi ve Özellikler penceresinde](https://docs.microsoft.com/visualstudio/extensibility/internals/template-policy-and-the-properties-window).  
  
Bir proje içinde bir kuruluş şablonu projesi içerdiğinde, kuruluş şablon proje ilkesini zorunlu kılabilir. Şablon İlkesi özelliklerin varsayılan değerlerini ayarlamak, özellikleri Gizle, özellikleri ekleyin ve benzeri için kullanılan bir kısıtlama sistemi haline gelir.  
  
 Bilgilerin görüntülenmesini denetlemek için şablon İlkesi'ni kullanarak **özellikleri** penceredir uygulama öğesinden farklı <xref:Microsoft.VisualStudio.Shell.Interop.IVsPerPropertyBrowsing>. <xref:Microsoft.VisualStudio.Shell.Interop.IVsPerPropertyBrowsing> Şablon İlkesi çözüm veya proje düzeyinde nesne özellikleri kısıtlamak için kullanılabilse de bileşen düzeyinde nesne özellikleri işler. Diğer bir deyişle  
  
-   Üzerinde yöntemleri uygulamak <xref:Microsoft.VisualStudio.Shell.Interop.IVsPerPropertyBrowsing> ne görüntülenen belirlemek için **özellikleri** belirli nesneler için Pencere  
  
-   Şablon İlkesi çözüm ve proje düzeyinde ne görüntülenen belirlemek için kullanın. **özellikleri** daha önce belirtilen nesneler için Pencere  
  
 Belirli özellikleri seçici olarak kısıtlamak için şablon İlkesi'ni kullanarak **özellikleri** belirtilen türde bir proje öğesi zaman penceresi içinde seçili **Çözüm Gezgini** tüm üyeleri için yararlı olabilir Geliştirme ekibi bir proje üzerinde çalışıyor. Örneğin, Şablon İlkesi'ni kullanarak, tüm bağlantı dizesi bilgilerini bir veritabanında Geliştiricileriniz için ayarlamanız ve bağlantı dizesini salt okunur hale getirin. Her geliştirici güvence altına almak için basit bir yol, veri erişimi için doğru yolu kullanır, bu şekilde, sağlayabilirsiniz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPerPropertyBrowsing>   
 [Özellikleri Genişletme](../../extensibility/internals/extending-properties.md)

