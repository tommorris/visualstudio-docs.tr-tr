---
title: Proje ve öğe şablonlarını kaydetme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- projects [Visual Studio SDK], adding items
- registry, Add New Item dialog box
- Add New Item dialog box
- Add New Project dialog box
- registry, Add New Project dialog box
ms.assetid: 6b909f93-d7f5-4aec-81c6-ee9ff0f31638
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: f3bc016a9c4b462c771db2cc98d1fd9493129278
ms.sourcegitcommit: f685fa5e2df9dc307bf1230dd9dc3288aaa408b5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36234046"
---
# <a name="registering-project-and-item-templates"></a>Proje ve Öğe Şablonlarını Kaydetme
Proje türleri kendi proje ve proje öğesi şablonları bulunduğu dizinleri kaydetmeniz gerekir. [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Proje türleri ile ilişkili tüm kayıt bilgileri göstermek üzere belirlemek için kullanır **Yeni Proje Ekle** ve **Yeni Öğe Ekle** iletişim kutuları.  
  
 Şablonlar hakkında daha fazla bilgi için bkz: [ekleme proje ve proje öğesi şablonları](../../extensibility/internals/adding-project-and-project-item-templates.md).  
  
## <a name="registry-entries-for-projects"></a>Projeler için kayıt defteri girdileri  
 Aşağıdaki örnekler HKEY_LOCAL_MACHINE\Software\Microsoft\VisualStudio altındaki kayıt defteri girişleri\\<*sürüm*>. Eşlik eden tablolar örneklerde kullanılan öğeleri açıklanır.  
  
```  
[Projects\{ProjectGUID}]  
@="MyProjectType"  
"DisplayName"="#2"  
"Package"="{VSPackageGUID}"  
"ProjectTemplatesDir"="C:\\MyProduct\\MyProjectTemplates"  
```  
  
|Ad|Tür|Açıklama|  
|----------|----------|-----------------|  
|@|REG_SZ|Bu tür projeleri varsayılan adı.|  
|Görünen adı|REG_SZ|Uydu DLL kaynak Kimliğinin adının altındaki paketlerin kayıtlı.|  
|Paket|REG_SZ|Sınıf kimliği paketin altında paketleri kayıtlı.|  
|ProjectTemplatesDir|REG_SZ|Proje şablonu dosyalarının varsayılan yolu. Proje şablonu dosyalar tarafından görüntülenen **yeni proje** şablonu.|  
  
### <a name="registering-item-templates"></a>Öğe şablonları kaydetme  
 Öğe şablonları depoladığınız dizin kaydetmeniz gerekir.  
  
```  
[Projects\{ProjectGUID}\AddItemTemplates\TemplateDirs\{VSPackageGUID}\1]  
@="#7"  
"TemplatesDir"="C:\\MyProduct\\MyProjectItemTemplates "  
"TemplatesLocalizedSubDir"="#10"  
"SortPriority"=dword:00000064  
```  
  
|Ad|Tür|Açıklama|  
|----------|----------|-----------------|  
|@|REG_SZ|Öğe Ekle şablonları için kaynak kimliği.|  
|TemplatesDir|REG_SZ|İletişim kutusunda görüntülenen proje öğeleri yolunu **Yeni Öğe Ekle** Sihirbazı.|  
|TemplatesLocalizedSubDir|REG_SZ|Kaynak Kimliği TemplatesDir alt adları bir dize, yerelleştirilmiş şablonları tutar. Çünkü [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] yükleri dize kaynağını Uydu DLL'leri bunları varsa, her uydu DLL farklı yerelleştirilmiş alt ad içerebilir.|  
|SortPriority|REG_DWORD|Ayarlama, şablonları görüntülenir sipariş yönetmek için SortPriority **Yeni Öğe Ekle** iletişim kutusu. Büyük SortPriority değerleri daha önce şablonu listede görüntülenir.|  
  
### <a name="registering-file-filters"></a>Dosya filtreleri kaydetme  
 İsteğe bağlı olarak, filtreleri kaydedebilirsiniz, [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] dosya adları için istediğinde kullanır. Örneğin, [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] filtre **Dosya Aç** iletişim kutusudur:  
  
 **Visual C# dosyalarını (\*.cs,\*.resx,\*.settings,\*.xsd,\*.wsdl);\*. cs,\*.resx,\*.settings,\*.xsd,\*.wsdl)**  
  
 Birden çok filtre kaydını desteklemek için her bir filtre HKEY_LOCAL_MACHINE\Software\Microsoft\VisualStudio altında kendi alt anahtarda kayıtlı\\<*sürüm*> \Projects\\{ \< *ProjectGUID*>} \Filters\\<*alt*>. Alt anahtar adı isteğe bağlıdır; [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] alt anahtarının adı yoksayar ve yalnızca kendi değerlerini kullanır.  
  
 Aşağıdaki tabloda gösterilen, bayrakları ayarlayarak bir filtre kullanıldığı bağlamları kontrol edebilirsiniz. Bir filtre ayarlamak bayrakları yoksa ortak filtreleri sonra listelenecektir **varolan öğeyi Ekle** iletişim kutusu ve **açık dosya** iletişim kutusu, ancak kullanılmaz içinde **dosyalarda Bul**  iletişim kutusu.  
  
```  
[Projects\{ProjectGUID}\Filters\MyLanguageFilter]  
@="#3"  
"CommonOpenFilesFilter"=dword:00000000  
"CommonFindFilesFilter"=dword:00000000  
"FindInFilesFilter"=dword:00000000  
"NotOpenFileFilter"=dword:00000000  
"NotAddExistingItemFilter"=dword:00000000  
"SortPriority"=dword:00000064  
```  
  
|Ad|Tür|Açıklama|  
|----------|----------|-----------------|  
|CommonFindFilesFilter|REG_DWORD|Filtreye ortak filtrelerden birini yapar **dosyalarda Bul** iletişim kutusu. Genel filtreler gibi ortak işaretlenmediği filtreleri önce Filtre listesinde listelenir.|  
|CommonOpenFilesFilter|REG_DWORD|Filtreye ortak filtrelerden birini yapar **Dosya Aç** iletişim kutusu. Genel filtreler gibi ortak işaretlenmediği filtreleri önce Filtre listesinde listelenir.|  
|FindInFilesFilter|REG_DWORD|Ortak filtreleri sonra filtre listeleri **dosyalarda Bul** iletişim kutusu.|  
|NotOpenFileFilter|REG_DWORD|Filtre olarak kullanılıp kullanılmadığını belirten **Dosya Aç** iletişim kutusu.|  
|NotAddExistingItemFilter|REG_DWORD|Filtre olarak kullanılıp kullanılmadığını belirten **varolan öğeyi Ekle** iletişim kutusu.|  
|SortPriority|REG_DWORD|Filtreler görüntülenen sipariş yönetmek için SortPriority ayarlayın. Büyük SortPriority değerleri önceki filtre listesinde görünür.|  
  
## <a name="directory-structure"></a>Dizin yapısı  
 Konumun aracılığıyla tümleşik geliştirme ortamı (IDE) kayıtlı olduğu sürece VSPackages şablon dosyaları ve klasörleri herhangi bir yerden bir yerel veya uzak diskte koyabilirsiniz. Ancak, kuruluş kolaylığı için aşağıdaki dizin yapısını ürününüzün yükleme yolu altında öneririz.  
  
 \Templates  
  
 \Projects (proje şablonları içerir)  
  
 \Applications  
  
 \Components  
  
 \ ...  
  
 \ProjectItems (proje öğeleri içerir)  
  
 \Class  
  
 \Form  
  
 \Web Sayfası  
  
 \HelperFiles (çok dosyalı proje öğelerinde kullanılan dosyaları içerir)  
  
 \WizardFiles  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Proje ve proje öğesi şablonları ekleme](../../extensibility/internals/adding-project-and-project-item-templates.md)   
 [Sihirbazlar](../../extensibility/internals/wizards.md)   
 [Uygulamaları yerelleştirme](../../ide/localizing-applications.md)   
 [Genişletme Projeleri için Genellikle Kullanılan Nesnelerin CATID’leri](../../extensibility/internals/catids-for-objects-that-are-typically-used-to-extend-projects.md)