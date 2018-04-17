---
title: 'Nasıl yapılır: Sunucu Gezgininde yerleşik bir SharePoint düğümü için veri alma | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint Connections [SharePoint development in Visual Studio], extending a node
- SharePoint development in Visual Studio, extending SharePoint Connections node in Server Explorer
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: f448ec8d7cfe22495aa3f7b2ce9191f106205c33
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-get-data-for-a-built-in-sharepoint-node-in-server-explorer"></a>Nasıl Yapılır: Sunucu Gezgininde Yerleşik bir SharePoint Düğümü için Veri Alma
  Her yerleşik SharePoint düğümü için **Sunucu Gezgini**, veri düğümünü temsil eden bir temel alınan SharePoint bileşenini Al. Daha fazla bilgi için bkz: [Sunucu Gezgininde SharePoint bağlantıları düğümünü genişletme](../sharepoint/extending-the-sharepoint-connections-node-in-server-explorer.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde bir liste düğümü temsil eder temel alınan SharePoint listesi için veri alma gösterilmektedir **Sunucu Gezgini**. Varsayılan olarak, liste düğümünüz bir **tarayıcıda görüntüle** listeler bir Web tarayıcısında açmak için tıklatabilirsiniz bağlam menüsü öğesini. Bu örnekte liste düğümlerine ekleyerek genişletir bir **Visual Studio görünümünde** listeler doğrudan Visual Studio'da açılır bağlam menüsü öğesini. Kod Visual Studio'da açmak için listeden URL'sini almak düğüm listesi verileri erişir.  
  
 [!code-vb[SPExtensibility.ProjectSystemExtension.General#10](../sharepoint/codesnippet/VisualBasic/projectsystemexamples/extension/serverexplorerextensionnodeinfo.vb#10)]
 [!code-csharp[SPExtensibility.ProjectSystemExtension.General#10](../sharepoint/codesnippet/CSharp/projectsystemexamples/extension/serverexplorerextensionnodeinfo.cs#10)]  
  
 Bu örnek, elde etmek için SharePoint Proje hizmeti kullanır. <xref:EnvDTE.DTE> açmak için kullanılan nesne Visual Studio'da listeler. SharePoint Proje hizmeti hakkında daha fazla bilgi için bkz: [SharePoint Proje hizmetini kullanma](../sharepoint/using-the-sharepoint-project-service.md).  
  
 Bir SharePoint düğümü için bir uzantı oluşturmak için temel görevler hakkında daha fazla bilgi için bkz: [nasıl yapılır: Sunucu Gezgininde SharePoint düğümünü genişletme](../sharepoint/how-to-extend-a-sharepoint-node-in-server-explorer.md).  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Bu örnekte aşağıdaki derlemelere başvuruları gerektirir:  
  
-   EnvDTE  
  
-   Microsoft.VisualStudio.SharePoint  
  
-   Microsoft.VisualStudio.SharePoint.Explorer.Extensions  
  
-   System.ComponentModel.Composition  
  
## <a name="deploying-the-extension"></a>Uzantısını dağıtma  
 Dağıtmak için **Sunucu Gezgini** uzantısı oluşturma bir [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] uzantısı (VSIX) paketini derleme ve uzantısıyla dağıtmak istediğiniz diğer dosyalar için. Daha fazla bilgi için bkz: [dağıtma uzantıları Visual Studio'da SharePoint araçları için](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sunucu Gezgininde SharePoint bağlantıları düğümünü genişletme](../sharepoint/extending-the-sharepoint-connections-node-in-server-explorer.md)   
 [Nasıl yapılır: Sunucu Gezgininde SharePoint düğümünü genişletme](../sharepoint/how-to-extend-a-sharepoint-node-in-server-explorer.md)   
 [SharePoint Proje hizmetini kullanma](../sharepoint/using-the-sharepoint-project-service.md)   
 [Visual Studio'da SharePoint Araçları için Hata Ayıklama Uzantıları](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md)  
  
  