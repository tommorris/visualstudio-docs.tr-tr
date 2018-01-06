---
title: "Denetim listesi: eski dil hizmet oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- language services
- language services, native code
ms.assetid: 8b73b341-a33a-4ab5-9390-178c9e563d2d
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: b09176efca3a8839d5e6a741a1e161ff61cdc7ca
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="checklist-creating-a-legacy-language-service"></a>Denetim listesi: eski dil hizmet oluşturma
Aşağıdaki denetim listesi için bir dil hizmeti oluşturmak için gerçekleştirmeniz gereken temel adımları özetlemektedir [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] çekirdek Düzenleyici. Dil hizmetinizi tümleştirmek için [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], bir hata ayıklama ifade değerlendiricisi oluşturmanız gerekir. Daha fazla bilgi için bkz: [bir CLR ifade değerlendiricisi yazma](../../extensibility/debugger/writing-a-common-language-runtime-expression-evaluator.md) içinde [Visual Studio hata ayıklayıcısı genişletilebilirlik](../../extensibility/debugger/visual-studio-debugger-extensibility.md).  
  
## <a name="steps-for-creating-a-language-service"></a>Bir dil hizmeti oluşturma adımları  
  
1.  Uygulama <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage> arabirimi.  
  
    -   VSPackage, uygulama <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider> dil hizmet sağlamak için arabirim.  
  
    -   Dil hizmetiniz tümleşik geliştirme ortamı (IDE) kullanımına, <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.SetSite%2A> uygulaması.  
  
2.  Uygulama <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo> ana dil Hizmet sınıfında arabirimi.  
  
     <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo> Arabirimi çekirdek Düzenleyicisi'ni ve dil hizmeti arasındaki etkileşim başlangıç noktasıdır.  
  
### <a name="optional-features"></a>İsteğe bağlı özellikler  
 Aşağıdaki özellikleri isteğe bağlıdır ve herhangi bir sırada uygulanabilir. Bu özellikler dil hizmetinizi işlevselliğini artırır.  
  
-   Sözdizimi renklendirmesi  
  
     Uygulama <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer> arabirimi. Bu arabirim, uygulamanızı uygun renk bilgileri döndürmek için ayrıştırıcı bilgi gerekir.  
  
     <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo.GetColorizer%2A> Yöntemi döndürür <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer> arabirimi. Uygulamanız gerekir böylece ayrı Renklendirici örneği her metin arabelleği için oluşturulan <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer> ayrı olarak arabirim. Daha fazla bilgi için bkz: [sözdizimi renkleri eski dil hizmetindeki](../../extensibility/internals/syntax-coloring-in-a-legacy-language-service.md).  
  
-   Kod penceresi  
  
     Uygulama <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindowManager> yeni bir kod penceresi oluşturulduğunda, bildirim almak dil hizmetini etkinleştirmek için arabirim.  
  
     <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo.GetCodeWindowManager%2A> Yöntemi döndürür <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindowManager> arabirimi. Dil hizmeti ardından özel kullanıcı Arabirimi kod penceresinde ekleyebilirsiniz <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindowManager.AddAdornments%2A>. Dil hizmeti da metin görünümü filtre ekleme gibi özel işlem yapabilirsiniz <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindowManager.OnNewView%2A>.  
  
-   Metin Görünümü Filtresi  
  
     IntelliSense deyim tamamlama dil hizmetindeki sağlamak için bazı metin görünümü başka türlü işleyebilirsiniz komutlar müdahale gerekir. Bu komutlar müdahale için aşağıdaki adımları tamamlayın:  
  
    -   Uygulama <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> komut zinciri ve tanıtıcı Düzenleyici komutlar katılmayı.  
  
    -   Çağrı <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.AddCommandFilter%2A> yöntemi ve geçişinde, <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> uygulaması.  
  
    -   Çağrı <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.RemoveCommandFilter%2A> böylece bu komutları artık size geçirilir görünümden ayırdığınızda yöntemi.  
  
     Ele alınması gereken komutları sağlanan hizmetlere bağlıdır. Daha fazla bilgi için bkz: [dil hizmeti filtreleri için önemli komutları](../../extensibility/internals/important-commands-for-language-service-filters.md).  
  
    > [!NOTE]
    >  <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextViewFilter> Arabirimi uygulanan, aynı nesne üzerinde <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> arabirimi.  
  
-   Deyim tamamlama  
  
     Uygulama <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCompletionSet> arabirimi.  
  
     Deyim tamamlama komutunu desteklemez (diğer bir deyişle, <xref:Microsoft.VisualStudio.VSConstants.VSStd2KCmdID>) ve arama <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.UpdateCompletionStatus%2A> yönteminde <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> geçirme arabirimi <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCompletionSet> arabirimi. Daha fazla bilgi için bkz: [deyim tamamlama eski dil hizmetindeki](../../extensibility/internals/statement-completion-in-a-legacy-language-service.md).  
  
