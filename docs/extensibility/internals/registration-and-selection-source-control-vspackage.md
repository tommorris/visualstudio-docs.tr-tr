---
title: Kayıt ve seçim (kaynak denetimi VSPackage) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- registration, source control packages
- source control packages, registration
ms.assetid: 7d21fe48-489a-4f55-acb5-73da64c4e155
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 1d7bcdb8f930430ac00335777e2c088ce52a34bb
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="registration-and-selection-source-control-vspackage"></a>Kayıt ve seçim (kaynak denetimi VSPackage)
VSPackage kayıtlı, kendisine kullanıma sunmak için bir kaynak denetimi [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. Birden fazla kaynak denetimi VSPackage kaydettiyseniz, kullanıcı uygun zamanlarda yüklemek için hangi VSPackage seçebilirsiniz. Bkz: [VSPackages](../../extensibility/internals/vspackages.md) VSPackages ve bunları kaydetmek nasıl daha ayrıntılı bilgi için.  
  
## <a name="registering-a-source-control-package"></a>Kaynak denetimi paketi kaydediliyor  
 Kaynak denetimi paketi kayıtlı böylece [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ortamı için desteklenen özellikleri ve sorgu bulabilir. Bu bir paket örneği yalnızca kendi özellikleri komutları gereklidir veya açıkça istenen oluşturulduğu bir gecikme yükleme uygun olarak düzenidir.  
  
 VSPackages yerleştirin bilgi HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio bir sürüme özgü kayıt defteri anahtarında\\*X.Y*, burada *X* ana sürüm numarası ve *Y* ikincil sürüm numarası. Bu uygulama birden fazla sürümünü yan yana yüklenmesini destekler olanağı sağlar [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Kullanıcı arabirimi (UI), kaynak denetimi VSPackages yanı sıra birden fazla yüklü kaynak denetimi eklenti (aracılığıyla kaynak denetimi bağdaştırıcı paketi) arasından seçim destekler. Olabilir yalnızca bir etkin kaynak denetim eklentisi veya VSPackage aynı anda. Ancak, aşağıda açıklandığı gibi IDE kaynak denetimi eklentiler ve VSPackages arasında bir otomatik çözüm tabanlı Paket Değişimi mekanizması geçiş sağlar. Bu seçim mekanizmasını etkinleştirmek için kaynak denetimi VSPackage bölümüne bazı gereksinimler vardır.  
  
### <a name="registry-entries"></a>Kayıt defteri girdileri  
 Kaynak denetimi paketi üç özel GUID'ler gerekir:  
  
-   Paket GUID'ini: (Bu bölümdeki ID_Package olarak adlandırılır) kaynak denetimi uyarlamasını içeren paket için ana GUID budur.  
  
-   Kaynak denetimi GUID: Bu kaynak denetimi ile Visual Studio kaynak denetimi saplama kaydetmek için kullanılan VSPackage için bir GUID ve komut UI bağlamı GUID olarak da kullanılır. Kaynak denetimi hizmeti GUID GUID kaynak denetimi altında kayıtlı değil. Örnekte, kaynak denetimi GUID ID_SccProvider adı verilir.  
  
-   Kaynak denetimi hizmeti GUID: Bu özel (Bu bölümdeki SID_SccPkgService olarak adlandırılır) Visual Studio tarafından kullanılan GUID hizmetidir. Buna ek olarak, diğer GUID'ler VSPackages, aracı windows tanımlamak ve benzeri kaynak denetimi paketi gerekir.  
  
 Aşağıdaki kayıt defteri girdileri kaynak denetimi VSPackage tarafından yapılması gerekir:  
  
|Anahtar adı|Girdileri|  
|--------------|-------------|  
|`HKEY_LOCAL_MACHINE\   SOFTWARE\     Microsoft\       VisualStudio\         X.Y\           SourceControlProviders\`|(varsayılan) rg_sz =: {ID_SccProvider}|  
|`HKEY_LOCAL_MACHINE\   SOFTWARE\     Microsoft\       VisualStudio\         X.Y\           SourceControlProviders\             {ID_SccProvider}\`|(varsayılan) rg_sz =:\<paketin kolay adı ><br /><br /> Hizmet rg_sz =: {SID_SccPkgService}|  
|`HKEY_LOCAL_MACHINE\   SOFTWARE\     Microsoft\       VisualStudio\         X.Y\           SourceControlProviders\             {ID_SccProvider}\               Name\`|(varsayılan) rg_sz =: #\<yerelleştirilmiş adı için kaynak kimliği ><br /><br /> Paket rg_sz =: {ID_Package}|  
|`HKEY_LOCAL_MACHINE\   SOFTWARE\     Microsoft\       VisualStudio\         X.Y\           SolutionPersistence\             <PackageName>\`<br /><br /> (Unutmayın anahtar adı `SourceCodeControl`, tarafından kullanılan [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ve bir seçenek olarak sağlanabilmesi için kullanılabilir değil \<PackageName >.)|(varsayılan) rg_sz =: {ID_Package}|  
  
## <a name="selecting-a-source-control-package"></a>Kaynak denetimi paketi seçme  
 Birden fazla kaynak denetim eklentisi API tabanlı eklentiler ve kaynak denetimi VSPackages eşzamanlı olarak kaydedilebilir. Kaynak denetimi eklenti veya VSPackage seçme emin olmanız gerekir [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] eklenti yükler veya VSPackage uygun zaman ve gerektiği kadar gereksiz Bileşenler yüklenirken erteler. Ayrıca, [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] menü öğeleri, iletişim kutuları ve araç çubukları gibi diğer etkin olmayan VSPackages tüm kullanıcı Arabirimi kaldırmanız ve kullanıcı arabirimini görüntülemek için etkin VSPackage gerekiyor.  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] aşağıdaki işlemleri herhangi biri gerçekleştirildiğinde kaynak denetimi VSPackage yükler:  
  
-   Çözüm (Çözüm kaynak denetimi altında olduğunda) açılır.  
  
     Bir çözüm ya da kaynak denetimindeki proje açıldığında, IDE kaynak denetimi yüklenmesi için bu çözümü belirlendiyse VSPackage neden olur.  
  
-   Kaynak denetimi VSPackage menü komutlarını hiçbirini yürütülür.  
  
 Bir kaynak denetimi VSPackage yalnızca bunlar aslında olacak olduğunda, gereken tüm bileşenleri yüklenecektir (Aksi Gecikmeli yükleme olarak bilinir) kullanılır.  
  
### <a name="automatic-solution-based-vspackage-swapping"></a>Otomatik çözüm tabanlı VSPackage değiştirme  
 Kaynak denetimi VSPackages el ile takas edebilirsiniz aracılığıyla [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] **seçenekleri** iletişim kutusunda altında **kaynak denetimi** kategorisi. Otomatik çözüm tabanlı paket değiştirme, bu çözüm açıldığında, belirli bir çözümü için belirtilen kaynak denetim paketi etkin olarak otomatik olarak ayarlanmış anlamına gelir. Her kaynak denetimi paketi uygulamalıdır <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProvider.SetActive%2A> ve <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProvider.SetInactive%2A>. [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] her ikisi arasında geçiş yapma işleme kaynağı (kaynak denetimi eklentisi API uygulama) denetim eklentiler ve kaynak denetimi VSPackages.  
  
 Kaynak denetimi bağdaştırıcı paketi her kaynak denetimi eklentisi API tabanlı geçiş yapmak için kullanılan eklentisi. Ara kaynak denetimi bağdaştırıcı paketi geçiş ve hangi kaynak denetim eklentisi belirleme işleminin etkin veya devre dışı kullanıcı için saydamdır ayarlanması gerekir. Eklenti herhangi bir kaynak denetimi etkin olduğunda bağdaştırıcı paketini her zaman etkindir. Sadece yükleme ve eklenti DLL'i kaldırma iki kaynak denetimi eklentileri tutarlarının arasında geçiş yapma. Kaynak denetimi VSPackage değiştirme, ancak uygun VSPackage yüklemek için IDE ile etkileşim içerir.  
  
 Kaynak denetimi VSPackage herhangi bir çözüm açılır ve çözüm dosyasında VSPackage kayıt defteri anahtarı olduğunda çağrılır. Çözüm açıldığında [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] kayıt defteri değerini bulur ve uygun kaynak denetimi VSPackage yükler. Tüm kaynak denetimi VSPackages yukarıda açıklanan kayıt defteri girişleri olması gerekir. Kaynak denetimi altında bir çözüm, belirli kaynak denetimi VSPackage ile ilişkili olarak işaretlenir. Kaynak denetimi VSPackages uygulanmalı <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionPersistence> otomatik çözüm tabanlı VSPackage takas etkinleştirmek için.  
  
### <a name="visual-studio-ui-for-package-selection-and-switching"></a>Visual Studio Paketi seçimi ve geçişi için kullanıcı Arabirimi  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] bir kaynak denetimi VSPackage için kullanıcı Arabirimi ve eklenti seçimde sağlayan **seçenekleri** iletişim kutusunda altında **kaynak denetimi** kategori. Eklenti etkin kaynak denetim seçmek için kullanıcı veya VSPackage sağlar. Aşağı açılan listesini içerir:  
  
-   Tüm kaynak denetim paketleri yüklü  
  
-   Tüm kaynak denetim eklentileri yüklü  
  
-   "none", hangi kaynak kodu denetimi devre dışı bırakır seçeneği  
  
 Yalnızca etkin kaynak denetim seçim için kullanıcı Arabirimi görünür olur. VSPackage seçimi için önceki VSPackage kullanıcı arabirimini gizler ve yeni bir kullanıcı Arabirimi gösterir. Bir kullanıcı başına temelinde etkin VSPackage seçilir. Bir kullanıcının birden çok kopyasını varsa [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] eşzamanlı olarak açın, her biri farklı bir etkin VSPackage potansiyel olarak kullanabilirsiniz. Birden çok kullanıcı aynı bilgisayarda oturum açtıysanız, her kullanıcının ayrı ayrı örnekleri olabilir [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] açın, her biri farklı bir etkin VSPackage. Zaman birden çok örneğini [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] kaynak denetimi son açık çözüm varsayılan kaynak denetimi yeniden başlatma sırasında etkin olarak ayarlanacağını VSPackage haline gelir, etkin VSPackage bir kullanıcı tarafından kapatıldı.  
  
 Önceki sürümlerinden farklı olarak [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], bir IDE yeniden başlatma artık kaynak denetimi VSPackages geçiş yapmak için tek yoludur. VSPackage seçimi otomatik olarak yapılır. Paketleri geçiş (yönetici veya Power User) Windows kullanıcı ayrıcalıkları gerektirir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionPersistence>   
 [Özellikleri](../../extensibility/internals/source-control-vspackage-features.md)   
 [Kaynak Denetimi Eklentisi oluşturma](../../extensibility/internals/creating-a-source-control-plug-in.md)   
 [VSPackage’lar](../../extensibility/internals/vspackages.md)