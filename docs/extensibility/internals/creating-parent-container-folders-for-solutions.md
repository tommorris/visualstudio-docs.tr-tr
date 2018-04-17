---
title: Üst kapsayıcı klasörleri çözümleri oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- solutions, creating parent containers
- source control plug-ins, creating parent containers
ms.assetid: 961e68ed-2603-4479-a306-330eda2b2efa
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 2104c0c109db0d410cbd08683ce227c62982fd65
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="creating-parent-container-folders-for-solutions"></a>Üst kapsayıcı klasörleri çözümleri oluşturma
Kaynak Denetim eklentisi API sürüm 1.2, bir kullanıcı çözüm içindeki tüm Web projeleri için tek bir kök kaynak denetimi hedef belirtebilirsiniz. Bu tek bir kök bir süper birleşik kök (SUR) adı verilir.  
  
 Kullanıcının kaynak denetimi için çok projeli bir çözümün eklediyseniz kaynak denetim eklentisi API sürüm 1.1, her Web projesi için bir kaynak denetimi hedefini belirlemek için kullanıcı istendi.  
  
## <a name="new-capability-flags"></a>Yeni yetenek bayrakları  
 `SCC_CAP_CREATESUBPROJECT`  
  
 `SCC_CAP_GETPARENTPROJECT`  
  
## <a name="new-functions"></a>Yeni işlevleri  
 [SccCreateSubProject](../../extensibility/scccreatesubproject-function.md)  
  
 [SccGetParentProjectPath](../../extensibility/sccgetparentprojectpath-function.md)  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE bir çözüm için kaynak denetimi eklerken SUR klasörü neredeyse her zaman oluşturur. Özellikle, bunu aşağıdaki durumlarda yapar:  
  
-   Bir dosya paylaşımı Web projesi projesidir.  
  
-   Proje ve çözüm dosyası için farklı sürücüler vardır.  
  
-   Proje ve çözüm dosyası için farklı paylaşımları vardır.  
  
-   Projeleri ayrı olarak (bir kaynak tarafından denetlenen çözümde) eklendi.  
  
 İçinde [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] SUR klasörün adını çözüm adı uzantısı olmadan aynı olması önerilir. Aşağıdaki tabloda iki sürüm davranışı özetlenmektedir.  
  
|Özellik|tSource denetim eklentisi API sürüm 1.1|Kaynak Denetim eklentisi API sürüm 1.2|  
|-------------|----------------------------------------------|---------------------------------------------|  
|Çözüm için SCC ekleme|SccInitialize()<br /><br /> SccGetProjPath()<br /><br /> SccGetProjPath()<br /><br /> SccOpenProject()|SccInitialize()<br /><br /> SccGetProjPath()<br /><br /> SccCreateSubProject()<br /><br /> SccCreateSubProject()<br /><br /> SccOpenProject()|  
|Kaynak denetimli çözüme proje ekleme|SccGetProjPath()<br /><br /> OpenProject()|SccGetParentProjectPath()<br /><br /> SccOpenProject() **Not:** Visual Studio varsayar bir çözüm Sur doğrudan alt olduğunu|  
  
## <a name="examples"></a>Örnekler  
 Aşağıdaki tabloda iki örnek listeler. Her iki durumda da [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] kullanıcı kadar kaynak denetimindeki çözüm için bir hedef konum sorulup *user_choice* hedefi olarak belirtilir. User_choice belirtildiğinde, çözüm ve iki proje kaynak denetimi hedefler için kullanıcıya sormadan eklenir.  
  
|Çözüm içerir|Disk konumları|Veritabanı varsayılan yapısı|  
|-----------------------|-----------------------|--------------------------------|  
|sln1.sln<br /><br /> Web1'i<br /><br /> Web2|C:\Solutions\sln1<br /><br /> C:\Inetpub\wwwroot\Web1<br /><br /> \\\server\wwwroot$\web2|$/*user_choice*/sln1<br /><br /> $/*user_choice*  /C/Web1<br /><br /> $/*user_choice*/Web2|  
|sln1.sln<br /><br /> Web1'i<br /><br /> Win1|C:\Solutions\sln1<br /><br /> D:\Inetpub\wwwroot\Web1<br /><br /> C:\solutions\sln1\Win1|$/*user_choice*/sln1<br /><br /> $/*user_choice*  /D/web1<br /><br /> $/*user_choice*  /sln1/win1|  
  
 Alt klasörleri ve SUR klasörü işlemi iptal edildi veya bir hata nedeniyle başarısız bağımsız olarak oluşturulur. Bunlar iptal veya hata koşulları otomatik olarak kaldırılmaz.  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Kaynak Denetim eklentisi oluşmazsa sürüm 1.1 davranışı varsayılan olarak `SCC_CAP_CREATESUBPROJECT` ve `SCC_CAP_GETPARENTPROJECT` yetenek bayrakları. Ayrıca, kullanıcılarının [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] DWORD: 00000001 için aşağıdaki anahtarı değerini ayarlayarak sürüm 1.1 davranışa geri dönmek seçebilirsiniz:  
  
 [HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\8.0\SourceControl] "DoNotCreateSolutionRootFolderInSourceControl" = dword: 00000001  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak Denetimi Eklentisi API Sürümü 1.2’deki Yenilikler](../../extensibility/internals/what-s-new-in-the-source-control-plug-in-api-version-1-2.md)