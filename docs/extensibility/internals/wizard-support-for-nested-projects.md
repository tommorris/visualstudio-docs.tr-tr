---
title: "İç içe geçmiş projeleri için sihirbaz desteği | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Add Item wizard
- nested projects, wizard support
- New Project wizard
ms.assetid: 1b496acc-b326-4cdb-bb48-e3b5c6f12e05
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 7191d31d4ec53fb26f4ab20114201836f1b58fc5
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="wizard-support-for-nested-projects"></a>İç içe geçmiş projeleri için sihirbaz desteği
İç içe geçmiş projeleri için ana proje uygulayabilirsiniz iki sihirbaz IDE çalıştırır: **yeni proje** Sihirbazı'nı ve **Öğe Ekle** Sihirbazı.  
  
 Bir kullanıcı başlıyorsa **yeni proje** seçerek Sihirbazı **Proje Ekle** tıklatıp **yeni proje** Dosya menüsünden veya seçerek **Ekle** ve sağ **yeni proje** IDE Çözüm Gezgini'nde çalıştıran **AddProject** komut ve üst projenin uyarlamasını **AddProject**komut ya da bir şablon proje dosyası ya da bir bağlam parametreleri kümesini içeren bir Sihirbazı'nı (.vsz) dosyası döndürür.  
  
 Benzer şekilde, bir üst projenin uyarlamasını **addItem** sihirbazları farklı bir bağlam parametreleri kümesini içeren bir .vsz dosyası döndürür.  
  
 Sihirbazları hakkında daha fazla bilgi için bkz: [Sihirbazı'nı (. Vsz) dosya](../../extensibility/internals/wizard-dot-vsz-file.md), [bağlam parametreleri](../../extensibility/internals/context-parameters.md) ve [proje ve öğe şablonlarını kaydetme](../../extensibility/internals/registering-project-and-item-templates.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy>   
 [İç içe geçme projeleri](../../extensibility/internals/nesting-projects.md)