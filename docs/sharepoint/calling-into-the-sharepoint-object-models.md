---
title: "SharePoint nesne modellerini çağırma | Microsoft Docs"
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
- SharePoint development in Visual Studio, client object model
- SharePoint development in Visual Studio, server object model
- SharePoint commands [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, extensibility features
ms.assetid: 99934f9e-901e-464e-ac8c-22c6c86440f4
caps.latest.revision: "38"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: b1a0f4175dc884283dcf92b7f6268a518cdaf0ca
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="calling-into-the-sharepoint-object-models"></a>SharePoint Nesne Modellerini Çağırma
  Visual Studio'da SharePoint araçları için Uzantılar oluşturduğunuzda, bazı görevleri gerçekleştirmek üzere SharePoint API'leri çağırmak gerekebilir. Örneğin, SharePoint projeleri için bir özel dağıtım adımı oluşturursanız, SharePoint çözümlerini dağıtmak için görevlerden bazılarını gerçekleştirmek için API çağrısı olabilir.  
  
 [!INCLUDE[wss_14_long](../sharepoint/includes/wss-14-long-md.md)]ve [!INCLUDE[moss_14_long](../sharepoint/includes/moss-14-long-md.md)] SharePoint araç uzantıları kullanabileceğiniz iki farklı nesne modelleri sağlar: bir sunucu nesne modeli ve bir istemci nesne modeli. Her nesne modeli SharePoint araç uzantıları bağlamında avantajları ve sakıncaları vardır.  
  
 SharePoint nesne modellerini genel bakış için bkz: [programlama modeli, SharePoint araç uzantıları genel bakış](../sharepoint/overview-of-the-programming-model-of-sharepoint-tools-extensions.md).  
  
## <a name="using-the-client-object-model-in-extension-projects"></a>Uzantı projelerinde istemci nesne modelini kullanma  
 SharePoint araçları için uzantı geliştirirken, herhangi bir yönetilen API'ler kümesi gibi projenizdeki istemci nesne modelini kullanabilirsiniz. Projeniz için istemci nesne modelini derlemelerine başvurular ekleyebilirsiniz ve doğrudan kodunuzdan istemci nesne modelini API'leri çağırabilirsiniz.  
  
 Ancak, istemci nesne modelini SharePoint araç uzantıları bağlamında iki sakıncaları vardır:  
  
-   İstemci nesne modelini yalnızca bir alt sunucu nesne modeli sağlar. İstemci nesne modelinde gösterilmeyen SharePoint işlevselliği kullanmak varsa, sunucu nesne modeli kullanmanız gerekir.  
  
-   SharePoint araç uzantıları istemci nesne modelini kullanarak, çoğu durumda çalışması gerekir, ancak burada istemci nesne modelini çağrıları beklendiği gibi çalışmıyor bazı senaryolar karşılaşabilirsiniz. İstemci nesne modelini istemci uygulamalarında SharePoint sitelerine bir uzak sunucuda veya grubunda çağırmak için kullanılmak üzere tasarlanmıştır. Visual Studio'da SharePoint araçları yalnızca yerel bir SharePoint yükleme geliştirme bilgisayarındaki çalışırlar. Bu nedenle, bir SharePoint araçları uzantısı'nda istemci nesne modelini kullandığınızda, bir SharePoint sitesine nasıl istemci nesne modelini kullanılmak üzere tasarlanmamıştır olduğu yerel bilgisayarda çağırın.  
  
 Visual Studio'da SharePoint araçları uzantısı istemci nesne modelini kullanmak nasıl izlenecek yol için bkz: [izlenecek yol: bir sunucu Gezgini uzantısında SharePoint istemcisi nesne modelini çağırma](../sharepoint/walkthrough-calling-into-the-sharepoint-client-object-model-in-a-server-explorer-extension.md).  
  
## <a name="using-the-server-object-model-in-extension-projects"></a>Sunucu nesne modeli uzantısı projelerinde kullanma  
 Sunucu nesne modeli istemci nesne modelini bir üst kümesidir. Sunucu nesne modeli kullandığınızda, tüm özellikleri kullanabilirsiniz, [!INCLUDE[wss_14_long](../sharepoint/includes/wss-14-long-md.md)] ve [!INCLUDE[moss_14_long](../sharepoint/includes/moss-14-long-md.md)] programlı olarak kullanıma sunar.  
  
 SharePoint araç uzantıları sunucusu nesne modelinde API'leri kullanabilirsiniz, ancak API'lerini doğrudan çağrılamaz. Sunucu nesne modeli, .NET Framework 3.5 hedefleyen yalnızca 64-bit işleminden çağrılabilir. Ancak, SharePoint araç uzantıları gerektiren [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] ve 32-bit Visual Studio işlemini çalıştırın. Bu, SharePoint araç uzantıları SharePoint sunucusu nesne modeline derlemelerde doğrudan başvuran önler.  
  
 Sunucu nesne modeli bir SharePoint araçları uzantısı'nda kullanmak istiyorsanız, özel bir oluşturmalısınız *SharePoint komutu* API'yi çağırmak için. SharePoint komutu sunucusu nesne modeline doğrudan çağırabilir miyim ikincil bir derlemede tanımlayın. Uzantı projeniz, SharePoint dolaylı olarak ExecuteCommand yöntemini kullanarak çağrı komutu bir <xref:Microsoft.VisualStudio.SharePoint.ISharePointConnection> nesnesi.  
  
 Oluşturma ve SharePoint komutları kullanma hakkında daha fazla bilgi için bkz: [nasıl yapılır: bir SharePoint komutu oluşturma](../sharepoint/how-to-create-a-sharepoint-command.md) ve [nasıl yapılır: SharePoint komutu yürütme](../sharepoint/how-to-execute-a-sharepoint-command.md). SharePoint komutları dağıtma hakkında daha fazla bilgi için bkz: [dağıtma uzantıları Visual Studio'da SharePoint araçları için](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md).  
  
 Oluşturma ve SharePoint komutlarını kullanmak gösteren talimatlara için bkz [izlenecek yol: SharePoint projeleri için bir özel dağıtım adımı oluşturma](../sharepoint/walkthrough-creating-a-custom-deployment-step-for-sharepoint-projects.md) ve [izlenecek yol: Görüntü Web Sunucu Gezgini genişletme Bölümleri](../sharepoint/walkthrough-extending-server-explorer-to-display-web-parts.md).  
  
### <a name="understanding-how-sharepoint-commands-are-executed"></a>Anlama nasıl SharePoint komutları çalıştırılır  
 SharePoint komutları tanımlayan derlemeleri vssphost4.exe adlı bir 64-bit ana işlemde yüklenir. Bir SharePoint araçları uzantısı'nda bir SharePoint komutu çağırdıktan sonra komut vssphost4.exe 32-bit Visual Studio işlemini (devenv.exe) yerine tarafından yürütülür. SharePoint komutları kayıt defterinde değerlerini ayarlayarak nasıl yürütülen bazı yönlerini kontrol edebilirsiniz. Daha fazla bilgi için bkz: [Visual Studio'da SharePoint araçları için hata ayıklama uzantıları](../sharepoint/debugging-extensions-for-the-sharepoint-tools-in-visual-studio.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: bir SharePoint komutu oluşturma](../sharepoint/how-to-create-a-sharepoint-command.md)   
 [Nasıl yapılır: SharePoint komutu yürütme](../sharepoint/how-to-execute-a-sharepoint-command.md)   
 [SharePoint Araç Uzantılarının Programlama Modeline Genel Bakış](../sharepoint/overview-of-the-programming-model-of-sharepoint-tools-extensions.md)  
  
  