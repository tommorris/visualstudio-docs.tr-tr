---
title: Eski dil hizmetinin model | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- language services, model
ms.assetid: d8ae1c0c-ee3d-4937-a581-ee78d0499793
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 943f0f013045e3082af3069ed4d45aaed1096869
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31131598"
---
# <a name="model-of-a-legacy-language-service"></a>Eski dil hizmet modeli
Bir dil hizmeti belirli bir dil için özellikler ve öğeler tanımlar ve düzenleyici bu dile özgü bilgileri sağlamak için kullanılır. Örneğin, düzenleyici sözdizimi renklendirmesi desteklemek için öğeleri ve dil anahtar sözcükleri bilmesi gerekir.  
  
 Dil hizmeti yakından Düzenleyicisi ve düzenleyici içeren görünümü tarafından yönetilen metin arabelleği ile çalışır. Microsoft IntelliSense **hızlı bilgi** seçeneği dil hizmeti tarafından sağlanan bir özelliği bir örnektir.  
  
## <a name="a-minimal-language-service"></a>En az bir dil hizmeti  
 En temel dil hizmeti aşağıdaki iki nesne içerir:  
  
-   *Dil hizmeti* uygulayan <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo> arabirimi. Bir dil hizmeti adı, dosya adı uzantıları, kod Pencere Yöneticisi ve Renklendirici içeren dili hakkında bilgi yer almaktadır.  
  
-   *Renklendirici* uygulayan <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer> arabirimi.  
  
 Aşağıdaki kavramsal çizim temel dil hizmet modeli gösterir.  
  
 ![Dil Hizmet Modeli grafiği](../../extensibility/media/vslanguageservicemodel.gif "vsLanguageServiceModel")  
Temel dil hizmet modeli  
  
 Belge penceresi konakları *belge görünümü* bu durumda düzenleyicisinin [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] çekirdek Düzenleyici. Belge görünümü ve metin arabelleği Düzenleyicisi tarafından sahibi olur. Bu nesneler çalışmak [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] özel belge pencere olarak adlandırılan bir *kod penceresi*. Kod penceresi bulunan bir <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame> oluşturulan ve IDE tarafından denetlenen nesne.  
  
 Belirtilen uzantılı bir dosya yüklendiğinde Düzenleyicisi bu uzantısıyla ilişkili dil hizmeti bulur ve için kod penceresi çağırarak geçirir <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo.GetCodeWindowManager%2A> yöntemi. Dil hizmeti döndürür bir *kod Pencere Yöneticisi*, hangi uygulayan <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindowManager> arabirimi.  
  
 Aşağıdaki tabloda, modeldeki nesneleri genel bir bakış sağlar.  
  
|Bileşen|Nesne|İşlev|  
|---------------|------------|--------------|  
|Metin arabelleği|<xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer>|Unicode okuma/yazma metin akış. Diğer Kodlamalar kullanmak metin için mümkündür.|  
|Kod penceresi|<xref:Microsoft.VisualStudio.TextManager.Interop.VsCodeWindow>|Bir veya daha fazla metin görünümleri içeren bir belge penceresi. Zaman [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] olan birden çok belge arabirimi (MDI) modunda bir MDI alt kod penceredir.|  
|Metin görünümü|<xref:Microsoft.VisualStudio.TextManager.Interop.VsTextView>|Kullanıcının gidin ve klavye ve fare kullanarak metin görüntüleme sağlayan bir pencere. Metin görünümü kullanıcıya bir düzenleyicisi olarak görünür. Metin görünümlerde sıradan Düzenleyici pencerelerini, çıktı penceresi ve komut penceresi kullanabilirsiniz. Ayrıca, bir veya daha fazla metin görünümler kod penceresi içinde yapılandırabilirsiniz.|  
|Metin Yöneticisi|Tarafından yönetilen <xref:Microsoft.VisualStudio.TextManager.Interop.SVsTextManager> hizmet, hangi elde gelen bir <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextManager> işaretçi|Daha önce açıklanan tüm bileşenleri tarafından paylaşılan ortak bilgileri tutan bir bileşeni.|  
|Dil hizmeti|Uygulamaya bağlıdır; uygular <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo>|Düzenleyici sözdizimi vurgulama, deyim tamamlama ve eşleşen ayraç gibi dile özgü bilgiler sağlayan bir nesne.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özel Düzenleyicilerde Belge Verileri ve Belge Görünümü](../../extensibility/document-data-and-document-view-in-custom-editors.md)