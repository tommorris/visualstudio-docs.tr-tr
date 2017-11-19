---
title: "Visual Studio'da hiyerarşileri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- hierarchies, Visual Studio IDE
- IDE, hierarchies
ms.assetid: 0a029a7c-79fd-4b54-bd63-bd0f21aa8d30
caps.latest.revision: "14"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 4a651267ed279fa5efaf14efb4f1f866794c5cc3
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="hierarchies-in-visual-studio"></a>Visual Studio'da hiyerarşileri
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Tümleşik geliştirme ortamı (IDE) görüntüleyen bir proje olarak bir *hiyerarşi*. IDE içinde bir hiyerarşi, her düğümün sahip olduğu ilişkili özellikler kümesi düğümlerinin ağacıdır. A *proje hiyerarşi* projenin öğeleri, öğeleri ilişkileri ve öğeleri ilişkili özellikler ve komutlar tutan bir kapsayıcıdır.  
  
 İçinde [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], hiyerarşi arabirimi kullanarak proje hiyerarşileri yönetmek <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy>. <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy> Arabirimi komutları standart komut işleyici yerine uygun hiyerarşiye penceresine proje öğelerinden çağırmayı yeniden yönlendirir.  
  
## <a name="project-hierarchies"></a>Proje hiyerarşileri  
 Her proje hiyerarşisi görüntülemek ve düzenlemek öğeleri içerir. Bu öğeler proje türüne bağlı olarak farklılık gösterir. Örneğin, bir veritabanı projesi veritabanı tabloları, veritabanı görünümleri ve saklı yordamlarını içerebilir. Bir programlama dili proje Öte yandan, büyük olasılıkla kaynak dosyaları ve bit eşlemler ve iletişim kutuları için kaynak dosyaları içerir. Hiyerarşileri, bir proje hiyerarşisi oluşturduğunuzda, size bazı eklenen esneklik iç içe.  
  
 Yeni bir proje türü oluşturduğunuzda, proje türü tamamını içinde düzenlenebilir öğeleri denetler. Ancak, projeleri desteği düzenleme sahip oldukları olmayan öğeler içerebilir. Örneğin, Visual C++ HTML dosya türü için herhangi bir özelleştirilmiş Düzenleyicisi sağlamaz olsa bile Visual C++ projeleri HTML dosyaları içerebilir.  
  
 Hiyerarşileri içerdikleri öğeleri kalıcılığı yönetin. Uygulama hiyerarşisinin hiyerarşi içindeki öğeler kalıcılığı etkileyen herhangi bir özel özellik kontrol gerekir. Örneğin, öğeleri dosyalar yerine bir havuzda nesneleri temsil ediyorsa, hiyerarşi uygulaması bu nesnelerin Kalıcılık kontrol gerekir. Kullanıcı girişi uyumlu öğeleri kaydetmek için hiyerarşi IDE yönlendirir, ancak IDE öğelerden kaydetmek için gereken tüm eylemleri denetlemez. Bunun yerine, denetiminde projesidir.  
  
 Bir kullanıcı bir öğeyi bir düzenleyicide oturum açtığında, o öğe denetimleri hiyerarşi seçilir ve etkin olan hiyerarşi olur. Seçilen hiyerarşi öğede görev yapması kullanılabilir komut kümesini belirler. Bu şekilde kullanıcı odağı izleme, kullanıcının geçerli bağlam yansıtacak şekilde hiyerarşi sağlar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Proje türleri](../../extensibility/internals/project-types.md)   
 [Seçim ve IDE içinde para birimi](../../extensibility/internals/selection-and-currency-in-the-ide.md)   
 [VSSDK örnekleri](http://aka.ms/vs2015sdksamples)