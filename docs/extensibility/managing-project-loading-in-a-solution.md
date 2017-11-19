---
title: "Bir çözümde proje yükleme yönetme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: solutions, managing project loading
ms.assetid: 097c89d0-f76a-4aaf-ada9-9a778bd179a0
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: b28db42e17e95ea7c354f5ba4d7b0c231c2d2fe5
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="managing-project-loading-in-a-solution"></a>Bir çözümde yönetme proje yükleniyor
Visual Studio çözümleri, çok sayıda projeleri içerebilir. Varsayılan Visual Studio çözümü açıldığında bir çözümdeki tüm projeleri yüklemek için ve bunların tümünün Yükleme tamamlanana kadar projelerin hiçbiri erişmek kullanıcı izin vermeyecek şekilde davranıştır. Proje yükleme işlemini iki dakikadan fazla en son ne zaman, yüklenen projelerinin sayısına ve projeleri toplam sayısını gösteren bir ilerleme çubuğu görüntülenir. Bir çözümde birden çok proje ile çalışırken, kullanıcı projeleri unload, ancak bu yordamı bazı dezavantajları vardır: bellekten projeleri, çözümü yeniden derle komutun bir parçası oluşturulan değil ve IntelliSense açıklamaları türleri ve üyeleri kapalı projeleri görüntülenmez.  
  
 Geliştiriciler çözüm yükleme süreleri azaltmak ve Proje Yöneticisi bir çözüm yük oluşturarak yükleme davranışını yönetebilirsiniz. Çözüm yük Yöneticisi'ni belirli projeler veya proje türleri için öncelikleri yüklenirken farklı proje ayarlayın, bir arka plan yapı başlatmadan önce projeleri yüklendiğinden emin olun, diğer arka plan görevleri tamamlanana kadar arka planda yüklenirken gecikme ve gerçekleştirmek diğer proje yükleme yönetim görevleri.  
  
