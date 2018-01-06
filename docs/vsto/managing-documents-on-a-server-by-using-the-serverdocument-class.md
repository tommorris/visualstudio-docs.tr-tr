---
title: "ServerDocument sınıfını kullanarak bir sunucu üzerinde belgeleri yönetme | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- documents [Office development in Visual Studio], managing on server
- Office documents [Office development in Visual Studio, managing on server
- ServerDocument class, managing documents on server
ms.assetid: 1ac90e89-d07d-4874-9d24-6741d6679a21
caps.latest.revision: "40"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 96d69ccb51be632440474bb0aa1b32e6ebe7a68a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="managing-documents-on-a-server-by-using-the-serverdocument-class"></a>ServerDocument Sınıfını Kullanarak Sunucuda Belge Yönetme
  ServerDocument sınıfını kullanabilirsiniz [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] Microsoft Office Word ve Microsoft Office Excel yüklenmemiş olsa bile belge düzeyi özelleştirmeleri, çeşitli yönlerini yönetmek için. Aşağıdaki görevleri gerçekleştirebilirsiniz:  
  
-   Erişim ve veriler bir belge veya çalışma kitabının veri önbelleğindeki değiştirin. Daha fazla bilgi için bkz: [çalışma ile önbelleğe alınmış veri belgesinde](#CachedData).  
  
-   Bir belge ile ilişkili özelleştirme derlemesini yönetin. Daha fazla bilgi için bkz: [belge özelleştirmesini yönetme](#CustomizationInfo).  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
## <a name="understanding-the-serverdocument-class"></a>ServerDocument Sınıfını Anlama  
 ServerDocument sınıfını Office yüklü olmayan bilgisayarlarda kullanılmak üzere tasarlanmıştır. Bu nedenle, genellikle bu sınıf, konsol projeleri veya Windows Forms projeleri yerine gibi Office projeleri Office ile tümleştirmek olmayan uygulamalarda kullanılır. Kullanım <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> Microsoft.VisualStudio.Tools.Applications.ServerDocument.dll derlemesindeki sınıfı.  
  
 ServerDocument sınıfını kullanarak oluşturulan belge düzeyi özelleştirmeleri üzerinde çalışılacak kullanılabilir [!INCLUDE[vs_dev12](../vsto/includes/vs-dev12-md.md)].  
  
 Hakkında daha fazla bilgi için Visual Studio 2010 Araçları Office çalışma zamanı ve Office uzantıları için .NET Framework için bkz: [Office çalışma zamanı genel bakış için Visual Studio Araçları](../vsto/visual-studio-tools-for-office-runtime-overview.md).  
  
> [!NOTE]  
>  Office sistemi için Visual Studio Araçları ServerDocument sınıfını kullanan eski bir uygulamanız varsa (sürüm 3.0 çalışma zamanı), Office sistemi için Visual Studio Araçları (sürüm 3.0 çalışma zamanı) uygulama çalıştıran bilgisayarlarda yüklü olmalıdır. Office çalışma zamanı için Visual Studio 2010 Araçları bu uygulamaları çalıştıramazsınız.  
  
##  <a name="CachedData"></a>Belgedeki önbelleğe alınmış verileri ile çalışma  
 ServerDocument sınıfını özelleştirilmiş belgelerde veri önbelleği ile çalışmak için kullanabileceğiniz üyeleri sağlar. Önbelleğe alınan veriler hakkında daha fazla bilgi için bkz: [veri önbelleğe alma](../vsto/caching-data.md) ve [sunucudaki belgelerde verilere erişme](../vsto/accessing-data-in-documents-on-the-server.md).  
  
 Aşağıdaki tabloda, önbelleğe alınan verilerle çalışmak için kullanabileceğiniz üyeleri listeler.  
  
|Görev|Kullanılacak üye|  
|----------|-------------------|  
|Bir belge bir veri önbelleği olup olmadığını belirlemek için.|<xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.IsCacheEnabled%2A> Yöntemi.|  
|Bir belgedeki önbelleğe alınan verilere erişmek için.<br /><br /> Daha fazla bilgi için bkz: [sunucudaki belgelerde verilere erişme](../vsto/accessing-data-in-documents-on-the-server.md).|<xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.CachedData%2A> Özelliği.|  
  
##  <a name="CustomizationInfo"></a>Belge özelleştirmesini yönetme  
 ServerDocument sınıfı üyeleri, bir belge ile ilişkili özelleştirme derlemesini yönetmek için kullanabilirsiniz. Örneğin, böylece belgeyi artık bir özelleştirme parçası olan bir belgeden özelleştirme program aracılığıyla kaldırabilirsiniz.  
  
 Aşağıdaki tabloda özelleştirme derlemesini yönetmek için kullanabileceğiniz üyeleri listeler.  
  
|Görev|Kullanılacak üye|  
|----------|-------------------|  
|Bir belge olup olmadığını belirlemek için belge düzeyi özelleştirme parçasıdır.|<xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.GetCustomizationVersion%2A> Yöntemi.|  
|Program aracılığıyla özelleştirme belgeye çalışma zamanında iliştirmek için.<br /><br /> Daha fazla bilgi için bkz: [nasıl yapılır: ekleme yönetilen kod uzantıları belgeleri](../vsto/how-to-attach-managed-code-extensions-to-documents.md)|Aşağıdakilerden birini <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.AddCustomization%2A> yöntemleri.|  
|Program aracılığıyla bir özelleştirme çalışma zamanında bir belgeden kaldırmak için.<br /><br /> Daha fazla bilgi için bkz: [nasıl yapılır: kaldırmak yönetilen kod uzantıları belgelerden](../vsto/how-to-remove-managed-code-extensions-from-documents.md).|<xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.RemoveCustomization%2A> Yöntemi.|  
|Belge ile ilişkili dağıtım bildirimi URL'si alınamadı.|<xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.DeploymentManifestUrl%2A> Özelliği.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: belgelere yönetilen kod uzantıları ekleme](../vsto/how-to-attach-managed-code-extensions-to-documents.md)   
 [Nasıl yapılır: belgelerden yönetilen kod uzantılarını kaldırma](../vsto/how-to-remove-managed-code-extensions-from-documents.md)   
 [Office çalışma zamanı genel bakış için Visual Studio Araçları](../vsto/visual-studio-tools-for-office-runtime-overview.md)   
 [Verileri Önbelleğe Alma](../vsto/caching-data.md)  
  