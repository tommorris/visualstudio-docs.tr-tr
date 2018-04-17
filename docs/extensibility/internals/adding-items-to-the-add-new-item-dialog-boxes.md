---
title: Öğeler ekleme yeni öğe Ekle iletişim kutuları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- Add New Item dialog box, adding items
ms.assetid: 2f70863b-425b-4e65-86b4-d6a898e29dc7
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: a24a6d531812a170768f8c100f14ad64ab1e68c5
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="adding-items-to-the-add-new-item-dialog-boxes"></a>Öğeler ekleme yeni öğe Ekle iletişim kutuları
Öğeler ekleme işlemi **Yeni Öğe Ekle** iletişim kutusu ile kayıt defteri anahtarlarını başlatır. Aşağıdaki kayıt defteri girdileri gösterildiği gibi AddItemTemplates bölüm içinde kullanılabilir hale hangi öğelerin dizininde adını ve yolunu içerir **Yeni Öğe Ekle** iletişim kutusu konur.  
  
> [!NOTE]
>  Tablonun hemen kod kesimi aşağıdaki kayıt defteri girdisi hakkında ek bilgiler içerir.  
  
 Bu bölümde [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\14.0Exp\Projects] altında yer alır.  
  
 Bu tür projelerde CLSID ilk GUID'dir; İkinci GUID öğeleri Ekle şablonları için kayıtlı proje türünü belirtir.  
  
 \\{C061DB26-5833-11D2-96F5-000000000000} \AddItemTemplates\TemplateDirs\ {ACEF4EB2-57CF-11D2-96F4-000000000000} \1  
  
 @="#6"  
  
 "TemplatesDir"="\<Visual Studio SDK yükleme yolu\\\VSIntegration\\\SomeFolder\\\SomePackage\\\SomeProject\\\SomeProjectItems"  
  
 "SortPriority" dword:00000064 =  
  
|Ad|Tür|Verilerden (.rgs dosyası)|Açıklama|  
|----------|----------|-----------------------------|-----------------|  
|@ (Varsayılan)|REG_SZ|#% IDS_ADDITEM_TEMPLATES_ENTRY %|Kaynak kimliği için **Öğe Ekle** şablonları.|  
|VAL TemplatesDir|REG_SZ|%TEMPLATE_PATH%\ SomeProjectItems|İletişim kutusunda görüntülenen proje öğeleri yolunu **Yeni Öğe Ekle** Sihirbazı.|  
|VAL SortPriority|REG_DWORD|100 ([!INCLUDE[vcprx64](../../extensibility/internals/includes/vcprx64_md.md)])|Ağaç düğümünde görüntülenen dosyalar, sıralama düzeni belirler **Yeni Öğe Ekle** iletişim kutusu.|  
  
