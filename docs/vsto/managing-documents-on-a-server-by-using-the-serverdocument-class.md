---
title: ServerDocument sınıfını kullanarak sunucu üzerinde belgeleri yönetme
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- documents [Office development in Visual Studio], managing on server
- Office documents [Office development in Visual Studio, managing on server
- ServerDocument class, managing documents on server
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 97eed0e4cec143e51195347bfb90d430d8e1eadb
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34573004"
---
# <a name="manage-documents-on-a-server-by-using-the-serverdocument-class"></a>ServerDocument sınıfını kullanarak sunucu üzerinde belgeleri yönetme
  Kullanabileceğiniz `ServerDocument` sınıfını [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] Microsoft Office Word ve Microsoft Office Excel yüklenmemiş olsa bile belge düzeyi özelleştirmeleri, çeşitli yönlerini yönetmek için. Aşağıdaki görevleri gerçekleştirebilirsiniz:  
  
-   Erişim ve veriler bir belge veya çalışma kitabının veri önbelleğindeki değiştirin. Daha fazla bilgi için bkz: [belgesindeki önbelleğe alınan veriler ile çalışırsınız](#CachedData).  
  
-   Bir belge ile ilişkili özelleştirme derlemesini yönetin. Daha fazla bilgi için bkz: [belge özelleştirme yönetmek](#CustomizationInfo).  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
## <a name="understand-the-serverdocument-class"></a>ServerDocument Sınıfını Anlama  
 `ServerDocument` Sınıfı Office yüklü olmayan bilgisayarlarda kullanılmak üzere tasarlanmıştır. Bu nedenle, genellikle bu sınıf, konsol projeleri veya Windows Forms projeleri yerine gibi Office projeleri Office ile tümleştirmek olmayan uygulamalarda kullanılır. Kullanım <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> sınıfını *Microsoft.VisualStudio.Tools.Applications.ServerDocument.dll* derleme.  
  
 `ServerDocument` Sınıfı kullanılarak oluşturulan belge düzeyi özelleştirmeleri üzerinde çalışılacak kullanılabilir [!INCLUDE[vs_dev12](../vsto/includes/vs-dev12-md.md)].  
  
 Hakkında daha fazla bilgi için Visual Studio 2010 Araçları Office çalışma zamanı ve Office uzantıları için .NET Framework için bkz: [Office çalışma zamanı genel bakış için Visual Studio Araçları](../vsto/visual-studio-tools-for-office-runtime-overview.md).  
  
> [!NOTE]  
>  Kullanan eski bir uygulamanız varsa, `ServerDocument` sınıfını `Visual Studio Tools for Office` system (sürüm 3.0 çalışma zamanı), `Visual Studio Tools for Office` sistem (sürüm 3.0 çalışma zamanı) uygulama çalıştıran bilgisayarlarda yüklü olmalıdır. `Visual Studio 2010 Tools for Office runtime` Bu uygulamaları çalıştıramazsınız.  
  
##  <a name="CachedData"></a> Belgedeki önbelleğe alınan verilerle çalışma  
 `ServerDocument` Sınıfı üyeleri özelleştirilmiş belgelerde veri önbelleği ile çalışmak için kullanabileceğiniz sağlar. Önbelleğe alınan veriler hakkında daha fazla bilgi için bkz: [veriyi önbelleğe](../vsto/caching-data.md) ve [sunucudaki belgelerde verilere erişim](../vsto/accessing-data-in-documents-on-the-server.md).  
  
 Aşağıdaki tabloda, önbelleğe alınan verilerle çalışmak için kullanabileceğiniz üyeleri listeler.  
  
|Görev|Kullanılacak üye|  
|----------|-------------------|  
|Bir belge bir veri önbelleği olup olmadığını belirlemek için.|<xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.IsCacheEnabled%2A> Yöntemi.|  
|Bir belgedeki önbelleğe alınan verilere erişmek için.<br /><br /> Daha fazla bilgi için bkz: [sunucudaki belgelerde verilere erişim](../vsto/accessing-data-in-documents-on-the-server.md).|<xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.CachedData%2A> Özelliği.|  
  
##  <a name="CustomizationInfo"></a> Belge özelleştirmesini yönetme  
 Üyeleri kullanabilir `ServerDocument` bir belge ile ilişkili özelleştirme derlemesini yönetmek için sınıf. Örneğin, böylece belgeyi artık bir özelleştirme parçası olan bir belgeden özelleştirme program aracılığıyla kaldırabilirsiniz.  
  
 Aşağıdaki tabloda özelleştirme derlemesini yönetmek için kullanabileceğiniz üyeleri listeler.  
  
|Görev|Kullanılacak üye|  
|----------|-------------------|  
|Bir belge olup olmadığını belirlemek için belge düzeyi özelleştirme parçasıdır.|<xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.GetCustomizationVersion%2A> Yöntemi.|  
|Program aracılığıyla çalışma zamanında belgeye özelleştirme iliştirmek için.<br /><br /> Daha fazla bilgi için bkz: [nasıl yapılır: ekleme yönetilen kod uzantıları belgelere](../vsto/how-to-attach-managed-code-extensions-to-documents.md)|Aşağıdakilerden birini <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.AddCustomization%2A> yöntemleri.|  
|Program aracılığıyla bir özelleştirme çalışma zamanında bir belgeden kaldırmak için.<br /><br /> Daha fazla bilgi için bkz: [nasıl yapılır: belgelerden kaldırma yönetilen kod uzantıları](../vsto/how-to-remove-managed-code-extensions-from-documents.md).|<xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.RemoveCustomization%2A> Yöntemi.|  
|Belge ile ilişkili dağıtım bildirimi URL'si alınamadı.|<xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.DeploymentManifestUrl%2A> Özelliği.|  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Nasıl yapılır: ekleme yönetilen kod uzantıları belgelere](../vsto/how-to-attach-managed-code-extensions-to-documents.md)   
 [Nasıl yapılır: belgelerden kaldırma yönetilen kod uzantıları](../vsto/how-to-remove-managed-code-extensions-from-documents.md)   
 [Office çalışma zamanı genel bakış için Visual Studio Araçları](../vsto/visual-studio-tools-for-office-runtime-overview.md)   
 [Verileri önbelleğe](../vsto/caching-data.md)  
  