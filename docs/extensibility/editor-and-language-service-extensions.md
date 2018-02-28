---
title: "Düzenleyici ve dil uzantıları hizmet | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK]
ms.assetid: 5653bac9-724f-4948-a820-68ce6aa96365
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 59de764dfcb976dfac303f44a67340e117ae5e06
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="editor-and-language-service-extensions"></a>Düzenleyici ve dil hizmeti uzantıları
Visual Studio kod düzenleyicisini çoğu özelliklerini genişletebilirsiniz. Düzenleyici, Windows Presentation Foundation (WPF) dayanır ve yönetilen kodda yazılır. Tasarımlar, Visual Studio'nun önceki sürümleri, bu tasarım farklıdır rağmen aynı özelliklerin çoğunu sağlar. Düzenleyiciyi genişletmek için Yönetilen Genişletilebilirlik Çerçevesi (MEF) kullanın.  
  
 Visual Studio SDK'sı olarak bilinir bağdaştırıcıları sağlar *dolgular* önceki sürümleri için yazılmış VSPackages desteklemek için. Bununla birlikte, varolan bir VSPackage varsa, daha iyi performans ve güvenilirlik elde etmek için yeni teknoloji güncelleştirme öneririz.  
  
## <a name="related-topics"></a>İlgili Konular  
  
|Başlık|Açıklama|  
|-----------|-----------------|  
|[Düzenleyici Öğesi Şablonuyla Uzantı Oluşturma](../extensibility/creating-an-extension-with-an-editor-item-template.md)|Düzenleyici öğe şablonlarını kullanarak giriş.|  
|[Düzenleyiciyi ve Dil Hizmetlerini Genişletme](../extensibility/extending-the-editor-and-language-services.md)|Tasarım ve çekirdek Düzenleyicisi özellikleri tanıtır ve genişletmek nasıl Göster belgelere bağlantılar.|  
|[Eski arabirimleri Düzenleyicisi'nde](../extensibility/legacy-interfaces-in-the-editor.md)|Var olan koddan çekirdek Düzenleyicisi'ne erişmek açıklanmaktadır belgelere bağlantılar.|  
|[Özel Düzenleyiciler ve Tasarımcılar Oluşturma](../extensibility/creating-custom-editors-and-designers.md)|Özel düzenleyici oluşturma açıklayan belgelere bağlantılar.|  
|[Eski Dil Hizmeti Genişletilebilirliği](../extensibility/internals/legacy-language-service-extensibility.md)|Visual Studio'ya programlama dilleri tümleştirme açıklayan belgelerin bağlantıları.|  
|[Managed Extensibility Framework (MEF)](/dotnet/framework/mef/index)|Yönetilen Genişletilebilirlik Çerçevesi (MEF) sunar.|  
|[Windows Presentation Foundation](/dotnet/framework/wpf/index)|Windows Presentation Foundation (WPF) sunar.|