> [!NOTE]
>  Visual C# ve Visual Basic proje türleri GUID'LERİNİ aşağıdaki gibidir:[!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)]: {FAE04EC0-301F-11D3-BF4B-00C04F79EFBC}[!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)]: {F184B08F-C81C-45F6-A57F-5ABD9991F28F}  
  
 Dizini listelenen % TEMPLATE_PATH%\SomeProjectItems olan TemplateDirs sol tarafındaki düğümde için **Yeni Öğe Ekle** iletişim kutusu ağacı. Ek öğeler ağacında, kök dizini içinde alt dayanır. Projeye eklemek kullanılabilir öğeleri sağ bölmesinde dosyalardır **Yeni Öğe Ekle** iletişim kutusu.  
  
 Genellikle, bu klasör bir şablon HTML veya .cpp dosyası gibi projeniz için şablon dosyalarını ve sihirbazları başlatma herhangi .vsz dosyaları içerir. Öğelerin nasıl görüntüleneceğini denetlemek için dizin adlarını ve simgeler yerelleştirme için .vsdir dosyaları da içerebilir. Yeni Öğe Ekle iletişim kutusu ağaçtaki bu düğümün temsil ettiği iletişim kutusunda görüntülenen açıklamalı alt yazı yerelleştirilmiş dizesidir.  
  
 Bununla birlikte, her şeyi bir .vsdir dosyasında olması gerekmez. Dizindeki her öğe için bir .vsdir dosyası olabilir. Daha fazla bilgi için bkz: [Sihirbazı'nı (. Vsz) dosya](../../extensibility/internals/wizard-dot-vsz-file.md) ve [şablon dizin açıklaması (. Vsdir) dosyaları](../../extensibility/internals/template-directory-description-dot-vsdir-files.md).  
  
> [!NOTE]
>  Şablon dizinlerini .vsdir dosyalarında isteğe bağlıdır. Yeni bir proje öğesi dizinde yerleştirin ve içinde görüntülemek istiyorsanız **Yeni Öğe Ekle** iletişim kutusu, TemplatesDir deyiminde belirtilen şablonları dizininde bu dosyayı koyabilir. Dosyayı sağ bölmesinde sonra görüntülenir **Yeni Öğe Ekle** proje iletişim kutusu. Ancak, dosya veya bir simge için yerelleştirilmiş bir resim yazısı görüntülemek istiyorsanız, şablonları dizinde en az bir .vsdir dosyası içermelidir.  
  
## <a name="grouping-project-items"></a>Proje öğeleri gruplandırma  
 Şablon grupları klasörlerdeki içeren isteyip istemediğinizi **Yeni Öğe Ekle** iletişim kutusu ağacında, bunların içinde alt dizinler öğelerle kök şablonu dizininin altında olması gerekir. Zaman **Yeni Öğe Ekle** iletişim kutusu, kullanıcılara görüntülenir, bunlar ayrıca alt klasörleri görebilir ve bunları proje öğelerini seçebilirsiniz.  
  
 Bu şablon dizin ağacında diğer öğeleri ağaç düğümünün göre oluşturulacağı kod kesimi sıralama öncelik belirler. İçin **Yeni Öğe Ekle** iletişim kutusu, sıralama önceliktir eklemeniz gerekir ve böylece öğelerinizi doğru yerde iletişim kutusunda görüntülenen tüm.  
  
 Ayrıca uygulayabilirsiniz <xref:Microsoft.VisualStudio.Shell.Interop.IVsFilterAddProjectItemDlg2> ne görüntülenen filtrelemek için arabirimi **Yeni Öğe Ekle** iletişim kutusu. Bu arabirim uygulayarak 50 şablonu ve Sihirbazı dosyaları içerir, örneğin, disk üzerinde tek bir şablonda dizini ayarlayabilirsiniz. Bu şekilde, bir proje türü, başka bir proje türe ait bir 30 dosyaları ve genel bir proje türünde kullanılabilen tüm dosyaları ait 20 dosyalarla farklı proje türleri olabilir. Bağlı olarak hangi proje şablonu oluşturulur, bu şekilde, farklı bir şablon dosyaları kümesini görüntüleyebilirsiniz.  
  
 Örneğin, bir Visual Basic projesinde Web projeleri ve istemci projeler olabilir. Web forms istemci projesine eklemek için yararlı öğeleri değildir ve windows forms bir Web sunucusu projeye eklemek için yararlı öğeler değil. Bu nedenle, her iki proje türleri için tüm dosyaları içeren bir şablon dizin oluşturabilirsiniz. Ardından uygulayarak <xref:Microsoft.VisualStudio.Shell.Interop.IVsFilterAddProjectItemDlg2>, proje veya proje ayarları proje türüne göre gösterilmesi öğeleri gizleyebilirsiniz.  
  
## <a name="filtering-project-items"></a>Proje öğeleri filtreleme  
 `IVsFilterAddProjectItemDlg2` öğeleri ağaç (sol bölme) ve proje dosyalarını (sağ bölme), aşağıdaki yollarla filtreleme için sağlar:  
  
-   Yerelleştirilmiş adlar (.vsdir dosyasında yer alan iletişim kutusunda görüntülenen açıklamalı alt yazıları) tarafından sağlanan `IVsFilterAddProjectItemDlg`.  
  
-   Dosya ve klasörleri diskteki gerçek adlarını tarafından (yerelleştirilmemiş — herhangi bir .vsdir dosyası) tarafından sağlanan `IVsFilterAddProjectItemDlg`.  
  
-   Tarafından sağlanan kategoriye `IVsFilterAddProjectItemDlg2`.  
  
 Kategoriye göre filtre uygulamak için bir öğe .vsdir dosyasında "Web formu" gibi veya Visual Basic "istemci öğesi" kategorisi dizeye sağlar. İletişim kutusu kodu, ardından kategori sınıflandırma .vsdir dosyasından alır ve size geçirir. Uygulamanız için bu bilgileri geçirebilirsiniz `IVsFilterAddProjectItemDlg2` filtrelemek için **Yeni Öğe Ekle** kategorilere göre iletişim kutusu. Ayrıca, Web sayfaları için veya istemci Win32 uygulama çalışmaları olarak öğeleri filtre uygulayabilirsiniz. Ayrıca, tanımlayabilirsiniz [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] öğeleri Microsoft Foundation sınıfları (MFC) veya Etkin Şablon kitaplığı (ATL) öğeleri olarak etiketlenir. Bu öğeler tanımladığınızda, sistem kategorilerini ve sınıflandırmalarını göre filtrelenebilir proje sistemi kendi sınıflandırmaları tanımlayabilirsiniz.  
  
 Bu filtre işlevselliği uygularsanız, gizli her öğenin bir tablo eşleme gerekmez. Yalnızca türlerine öğelerini sınıflandırmak ve sınıflandırmalar .vsdir dosya veya dosyalar yerleştirin. Ardından, belirli bir sınıflandırmada arabirimi uygulayarak sahip öğelerden herhangi birini gizleyebilirsiniz. Bu şekilde, öğeleri yapabileceğiniz **Yeni Öğe Ekle** projedeki durumu iletişim kutusu dinamik temel.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFilterAddProjectItemDlg2>   
 [Proje ve öğe şablonları kaydediliyor](../../extensibility/internals/registering-project-and-item-templates.md)   
 [Genellikle projeleri genişletmek için kullanılan nesneler için CATIDs](../../extensibility/internals/catids-for-objects-that-are-typically-used-to-extend-projects.md)   
 [Proje ve proje öğesi şablonları ekleme](../../extensibility/internals/adding-project-and-project-item-templates.md)   
 [Şablon dizin açıklaması (. Vsdir) dosyaları](../../extensibility/internals/template-directory-description-dot-vsdir-files.md)   
 [Sihirbaz (.Vsz) Dosyası](../../extensibility/internals/wizard-dot-vsz-file.md)