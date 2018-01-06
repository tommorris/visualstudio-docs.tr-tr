---
title: "Özellikler penceresi genel bakış | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Properties window
ms.assetid: 289ed4f2-02ac-4899-855e-42dfe57ee05f
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 1f766fe903df4f7a7ea36fb4ec1654b889457f65
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="properties-window-overview"></a>Özellikler penceresi genel bakış
**Özellikleri** penceresi windows bulunan iki ana tür seçili nesnelerin özelliklerini görüntülemek için kullanılan [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] tümleşik geliştirme ortamı (IDE). Bu iki windows türleri şunlardır:  
  
-   Çözüm Gezgini'nde sınıf görünümü ve nesne tarayıcısı gibi araç pencereleri  
  
-   Bu tür düzenleyicileri ve tasarımcıları forms Tasarımcısı, XML Düzenleyicisi'ni ve HTML düzenleyicisi olarak içeren belge pencereleri  
  
## <a name="using-the-properties-window"></a>Özellikler penceresini kullanma  
 **Özellikleri** penceresi, tek veya birden çok seçili öğe özelliklerini görüntüler. Birden çok öğe seçildiğinde, seçilen tüm nesneler için tüm özellikleri kesişimi görüntülenir.  
  
 Seçili nesneyi bir form Tasarım penceresini veya COM + meta verileri kullanarak HTML düzenleyicisi içinde ilgili olayları görüntülenir **özellikleri** penceresi. Örneğin, bir düğme seçin ve onun ilişkili olayları görüntüleyen bir `OnClick` bu düğme bağlantılı olay.  
  
 Görüntülenen olayları **özellikleri** penceresi koduna bağlı nesnelerle birincil olarak kullanılır. Kodu ile yapmak için herhangi bir şey yok bir dosya biçimi düzenliyorsanız, herhangi bir olayı olmasını yapmayacağınız. Olaylar yalnızca görüntülenir **özellikleri** kodu ve belirli nesneler ile ilişkilendirilmiş belirli olaylar çalıştıran arasında bir bağlama olduğunda penceresi. Buna örnek olarak, bu nesne etkinleştirildiğinde, yürüten seçili nesnenin arka plan kod olacaktır.  
  
 Aşağıdaki tabloda tarafından kullanılan birincil arabirimleri listeler **özellikleri** penceresi.  
  
|Arabirim adı|Açıklama|  
|--------------------|-----------------|  
|<xref:Microsoft.VisualStudio.Shell.Interop.ICategorizeProperties>|Kategorilere listesini sağlar **özellikleri** penceresi ve her bir özellik için bir kategori eşler.|  
|[IDispatch arabirimi](https://msdn.microsoft.com/library/windows/desktop/ms221608.aspx)|Bir nesnenin yöntemleri ve programlama araçları ve Otomasyon destekleyen diğer uygulamalar için özellikler sunar.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IProvidePropertyBuilder>|Adlı üç nokta (...) düğmeler sağlar *oluşturucular* nesne tarafından uygulanan modal iletişim windows açın. Bir değer kolayca bir metin alanı kullanıcı tarafından yazılan değil olduğunda kullanılır. Örneğin, sizin için RGB değerini belirleyen bir renk seçici açmak için kullanılabilir.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer>|Görüntülenen bilgileri güncelleştirmek için kullanılan nesneleri erişim sağlayan **özellikleri** penceresi. <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer>VSPackages tarafından görüntülenecek ilgili özellikleri seçilebilir nesneleriyle içeren her bir pencere için uygulanır.|  
|<xref:Microsoft.VisualStudio.OLE.Interop.ITypeInfo>|Bir arabirim ve bir yapı alanları yöntemleri gibi bir nesne türü hakkında bilgi verilmektedir.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection>|VSPackages seçimi olayların bildirim almak ve geçerli proje hiyerarşisi, öğesi, öğenin değeri ve komut UI bağlamı hakkında bilgi almak için etkinleştirir.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsMultiItemSelect>|Birden çok seçimin erişimi olan bir ortam sağlar.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsPerPropertyBrowsing>|Görüntülenen bazı özellikleri yerelleştirilmiş adlar sağlamak için kullanılan **özellikleri** penceresi.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSelectionEvents>|Geçerli seçim, öğe değeri ya da komut UI bağlam değişiklikleri kayıtlı VSPackages bildirir.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackSelectionEx>|Geçerli seçim içindeki bir değişiklik ortamının bildirir ve yeni seçime ilgili hiyerarşi ve madde bilgilerine erişim sağlar.|  
  
 İlgili daha fazla bilgi için `IDispatch`, MSDN Kitaplığı bakın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Genişletme özellikleri](../../extensibility/internals/extending-properties.md)   
 [Özellikler Penceresi Alanları ve Arabirimleri](../../extensibility/internals/properties-window-fields-and-interfaces.md)