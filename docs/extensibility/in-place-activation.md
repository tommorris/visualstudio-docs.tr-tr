---
title: "Yerinde etkinleştirme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], custom - in-place view activation
ms.assetid: 7d316945-06e0-4d8e-ba3a-0ef96fc75399
caps.latest.revision: "26"
manager: douge
ms.openlocfilehash: 16c091dc6d5602e4d19b8679794ef2794b29d7ed
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="in-place-activation"></a>Yerinde etkinleştirme
Düzenleyici görünümünüzü ActiveX veya diğer etkin denetimleri barındırıyorsa, bir ActiveX denetimi veya yerinde etkinleştirme modeli kullanarak bir etkin belgeyi veri nesnesi olarak Düzenleyicisi görünümünüzü uygulamalıdır.  
  
## <a name="support-for-menus-toolbars-and-commands"></a>Menüleri, araç çubukları ve komutları desteği  
 Visual Studio menüleri ve araç çubuklarını IDE kullanmak üzere, düzenleyici görünüm sağlar. Bu uzantılar denir *OLE yerinde bileşenleri*. Daha fazla bilgi için bkz: <xref:Microsoft.VisualStudio.Shell.Interop.IOleInPlaceComponent> ve <xref:Microsoft.VisualStudio.Shell.Interop.IOleInPlaceComponentUIManager>.  
  
 ActiveX denetimi uygularsanız, diğer katıştırılmış nesneler barındırabilir. Bir belge veri nesnesi uygularsanız, pencere çerçevesi ActiveX denetimlerini kullanma yeteneğini kısıtlar.  
  
> [!NOTE]
>  <xref:Microsoft.VisualStudio.OLE.Interop.IOleDocument> Ve <xref:Microsoft.VisualStudio.OLE.Interop.IOleDocumentView> arabirimi veri ve görünüm ayırmada izin verir. Ancak, Visual Studio bu işlevi desteklemiyor ve bu arabirimleri yalnızca belge görünüm nesnesi göstermek için kullanılır.  
  
 Kullanın düzenleyicileri <xref:Microsoft.VisualStudio.Shell.Interop.SOleComponentUIManager> hizmet sağlayabilir menüsü, araç ve komut tümleştirme yöntemlerini çağırarak <xref:Microsoft.VisualStudio.Shell.Interop.IOleInPlaceComponentUIManager> arabirimi uygulanan tarafından <xref:Microsoft.VisualStudio.Shell.Interop.SOleComponentUIManager> hizmet. Düzenleyiciler de izleme seçimi gibi diğer Visual Studio işlevleri sunar ve yönetim geri. Daha fazla bilgi için bkz: [özel düzenleyici oluşturma ve tasarımcıları](../extensibility/creating-custom-editors-and-designers.md).  
  
## <a name="objects-and-interfaces-used"></a>Nesneleri ve kullanılan arabirimleri  
 Yerinde etkinleştirme oluşturmak için kullanılan nesneleri aşağıdaki çizimde gösterilmektedir.  
  
 ![İçinde &#45; Yerleştir etkinleştirme Düzenleyicisi](../extensibility/media/vsinplaceactivationeditor.gif "vsInPlaceActivationEditor")  
Yerinde etkinleştirme Düzenleyicisi  
  
> [!NOTE]
>  Bu, yalnızca çizim nesnelerinin `CYourEditorFactory` nesne standart düzenleyici oluşturmak için gereklidir. Özel bir düzenleyici oluşturuyorsanız, uygulamanız gerekmez <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData2> düzenleyicinizi büyük olasılıkla özel Kalıcılık mekanizması olacağı için. Daha fazla bilgi için bkz: [özel düzenleyici oluşturma ve tasarımcıları](../extensibility/creating-custom-editors-and-designers.md).  
  
 Tek bir yerinde etkinleştirme Düzenleyicisi oluşturmak amacıyla uygulanan tüm arabirimler gösterilir `CYourEditorDocument` nesne destekler, ancak bu yapılandırma yalnızca belge verileri tek bir görünüm. Belge verilerinizin birden çok görünüm destekleme hakkında daha fazla bilgi için bkz: [destekleyen birden çok belge görünümleri](../extensibility/supporting-multiple-document-views.md).  
  
|Arabirim|Nesne türü|Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında|  
|---------------|--------------------|---------|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IOleInPlaceComponent>|Görüntüle|IDE tam olarak tümleşik bileşenleri olarak kullanarak çalışmaya yerinde VSPackage nesneler sağlayan <xref:Microsoft.VisualStudio.Shell.Interop.SOleComponentUIManager> hizmet. Bu hizmet, menüleri, araç çubukları ve komutları nesnesinin IDE içinde tümleşir ve durum değişikliği bildirimlerini verir.|  
|<xref:Microsoft.VisualStudio.OLE.Interop.IOleObject>|Görüntüle|Katıştırılmış nesne kapsayıcısı için temel işlevleri sağlar ve bununla iletişim kurar asıl anlamına gelir.|  
|<xref:Microsoft.VisualStudio.OLE.Interop.IOleInPlaceActiveObject>|Görüntüle|Etkinleştirme ve devre dışı bırakma yerinde nesnelerin yönetir ve yerinde nesne ne kadarının görünür olması belirler.|  
|<xref:Microsoft.VisualStudio.OLE.Interop.IOleInPlaceObject>|Görüntüle|Yerinde nesneyi, ilişkili uygulamanın en dıştaki çerçeve penceresi ve katıştırılmış nesne içeren uygulamayı belge penceresinde arasındaki iletişimin doğrudan bir kanal sağlar.|  
|<xref:Microsoft.VisualStudio.OLE.Interop.IOleDocument>|Görüntüle|Bir ActiveX nesnesi uygular. Unutmayın yöntemlerinin <xref:Microsoft.VisualStudio.OLE.Interop.IOleDocument> ve <xref:Microsoft.VisualStudio.OLE.Interop.IOleDocumentView> ayrı belge veri ve görünüm IDE içinde kullanılmaz.|  
|<xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>|Verilerini görüntüleme|Belge veri nesnesi veya belge görünüm nesnesi ya da komut işlemede katılmak için her ikisini de sağlar.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbarUser>|Görüntüle|Durum çubuğu güncelleştirmeleri sağlar.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsToolboxUser>|Görüntüle|Öğe araç kutusuna ekleme etkinleştirir.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsFileChangeEvents>|Veri|Düzenlenen dosya değişikliklerle ilgili bildirim gönderir. (Bu arabirim isteğe bağlıdır.)|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IPersistFileFormat>|Veri|Bir dosya türü için Farklı Kaydet özelliğini etkinleştirmek için kullanılır.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData>|Veri|Belge kalıcılığını etkinleştirir. Salt okunur dosyalar için arama <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData2.SetDocDataReadOnly%2A> salt okunur dosyaları belirten "kilitleme" simge sağlamak için.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsDocDataFileChangeControl>|Veri|Belge verilerde yapılan değişiklikleri yok sayılıp sayılmayacağını belirler.|