-   Yöntem ipuçları  
  
     Uygulama <xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodData> yöntemi ipucu penceresi veri sağlamak için arabirim.  
  
     Bir yöntem veri ipucu penceresi göstermek ne zaman bilmesi komutları uygun şekilde, işlemek üzere metin Görünümü Filtresi yükleyin. Daha fazla bilgi için bkz: [parametre bilgisi eski dil hizmetindeki](../../extensibility/internals/parameter-info-in-a-legacy-language-service1.md).  
  
-   Hata işaretçileri  
  
     Uygulama <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClient> arabirimi.  
  
     Uygulayan işaret nesneler oluşturma hatası <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClient> arabirimi ve çağrı <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines.CreateLineMarker%2A> geçirerek yöntemini <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClient> hata işaret nesnesinin arabirimi.  
  
     Genellikle her hata işaret Görev Listesi penceresi bir öğeyi yönetir.  
  
-   Görev listesi öğeleri  
  
     Bir görev öğesi sınıfı sağlayarak uygulama <xref:Microsoft.VisualStudio.Shell.Interop.IVsTaskItem> arabirimi.  
  
     Bir görev sağlayıcısı sınıfı sağlayarak uygulama <xref:Microsoft.VisualStudio.Shell.Interop.IVsTaskProvider> arabirimi ve <xref:Microsoft.VisualStudio.Shell.Interop.IVsTaskProvider2> arabirimi.  
  
     Bir görev Numaralandırıcı sınıfı sağlayarak uygulama <xref:Microsoft.VisualStudio.Shell.Interop.IVsEnumTaskItems> arabirimi.  
  
     Görev listesi ile 's görev sağlayıcısını Kaydet <xref:Microsoft.VisualStudio.Shell.Interop.IVsTaskList.RegisterTaskProvider%2A> yöntemi.  
  
     Elde <xref:Microsoft.VisualStudio.Shell.Interop.IVsTaskList> dil hizmetin hizmet sağlayıcısı GUID hizmetiyle çağırarak arabirim <xref:Microsoft.VisualStudio.Shell.Interop.SVsTaskList>.  
  
     Görev öğesi nesneleri ve çağrı oluşturma <xref:Microsoft.VisualStudio.Shell.Interop.IVsTaskList.RefreshTasks%2A> yönteminde <xref:Microsoft.VisualStudio.Shell.Interop.IVsTaskList> arabirim olduğunda yeni veya güncelleştirilmiş görevler.  
  
-   Açıklama görev öğeleri  
  
     Kullanım <xref:Microsoft.VisualStudio.Shell.Interop.IVsCommentTaskInfo> arabirimi ve <xref:Microsoft.VisualStudio.Shell.Interop.IVsEnumCommentTaskTokens> açıklama görev belirteçleri elde etmek için arabirim.  
  
     Elde bir <xref:Microsoft.VisualStudio.Shell.Interop.IVsCommentTaskInfo> alanından arabirim <xref:Microsoft.VisualStudio.Shell.Interop.SVsTaskList> hizmet.  
  
     Elde <xref:Microsoft.VisualStudio.Shell.Interop.IVsEnumCommentTaskTokens> alanından arabirim <xref:Microsoft.VisualStudio.Shell.Interop.IVsCommentTaskInfo.EnumTokens%2A> yöntemi.  
  
     Uygulama <xref:Microsoft.VisualStudio.Shell.Interop.IVsTaskListEvents> belirteci listesindeki değişiklikleri dinlemek için arabirim.  
  
-   Anahat Oluşturma  
  
     Anahat oluşturma desteklemek için birkaç seçeneğiniz vardır. Örneğin, destekleyebilir **daraltmak için tanımları** komutu, Düzenleyicisi denetimli anahat bölgeler sağlamaz veya istemci tarafından denetlenen bölgeler desteklemez. Daha fazla bilgi için bkz: [nasıl yapılır: sağlayan genişletilmiş anahat oluşturma desteği eski dil hizmeti](../../extensibility/internals/how-to-provide-expanded-outlining-support-in-a-legacy-language-service.md).  
  
-   Dil hizmet kaydı  
  
     Bir dil hizmeti kaydetme hakkında daha fazla bilgi için bkz: [eski dil hizmeti kaydetme](../../extensibility/internals/registering-a-legacy-language-service2.md) ve [yönetme VSPackages](../../extensibility/managing-vspackages.md).  
  
-   Bağlama duyarlı Yardım  
  
     Bağlam için Düzenleyicisi'ni aşağıdaki yollardan biriyle sağlar:  
  
    -   Bağlam için metin işaretçileri uygulayarak sağlamak <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerContextProvider> arabirimi.  
  
 Tüm kullanıcı bağlamı uygulama tarafından sağlamak <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageContextProvider> arabirimi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eski dil hizmeti geliştirme](../../extensibility/internals/developing-a-legacy-language-service.md)   
 [Bir CLR ifade değerlendiricisi yazma](../../extensibility/debugger/writing-a-common-language-runtime-expression-evaluator.md)