## <a name="project-loading-priorities"></a>Proje öncelikleri yükleniyor  
 Visual Studio dört farklı proje yükleme öncelikleri tanımlar:  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop._VSProjectLoadPriority>(varsayılan): bir çözümü açtığınızda projeleri zaman uyumsuz olarak yüklenir. Çözüm zaten açıldıktan sonra kaldırılan bir projede bu öncelik ayarlanırsa, proje sonraki boşta noktada yüklenecek.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop._VSProjectLoadPriority>: bir çözümü açtığınızda projeleri kullanıcının yüklenen tüm projeleri yüklenene kadar beklemek zorunda kalmadan oldukları gibi projeleri erişmesine izin verme arka planda yüklenir.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop._VSProjectLoadPriority>: Bunlar erişildiğinde projeleri yüklenir. Kullanıcı, (çözümün kullanıcı seçenekleri dosyası'nda kalıcı) açık belge listesinde olduğundan çözümü açıldığında projeye ait bir dosya açıldığında ya da Çözüm Gezgini'nde, proje düğümüne genişletirken proje erişilir başka bir projeye diğer bir deyişle projede sahip bağımlılık yükleniyor. Bu tür bir proje oluşturma işlemi başlamadan önce otomatik olarak yüklü değil; Çözüm yük Yöneticisi'ni, gerekli tüm projeleri yüklenmesini sağlamak için sorumludur. Bu projeleri de bulun ve değiştirin dosyalarında çözümün tamamında arasında başlatmadan önce yüklenmelidir.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop._VSProjectLoadPriority>: Proje yoksa kullanıcı formu açıkça istemedikçe yüklenmesi değil. Projeleri açıkça kaldırılan olduğunda bu durumdur.  
  
## <a name="creating-a-solution-load-manager"></a>Bir çözüm yük Yöneticisi oluşturma  
 Geliştiriciler oluşturabileceğiniz bir çözüm yük Yöneticisi uygulayarak <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionLoadManager> ve Visual Studio çözümü yük Yöneticisi'ni etkin olduğunu bildiren.  
  
#### <a name="activating-a-solution-load-manager"></a>Bir çözüm yük Yöneticisi'ni etkinleştirme  
 Çözüm yük etkinleştirmek istediğinizde Visual Studio bildirmek için visual Studio Yöneticisi belirli bir zamanda yalnızca bir çözüm yük Yöneticisi'ni sağlar. İkinci bir çözüm yük Yöneticisi daha sonra etkinleştirilmişse, çözüm yük yöneticinize kesilecektir.  
  
 Almanız gerekir <xref:Microsoft.VisualStudio.Shell.Interop.SVsSolution> ayarlayın ve hizmeti <xref:Microsoft.VisualStudio.Shell.Interop.__VSPROPID4> özelliği:  
  
```csharp  
IVsSolution pSolution = GetService(typeof(SVsSolution)) as IVsSolution;  
object objLoadMgr = this;   //the class that implements IVsSolutionManager  
pSolution.SetProperty((int)__VSPROPID4.VSPROPID_ActiveSolutionLoadManager, objLoadMgr);  
```  
  
#### <a name="implementing-ivssolutionloadmanager"></a>IVsSolutionLoadManager uygulama  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionLoadManager.OnBeforeOpenProject%2A> Yöntemi çözümü açma işlemi sırasında çağrılır. Bu yöntem uygulamak için kullandığınız <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionLoadManagerSupport> yönetmek istediğiniz proje türüne ilişkin Yük önceliğini ayarlamak için hizmet. Örneğin, aşağıdaki kod arka planda yüklemek için C# proje türleri ayarlar:  
  
```csharp  
Guid guidCSProjectType = new Guid("{FAE04EC0-301F-11d3-BF4B-00C04F79EFBC}");  
pSLMgrSupport.SetProjectLoadPriority(guidProjectID, (uint)_VSProjectLoadPriority.PLP_BackgroundLoad);  
```  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionLoadManager.OnDisconnect%2A> Visual Studio kapatılıyor olduğunda veya farklı bir paket etkin çözüm yük Yöneticisi'ni arayarak edildiğinde yöntemi çağrıldığında <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution.SetProperty%2A> ile <xref:Microsoft.VisualStudio.Shell.Interop.__VSPROPID4> özelliği.  
  
#### <a name="strategies-for-different-kinds-of-solution-load-manager"></a>Farklı türde çözüm yük Yöneticisi stratejileri  
 Yönetmek üzere tasarlanmışlardır çözümlerinin türlerine bağlı olarak, farklı şekillerde çözüm yük yöneticilerini kullanır.  
  
 Genel yükleme çözümü yönetmek için çözüm yük Yöneticisi'ni istediyseniz bir VSPackage bir parçası olarak uygulanabilir. Paket ekleyerek autoload için ayarlanmalıdır <xref:Microsoft.VisualStudio.Shell.ProvideAutoLoadAttribute> değerini VSPackage üzerinde <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT.SolutionOpening_guid>. Çözüm yük Yöneticisi'ni, sonra etkinleştirilebilir <xref:Microsoft.VisualStudio.Shell.Package.Initialize%2A> yöntemi.  
  
> [!NOTE]
>  Autoloading paketler hakkında daha fazla bilgi için bkz: [yüklenirken VSPackages](../extensibility/loading-vspackages.md).  
  
 Visual Studio etkinleştirilmesi için yalnızca son çözüm yük Yöneticisi tanıdığı olduğundan, genel çözüm yük yöneticileri olup olmadığını var olan bir yükleme yöneticisi kendilerini etkinleştirmeden önce her zaman tanımalıdır. GetProperty() çözüm hizmeti için çağrılması durumunda <xref:Microsoft.VisualStudio.Shell.Interop.__VSPROPID4> döndürür `null`, hiçbir etkin çözüm yük Yöneticisi yoktur. Null döndürmezse, nesne çözüm yük Yöneticisi ile aynı olup olmadığını denetleyin.  
  
 Yalnızca birkaç çözüm türlerini yönetmek için çözüm yük Yöneticisi'ni istediyseniz VSPackage çözüm yük olaylarına abone olabilir (çağırarak <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution.AdviseSolutionEvents%2A>) ve için olay işleyicisini kullanmak <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionLoadEvents.OnBeforeOpenSolution%2A> çözüm yük Yöneticisi'ni etkinleştirmek için.  
  
 Yalnızca belirli çözümleri yönetmek için çözüm yük Yöneticisi'ni istediyseniz etkinleştirme bilgilerini çözüm dosyasını bir parçası olarak kalıcı. Bunu yapmak için arama <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionProps.WriteSolutionProps%2A> öncesi çözüm bölümü için.  
  
 Belirli çözüm yük yöneticileri devre dışı bırakma kendileri de <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents.OnAfterCloseSolution%2A> diğer çözüm yük yöneticilerle çakışmaması sırayla olay işleyicisi.  
  
 Genel proje yük önceliklerini (örneğin, bir seçenekleri sayfasında ayarlamak özellikleri) kalıcı hale getirmek için çözüm yük Yöneticisi'nde etkinleştirebilirsiniz yalnızca bir çözüm yük Yöneticisi gerekiyorsa <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3.OnAfterOpenProject%2A> olay işleyicisi çözüm özellikleri sonra ayarında Sürdür Çözüm yük Yöneticisi'ni devre dışı bırakın.  
  
## <a name="handling-solution-load-events"></a>Çözüm yük olayları işleme  
 Çözüm yük olaylarına abone olmak için arama <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution.AdviseSolutionEvents%2A> çözüm yük yöneticinize etkinleştirdiğinizde. Öğesini uygularsanız <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionLoadEvents>, farklı proje öncelikleri yüklenirken ilişkili olaylara yanıt verebilir.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionLoadEvents.OnBeforeOpenSolution%2A>: Bu, bir çözüm açılmadan önce tetiklenir. Çözümdeki projeler için öncelik yüklenirken proje değiştirmek için kullanabilirsiniz.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionLoadEvents.OnBeforeBackgroundSolutionLoadBegins%2A>: Bu çözümü tamamen yüklenir, ancak önce arka plan yüklenirken proje yeniden başladıktan sonra ateşlenir. Örneğin, bir kullanıcı LoadIfNeeded yük önceliğini olduğu projesinde erişmiş veya bir arka plan yük projenin başlarsınız BackgroundLoad çözüm yük Yöneticisi'ni bir proje yük önceliğini değişmiş olabilir.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionLoadEvents.OnAfterBackgroundSolutionLoadComplete%2A>: Bir çözüm başlangıçta tamamen yüklendikten sonra var olup olmadığını çözüm yük Yöneticisi bu tetiklenir. Arka plan yük veya isteğe bağlı yükleme sonra çözümü tam olarak yüklenen olur her ayrıca tetiklenir. Aynı anda <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT.SolutionExistsAndFullyLoaded_guid> yeniden etkinleştirilir.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionLoadEvents.OnQueryBackgroundLoadProjectBatch%2A>: Bu proje (veya projeleri) yüklenmesini önce tetiklenir. Projeleri yüklenmeden önce diğer arka plan işlemleri tamamlandığından emin olmak için ayarlanmış `pfShouldDelayLoadToNextIdle` için **doğru**.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionLoadEvents.OnBeforeLoadProjectBatch%2A>: Bu projeleri toplu hakkında yüklenmesi olduğunda tetiklenir. Varsa `fIsBackgroundIdleBatch` projeleri olup arka planda; yüklenecek doğrudur `fIsBackgroundIdleBatch` proje yoksa örneğin kullanıcı Çözüm Gezgini'nde bekleyen bir projeye genişletir, zaman uyumlu olarak bir kullanıcı isteği sonucunda yüklenecek false olur. Aksi takdirde yapılması gerekir pahalı işlerini yapmak için uygulayabileceğiniz <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3.OnAfterOpenProject%2A>.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionLoadEvents.OnAfterLoadProjectBatch%2A>: Bu projeleri toplu yüklendikten sonra ateşlenir.  
  
## <a name="detecting-and-managing-solution-and-project-loading"></a>Algılama ve çözüm ve proje yükleme yönetme  
 Projeler ve çözümler yüklenme durumunu saptamak amacıyla çağrı <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution.GetProperty%2A> aşağıdaki değerlere sahip:  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.__VSPROPID4>: `var` döndürür `true` çözümü ve tüm projeleri, aksi takdirde yüklenirse `false`.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.__VSPROPID4>: `var` döndürür `true` projeleri toplu şu anda yükleniyor, arka planda, aksi takdirde `false`.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.__VSPROPID4>: `var` döndürür `true` projeleri toplu şu anda yükleniyor, zaman uyumlu olarak bir kullanıcı komut veya diğer açık yük sonucu aksi `false`.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.__VSPROPID2>: `var` döndürür `true` çözümü şu anda, aksi takdirde kapatıldığını varsa `false`.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.__VSPROPID>: `var` döndürür `true` bir çözüm şu anda, aksi takdirde açılıyorsa `false`.  
  
 Ayrıca (Proje yük öncelikleri nelerdir olsun) projeler ve çözümler yüklenen aşağıdaki yöntemlerden birini çağırarak sağlayabilirsiniz:  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution4.EnsureSolutionIsLoaded%2A>: Bu yöntemi çağırmadan yöntemi döndürmeden önce yüklemek için bir çözüm projelerinde zorlar.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution4.EnsureProjectIsLoaded%2A>: Bu yöntemi çağırmadan zorlar projelerinde `guidProject` yöntemi döndürmeden önce yüklemek için.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution4.EnsureProjectsAreLoaded%2A>: Bu yöntemi çağırmadan zorlar projede `guidProjectID` yöntemi döndürmeden önce yüklemek için.  
  
> [!NOTE]
>  biçimindeki telefon numarasıdır. Varsayılan olarak yalnızca talep projeleri yüklemek ve arka plan yük öncelikleri yüklenir, ancak varsa <xref:Microsoft.VisualStudio.Shell.Interop.__VSBSLFLAGS> bayrağı yönteme geçirilir, açıkça yüklemek için işaretlenmiş olanlar dışında tüm projeleri yüklenecek.