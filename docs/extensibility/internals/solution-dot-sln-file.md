---
title: Çözüm (. Sln) dosya | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- sln files, VSPackages
- solutions, .sln files
- .sln files, VSPackages
ms.assetid: 7d7ef539-2e4b-4637-b853-8ec7626609df
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 73d6f7fb83e9420f59122135761ce44ea641fe57
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31133412"
---
# <a name="solution-sln-file"></a>Çözüm (. Sln) dosyası
Bir çözüm, Visual Studio projelerinde düzenlemek için bir yapıdır. Çözüm .sln (metin tabanlı, paylaşılan) ve (ikili, kullanıcıya özgü çözüm seçenekleri) .suo dosyaları projeler için durum bilgisini tutar. .Suo dosyaları hakkında daha fazla bilgi için bkz: [çözüm kullanıcı seçenekleri (. Suo) dosya](../../extensibility/internals/solution-user-options-dot-suo-file.md).  
  
 Ortamı, VSPackage .sln dosyasını başvuru sonucu olarak yüklenmişse, çağıran <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionProps.ReadSolutionProps%2A> .sln dosyasını okumak için.  
  
 .Sln dosyasını bulun ve kalıcı veri ve başvurduğu VSPackages proje için ad-değer parametreleri yükleme ortamı kullanır metin tabanlı bilgiler içerir. Bir çözümü bir kullanıcı oturum açtığında, ortam aracılığıyla döngüleri `preSolution`, `Project`, ve `postSolution` çözümü yüklemeye .sln dosyasındaki bilgileri projeleri çözüm içinde ve kalıcı bilgileri çözüme bağlı.  
  
 Her projenin dosya projenin öğeleri hiyerarşisiyle doldurmak için ortamı tarafından okunur ek bilgiler içerir. Hiyerarşi veri kalıcılığını proje tarafından kontrol edilir; Bunu yapmak seçerseniz .sln dosyasını proje bilgileri bilerek yazabilirsiniz karşın verileri .sln dosyasını normalde depolanmaz. Kalıcılığı için ilgili daha fazla bilgi için bkz: [proje kalıcılığı](../../extensibility/internals/project-persistence.md) ve [açma ve kaydetme proje öğeleri](../../extensibility/internals/opening-and-saving-project-items.md).  
  
## <a name="solution-file-contents"></a>Çözüm dosyası içeriği  
 .Sln dosyasını aşağıdaki kodda gösterildiği gibi birkaç bölümden oluşur.  
  
```  
Project("{F184B08F-C81C-45F6-A57F-5ABD9991F28F}") = "Project1", "Project1.vbproj", "{8CDD8387-B905-44A8-B5D5-07BB50E05BEA}"  
EndProject  
Global  
  GlobalSection(SolutionNotes) = postSolution  
  EndGlobalSection  
  GlobalSection(SolutionConfiguration) = preSolution  
       ConfigName.0 = Debug  
       ConfigName.1 = Release  
  EndGlobalSection  
  GlobalSection(ProjectDependencies) = postSolution  
  EndGlobalSection  
  GlobalSection(ProjectConfiguration) = postSolution  
   {8CDD8387-B905-44A8-B5D5-07BB50E05BEA}.Debug.ActiveCfg = Debug|x86  
   {8CDD8387-B905-44A8-B5D5-07BB50E05BEA}.Debug.Build.0 = Debug|x86  
   {8CDD8387-B905-44A8-B5D5-07BB50E05BEA}.Release.ActiveCfg = Release|x86  
   {8CDD8387-B905-44A8-B5D5-07BB50E05BEA}.Release.Build.0 = Release|x86  
  EndGlobalSection  
  GlobalSection(ExtensibilityGlobals) = postSolution  
  EndGlobalSection  
  GlobalSection(ExtensibilityAddIns) = postSolution  
  EndGlobalSection  
EndGlobal  
```  
  
 Bir çözümü yüklemek için aşağıdaki görev dizisi ortamı gerçekleştirir.  
  
1.  Ortam .sln dosyasını Genel bölümünü okur ve işaretlenmiş tüm bölümleri işler `preSolution`. Bu durumda, bu tür bir ifade vardır:  
  
    ```  
    GlobalSection(SolutionConfiguration) = preSolution  
         ConfigName.0 = Debug  
         ConfigName.1 = Release  
    ```  
  
     Zaman ortam okur `GlobalSection('name')` etiketi, bu eşlemeleri adı kayıt defterini kullanarak bir VSPackage. Anahtar adı, kayıt defterinde altında bulunması [HKLM\\< Uygulama kimliği kayıt defteri kök\>\SolutionPersistence\AggregateGUIDs]. Paket GUID'si (REG_SZ) girişleri yazdı VSPackage, anahtarları varsayılan değerdir.  
  
2.  Ortam çağrıları VSPackage yükler `QueryInterface` için VSPackage üzerinde <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionProps> arabirimi ve çağrıları <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionProps.ReadSolutionProps%2A> VSPackage verileri depolayabilirsiniz şekilde bölümünde verilerle yöntemi. Bu işlem her biri için ortam yinelenir `preSolution` bölümü.  
  
