---
title: "Projeler ve editörler için ek kaynak denetimi yönergeleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- source control [Visual Studio SDK], guidelines for projects and editors
ms.assetid: 2483cce5-321c-4d3c-9c5c-ee8385263f74
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 308de182e604f06fff9ad25cb65428b2d48ff257
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="additional-source-control-guidelines-for-projects-and-editors"></a>Projeler ve editörler için ek kaynak denetimi yönergeleri
Projeleri ve editörler için kaynak denetimi desteklemek için uyması yönergeler mevcuttur.  
  
## <a name="guidelines"></a>Kuralları  
 Proje veya düzenleyicisi ayrıca kaynak denetimi desteklemek için aşağıdakileri yapmanız gerekir:  
  
|Alan|Proje|Düzenleyici|Ayrıntılar|  
|----------|-------------|------------|-------------|  
|Dosyaların özel kopyaları|X||Ortam dosyaları özel kopyalarını destekler. Diğer bir deyişle, projede kayıtlı her kişi güncelleştirmesini kendi özel proje dosyalarında kopyasına sahip.|  
|ANSI/Unicode kalıcılığı|X|X|Kalıcılık kodu yazarsanız, kaynak denetimi programlarının çoğu Unicode şu anda desteklemediği için ANSI form dosyalarında kalıcı olmasını sağlar.|  
|Dosyaları listeleme|X||Proje belirli içindeki tüm dosyaların listesini içermeli ve kullanarak dosyaları listesi numaralandırmayacağı <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProject2> veya <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.GetProperty%2A> (VSH_PROPID_First_Child/Next_Sibling). Proje öğesi adları yoluyla maruz bırakmamalısınız kendi <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject.GetMkDocument%2A> (özel dosyaları dahil) uygulama ve Destek ad araması aracılığıyla kendi <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject.IsDocumentInProject%2A> uygulaması.|  
|Metin biçimi|X|X|Mümkün olduğunda, dosyaları birleştirme farklı sürümleri desteklemek için metin biçiminde olmalıdır. Metin biçiminde olmayan dosyaları dosyanın diğer sürümünü daha sonra birleştirilemez. Tercih edilen metin biçimi XML şeklindedir.|  
|Tabanlı başvurusu|X||Başvuru tabanlı projelerde kaynak denetiminde taşımalarına desteklenir. Ancak, proje dosyaları diskte mi mevcut bağımsız olarak isteğe bağlı olarak, kendi dosyaların bir listesini oluşturmak üzere sürece directory tabanlı projeler Ayrıca kaynak denetimi tarafından desteklenir. Bir proje kaynak denetiminden açarken proje dosyası dosyalarından birini önce ilk kapalı duruma getirilir.|  
|Nesneleri ve özellikleri tahmin edilebilir sırayla Sürdür|X|X|Dosyalarınızı birleştirme kolaylaştırmak için alfabetik sırayla gibi tahmin edilebilir bir sırada kalıcı olmasını sağlar.|  
|Yeniden yükleme|X|X|Bir dosya değiştirildiğinde diskteki düzenleyicinizi yeniden kurabilmesi gerekir. Kaynak denetiminde katıldığınızda ortamı verileri sizin için çağırarak yeniden yükleyecektir, <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData2.ReloadDocData%2A> uygulaması. IVsQueryEditQuerySave çağrıldığında bir checkout oluştuğunda en zor yeniden durumda::<xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QueryEditFiles%2A> ve bilgileri işleniyor. Ancak, yeniden yükleme kodunuzu çalıştırabilir ve bu durumda olması gerekir.<br /><br /> Ortam proje dosyalarını otomatik olarak yeniden yükler. Ancak, bir proje uygulamalıdır <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistHierarchyItem2> iç içe değilse hiyerarşileri yeniden desteklemek için proje dosyalarını iç içe geçmiş.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak Denetimini Destekleme](../../extensibility/internals/supporting-source-control.md)