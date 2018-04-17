---
title: Eski arabirimleri Düzenleyicisi'nde | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy
ms.assetid: 741d45f5-0ea3-4614-972a-8728fe054e07
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 64e867430c2ae55f530bdb66844240a887bd5545
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="legacy-interfaces-in-the-editor"></a>Eski arabirimleri Düzenleyicisi'nde
Visual Studio düzenleyicisinde eski arabirimlerinden erişebilir. Visual Studio SDK'sı olarak bilinir bağdaştırıcıları içerir *dolgular*, yeni Düzenleyicisi ile etkileşim kurmak bu arabirimleri etkinleştirin. Bununla birlikte, yeni API Düzenleyicisi kullanmak için eski kodunuzu güncelleştirmenizi öneririz. Kodunuzu daha iyi performans ve Windows Presentation Foundation (WPF) ve Yönetilen Genişletilebilirlik Çerçevesi (MEF) gibi yeni teknolojileri kullanabilirsiniz.  
  
## <a name="related-topics"></a>İlgili Konular  
  
|Başlık|Açıklama|  
|-----------|-----------------|  
|[Eski kod düzenleyicisine uyarlama](../extensibility/adapting-legacy-code-to-the-editor.md)|Kodunuzu yeni düzenleyiciye uyum açıklanmaktadır.|  
|[Düzenleyici bağdaştırıcıları ile yeni veya değiştirilmiş davranışı](../extensibility/new-or-changed-behavior-with-editor-adapters.md)|Nasıl Düzenleyicisi bağdaştırıcıları davranışını düzenleyicisinin önceki sürümlerinden farklı açıklanmaktadır.|  
|[İçinde çekirdek Düzenleyicisi](../extensibility/inside-the-core-editor.md)|Düzenleyicinin önceki sürümlerinden farklı bileşenleri açıklar.|  
|[Eski API kullanarak çekirdek Düzenleyici örneği](../extensibility/instantiating-the-core-editor-by-using-the-legacy-api.md)|Eski API çekirdek Düzenleyici örneği oluşturmak için nasıl kullanılacağını açıklar.|  
|[Düzenleyici oluşturucuları](../extensibility/editor-factories.md)|Eski API ile Düzenleyicisi oluşturucuları kullanımı açıklanmaktadır.|  
|[Nasıl yapılır: Düzenleyici dosya türlerini kaydetme](../extensibility/how-to-register-editor-file-types.md)|Bir dosya adı uzantısı, düzenleyici bağlantı açıklanmaktadır.|  
|[İzlenecek yol: bir çekirdek düzenleyici oluşturma ve bir düzenleyici dosya türü kaydetme](../extensibility/walkthrough-creating-a-core-editor-and-registering-an-editor-file-type.md)|Bir çekirdek düzenleyici oluşturma ve bir dosya adı uzantısı Bağla açıklanmaktadır.|  
|[Nasıl yapılır: içerik düzenleyicileri açısından sağlayın](../extensibility/how-to-provide-context-for-editors.md)|Bağlam için düzenleyici sağlamayı açıklar.|  
|[Dil Hizmetleri ve çekirdek Düzenleyicisi](../extensibility/language-services-and-the-core-editor.md)|Bir dil hizmeti ve bir düzenleyici arasındaki etkileşimler açıklanmaktadır.|  
|[Eski API kullanarak metin arabelleği erişme](../extensibility/accessing-the-text-buffer-by-using-the-legacy-api.md)|Eski API kullanarak metin arabelleği erişmeye açıklanmaktadır.|  
|[Eski API kullanarak getirip metin görünümü erişme](../extensibility/accessing-thetext-view-by-using-the-legacy-api.md)|Metin görünümü eski API kullanarak erişmek açıklanmaktadır.|  
|[Eski API'sini kullanarak kod Windows özelleştirme](../extensibility/customizing-code-windows-by-using-the-legacy-api.md)|Eski API'sini kullanarak kod windows özelleştirileceği açıklanmaktadır.|  
|[Eski API kullanarak metin katmanları erişme](../extensibility/accessing-text-layers-by-using-the-legacy-api.md)|Eski API kullanarak metin farklı katmanlar erişmeye açıklanmaktadır.|  
|[Metin işaretçileri eski API ile kullanma](../extensibility/using-text-markers-with-the-legacy-api.md)|Eski API kullanarak metin işaretçileri eklemeyi açıklar.|  
|[Düzenleyici denetimleri ve menüleri eski API kullanarak özelleştirme](../extensibility/customizing-editor-controls-and-menus-by-using-the-legacy-api.md)|Düzenleyici denetimleri eski API kullanarak özelleştirebileceğiniz açıklanmaktadır.|  
|[Yönetme Geri Al ve eski API'yi kullanarak Yinele](../extensibility/managing-undo-and-redo-by-using-the-legacy-api.md)|Geri alma yönetmek ve eski API kullanarak Yinele açıklanmaktadır.|  
|[Nasıl yapılır: Bul uygulamak ve mekanizmasını değiştirin](../extensibility/how-to-implement-the-find-and-replace-mechanism.md)|Bul yönetmek ve eski API kullanarak değiştirin açıklanmaktadır.|  
|[Nasıl yapılır: dosya değişiklik bildirimlerini bastır](../extensibility/how-to-suppress-file-change-notifications.md)|Eski API kullanarak dosya değişiklik bildirimlerini bastır açıklanmaktadır.|  
|[Özel Düzenleyiciler ve Tasarımcılar Oluşturma](../extensibility/creating-custom-editors-and-designers.md)|Özel düzenleyicileri ve tasarımcıları nasıl oluşturulacağını açıklar.|  
|[Eski Dil Hizmeti Geliştirme](../extensibility/internals/developing-a-legacy-language-service.md)|Özelleştirme olanağı sağlayan özellikleri hakkında belge bağlantılar sağlar [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] dil hizmeti için destek ekleyerek çekirdek Düzenleyici.|  
|[Yazı tipleri ve renkler kullanarak](../extensibility/using-fonts-and-colors.md)|Yazı tipleri ve renkler eski arabirimleriyle kullanımı açıklanmaktadır.|