3.  Ortam proje Kalıcılık blokları yineler. Bu durumda, bir proje yok.  
  
    ```  
    Project("{F184B08F-C81C-45F6-A57F-5ABD9991F28F}") = "Project1",  
    "Project1.vbproj", "{8CDD8387-B905-44A8-B5D5-07BB50E05BEA}"  
    EndProject  
    ```  
  
     Bu bildirimi GUID benzersiz proje ve proje türüne GUID içerir. Bu bilgiler proje dosyası veya çözüme ait dosyaları bulmak için ortamı tarafından kullanılır ve VSPackage her proje için gerekli. GUID geçirilen proje <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFactory> proje ile ilgili belirli VSPackage yüklemek için daha sonra projeyi VSPackage tarafından yüklenir. Bu durumda, bu proje için yüklenen VSPackage Visual Basic ' dir.  
  
     Çözümdeki diğer projeler tarafından gerektiği şekilde erişilebilir böylece her proje bir benzersiz proje örnek kimliği devam edebilir. İdeal olarak, kaynak kodu denetimi altında çözüm ve projeler varsa, çözüme göreli yolun projeye olmalıdır. Çözümü ilk yüklendiğinde, proje dosyalarını kullanıcının makinesinde olamaz. Çözüm dosyasıyla ilişkili sunucuda depolanan proje dosyası sağlayarak bulundu ve kullanıcının makineye kopyaladığınız proje dosyası için görece basit değildir. Bunu daha sonra kopyalar ve proje için gerekli dosyaları geri kalanını yükler.  
  
4.  .Sln dosyasını Proje bölümünde yer alan bilgileri bağlı olarak, her proje dosyası ortam yükler. Proje sonra proje hiyerarşisi doldurma ve tüm iç içe geçmiş projeleri yüklenirken sorumludur.  
  
5.  .Sln dosyasını tüm bölümleri işlendikten sonra çözüm Çözüm Gezgini'nde görüntülenir ve kullanıcı tarafından değiştirilmek üzere hazırdır.  
  
 Çözümdeki bir proje uygulayan VSPackage yükleme başarısız olursa <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionProps.OnProjectLoadFailure%2A> yöntemi çağrılır ve her bir çözümü projede onu yapmış yüklemesi sırasında değişiklikleri yoksay olanağı verilir. Ayrıştırma hataları oluşursa, mümkün olduğunca fazla bilgi ile çözüm dosyalarını korunur ve ortam çözümü bozuk kullanıcı uyarı bir iletişim kutusu görüntüler.  
  
 Çözüm kaydedildiğinde veya kapalı, <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionProps.QuerySaveSolutionProps%2A> yöntemi çağrılır ve .sln dosyasına girilmesi gerekir çözüme değişiklik yapılıp yapılmadığını görmek için hiyerarşiye geçirildi. İçin geçirilen bir null değer `QuerySaveSolutionProps` içinde <xref:Microsoft.VisualStudio.Shell.Interop.VSQUERYSAVESLNPROPS>, çözüm için bilgi kalıcı olduğunu gösterir. Değer null değilse, kalıcı işaretçisine tarafından belirlenen belirli bir projenin bilgilerdir <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> arabirimi.  
  
 Kaydedilecek, bilgi ise <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionPersistence> arabirimi için bir işaretçi olarak adlandırılan <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionProps.SaveSolutionProps%2A> yöntemi. <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionProps.WriteSolutionProps%2A> Yöntemi ad-değer çiftlerinden almak için ortamı tarafından çağrıldıktan sonra `IPropertyBag` arabirim ve .sln dosyasını bilgilerini yazar.  
  
 `SaveSolutionProps` ve `WriteSolutionProps` nesneleri gelen kaydedilecek bilgi almak için ortamı tarafından yinelemeli olarak adlandırılır `IPropertyBag` tüm değişiklikleri .sln dosyasına girilene kadar arabirim. Bu şekilde, bilgiler çözüm ve çözüm kullanılabilir sonraki açılışında kalıcı emin olun.  
  
 .Sln dosyasını kaydetmek için herhangi bir şey olup olmadığını görmek için her yüklenen VSPackage numaralandırılır. Kayıt defteri anahtarlarını sorgulanan yükleme zamanında değil. Bellekte çözümü kaydedildiğinde olduklarından ortamı tüm yüklenen paketler hakkında bilir.  
  
 Girdiler .sln dosyasını içeren yalnızca `preSolution` ve `postSolution` bölümler. Benzer bölüm yok .suo dosyasında çözüm düzgün bir şekilde yüklemek için bu bilgiye gerektiğinden. .Suo dosyası, paylaşılabilir veya kaynak kodu denetimi altında yerleştirilen düşünülmeyen özel notlar gibi kullanıcıya özgü seçenekleri içerir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionProps>   
 [Çözüm kullanıcı seçenekleri (. Suo) dosyası](../../extensibility/internals/solution-user-options-dot-suo-file.md)   
 [Çözümler](../../extensibility/internals/solutions.md)