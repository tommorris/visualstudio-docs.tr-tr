---
title: İç içe projeler için sihirbaz desteği | Microsoft Docs
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
- Add Item wizard
- nested projects, wizard support
- New Project wizard
ms.assetid: 1b496acc-b326-4cdb-bb48-e3b5c6f12e05
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 4621627faae761bfe63b7fd056427a3771d21582
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42693646"
---
# <a name="wizard-support-for-nested-projects"></a>İç içe Projeler için Sihirbaz Desteği
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [iç içe projeler için sihirbaz desteği](https://docs.microsoft.com/visualstudio/extensibility/internals/wizard-support-for-nested-projects).  
  
IDE ana proje iç içe projeler için uygulayabileceğiniz iki sihirbazları çalıştırır: **yeni proje** Sihirbazı ve **Öğe Ekle** Sihirbazı.  
  
 Bir kullanıcı başlarsa **yeni proje** seçerek Sihirbazı **Proje Ekle** tıklayıp **yeni proje** Dosya menüsünden veya seçerek **Ekle** sağ **yeni proje** IDE Çözüm Gezgini'nde çalışan **AddProject** komut ve üst projenin uygulaması **AddProject**komut ya da bir şablon proje dosyası veya bir dizi bağlam parametreleri içeren bir sihirbaz (.vsz) dosyası döndürür.  
  
 Benzer şekilde, bir üst projenin uygulaması **addItem** sihirbazları farklı bir bağlam parametreleri kümesini içeren bir .vsz dosyası döndürür.  
  
 Sihirbazları hakkında daha fazla bilgi için bkz: [Sihirbazı (. Vsz) dosya](../../extensibility/internals/wizard-dot-vsz-file.md), [bağlam parametreleri](../../extensibility/internals/context-parameters.md) ve [proje ve öğe şablonlarını kaydetme](../../extensibility/internals/registering-project-and-item-templates.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy>   
 [Projeleri İç İçe Geçirme](../../extensibility/internals/nesting-projects.md)

