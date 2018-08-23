---
title: Düzenleyici ve dil hizmeti uzantıları | Microsoft Docs
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
- editors [Visual Studio SDK]
ms.assetid: 5653bac9-724f-4948-a820-68ce6aa96365
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: e464b46185339bd1a22b433e4784154dbdb818c1
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42687777"
---
# <a name="editor-and-language-service-extensions"></a>Düzenleyici ve Dil Hizmeti Uzantıları
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [düzenleyici ve dil hizmeti uzantıları](https://docs.microsoft.com/visualstudio/extensibility/editor-and-language-service-extensions).  
  
Çoğu Visual Studio Kod Düzenleyicisi özelliklerini genişletebilirsiniz. Düzenleyici, Windows Presentation Foundation (WPF) dayanır ve yönetilen kodda yazılır. Bu tasarım, Visual Studio'nun önceki sürümlerinde tasarımları farklıdır, aynı özelliklerin çoğunu sağlar. Düzenleyiciyi genişletmek için Yönetilen Genişletilebilirlik Çerçevesi (MEF) kullanın.  
  
 Visual Studio SDK'sı olarak da bilinen bağdaştırıcıları sağlar *dolgular* önceki sürümleri için yazılmış VSPackages desteklemek için. Bununla birlikte, mevcut bir VSPackage varsa, daha iyi performans ve güvenilirlik elde etmek için yeni teknoloji güncelleştirme öneririz.  
  
## <a name="related-topics"></a>İlgili Konular  
  
|Başlık|Açıklama|  
|-----------|-----------------|  
|[Düzenleyici Öğesi Şablonuyla Uzantı Oluşturma](../extensibility/creating-an-extension-with-an-editor-item-template.md)|Düzenleyici öğesi şablonlarını kullanarak giriş.|  
|[Düzenleyiciyi ve Dil Hizmetlerini Genişletme](../extensibility/extending-the-editor-and-language-services.md)|Tasarım ve çekirdek Düzenleyici özelliklerini tanıtır ve genişletmek nasıl Göster belgelere bağlantılar.|  
|[Eski arabirimleri Düzenleyicisi](../extensibility/legacy-interfaces-in-the-editor.md)|Mevcut koddan çekirdek Düzenleyicisi'ne erişmek nasıl açıklayan belgelere bağlantılar.|  
|[Özel Düzenleyiciler ve Tasarımcılar Oluşturma](../extensibility/creating-custom-editors-and-designers.md)|Özel düzenleyicilerde nasıl oluşturulacağını açıklayan belgelere bağlantılar.|  
|[Eski Dil Hizmeti Genişletilebilirliği](../extensibility/internals/legacy-language-service-extensibility.md)|Programlama dilleri Visual Studio ile tümleştirmek nasıl açıklayan belgelere bağlantılar.|  
|[Managed Extensibility Framework (MEF)](http://msdn.microsoft.com/library/6c61b4ec-c6df-4651-80f1-4854f8b14dde)|Yönetilen Genişletilebilirlik Çerçevesi (MEF) sunar.|  
|[Windows Presentation Foundation](http://msdn.microsoft.com/library/f667bd15-2134-41e9-b4af-5ced6fafab5d)|Windows Presentation Foundation (WPF) sunar.|

