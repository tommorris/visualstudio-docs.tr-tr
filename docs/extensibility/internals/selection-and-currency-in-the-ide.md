---
title: Seçimi ve IDE içinde para birimini | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- currency, Visual Studio IDE
- IDE, selection
- selection, Visual Studio IDE
- IDE, currency
ms.assetid: 2f6f18d1-acd8-454d-a856-9a4d81155052
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: bf8c58cb08f82b10970424600843b0fedcf477fc
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="selection-and-currency-in-the-ide"></a>Seçim ve IDE içinde para birimi
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Tümleşik geliştirme ortamı (IDE) tutar kullanıcıların hakkında bilgi seçili nesneler seçimi kullanarak *bağlamı*. Seçim bağlamla VSPackages iki yolla izleme para yer alabilir:  
  
-   Para birimi bilgilerini IDE'ye VSPackages yayarak.  
  
-   Kullanıcıların şu anda etkin seçimleri IDE içinden izleyerek.  
  
## <a name="selection-context"></a>Seçim bağlamı  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE genel izler IDE para kendi genel Seçim bağlam nesnesi. Aşağıdaki tabloda seçimi bağlamı oluşturan öğeler gösterilir.  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|Geçerli hiyerarşi|Geçerli projenin genellikle; NULL geçerli hiyerarşi bir bütün olarak çözüm geçerli olduğunu gösterir.|  
|Geçerli öğe kimliği|Seçili öğenin geçerli hiyerarşi içinde; bir proje penceresinde birden çok seçimin olduğunda, birden çok geçerli öğe olabilir.|  
|Geçerli `SelectionContainer`|Özellikler penceresini Özellikler'e görüntülemesi gereken bir veya daha fazla nesneleri tutar.|  
  
 Ayrıca, ortamın genel listelerini tutar:  
  
-   Etkin kullanıcı Arabirimi komut tanımlayıcıları listesi  
  
-   Şu anda etkin öğe türleri listesi.  
  
### <a name="window-types-and-selection"></a>Pencere türleri ve seçimi  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE iki genel türlerine windows düzenler:  
  
-   Hiyerarşi türü windows  
  
-   Araç ve belge pencereleri gibi çerçeve pencereleri  
  
 Para birimi, IDE Bu pencere türlerinin her biri için farklı bir şekilde izler.  
  
 En yaygın proje türü IDE denetimleri Çözüm Gezgini penceredir. Bir proje türü penceresi genel seçimi bağlamının ItemId ve genel hiyerarşi izler ve geçerli hiyerarşi belirlemek için kullanıcının seçimini penceresi dayanır. Proje türü windows, küresel hizmet ortamı sağlar <xref:Microsoft.VisualStudio.Shell.Interop.SVsShellMonitorSelection>, ile hangi VSPackages açık öğeler için geçerli değerler izleyebilirsiniz. Ortamında gözatma özelliği bu genel hizmet tarafından yönetilir.  
  
 Çerçeve pencereleri çerçeve penceresi içinde DocObject SelectionContext değeri (ItemId/hiyerarşi/SelectionContainer sorularının cevabını) göndermek için diğer yandan kullanın. biçimindeki telefon numarasıdır. Çerçeve pencereleri hizmeti kullanan <xref:Microsoft.VisualStudio.Shell.Interop.SVsShellMonitorSelection> bu amaç için. DocObject hiyerarşi için yerel değerler bırakarak yalnızca seçim kapsayıcısı için değerler gönderebilir ve MDI alt belgeler için tipik olan ItemId değişmedi.  
  
### <a name="events-and-currency"></a>Olaylar ve para birimi  
 İki tür olay para birimi ortam kavramı etkileyen oluşabilir:  
  
-   Genel düzeyde yayılır ve pencere çerçevesi seçimi bağlamını değiştirmek olaylar. Bu tür bir olay örnekleri açıldı, açılmakta olan bir genel araç penceresi ya da açılmakta olan bir proje türü araç penceresi bir MDI alt pencere içerir.  
  
-   Pencere çerçevesi seçimi bağlamı içinde izlenen öğelerini değiştirme olayları. Seçim DocObject içinde değiştirme veya bir proje türü penceresinde seçimi değiştirmek örnek olarak verilebilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Seçim bağlam nesneleri](../../extensibility/internals/selection-context-objects.md)   
 [Kullanıcıya Geri Bildirim](../../extensibility/internals/feedback-to-the-user.md)