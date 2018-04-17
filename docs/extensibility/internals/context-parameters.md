---
title: Bağlam parametreleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- wizards, context parameters
- context parameters
ms.assetid: 1a062dcb-8a8f-40dd-bea9-3d10f9448966
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: cb6646e917b4cb94b4cd0534b513d148490cf69d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="context-parameters"></a>Bağlam parametreleri
İçinde [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] tümleşik geliştirme ortamı (IDE), sihirbazlara ekleyebilirsiniz **yeni proje**, **Yeni Öğe Ekle**, veya **alt proje Ekle** iletişim kutuları. Eklenen sihirbazları kullanılabilir **dosya** menüsü veya bir projeye sağ tıklanarak **Çözüm Gezgini**. IDE bağlam parametreleri Sihirbazı'nın kullanımla geçirir. IDE sihirbaz çağırdığında bağlam parametreleri proje durumunu tanımlayın.  
  
 IDE ayarlayarak sihirbazları başlatır <xref:Microsoft.VisualStudio.Shell.Interop.VSADDITEMOPERATION> IDE'nin çağrısına bayrağı <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3.AddItem%2A> projesi için yöntemi. Ayarlandığında, proje neden gerekir `IVsExtensibility::RunWizardFile` kayıtlı sihirbaz adı veya GUID ve IDE aktardığı diğer bağlam parametreleri kullanarak yürütülecek yöntemi.  
  
## <a name="context-parameters-for-new-project"></a>Yeni proje için bağlam parametreleri  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`WizardType`|Kayıtlı sihirbaz türü (<xref:EnvDTE.Constants.vsWizardNewProject>) veya Sihirbazı türünü gösterir GUID. İçinde [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] , sihirbazın GUID uygulamasıdır {0F90E1D0-4999-11D1-B6D1-00A0C90F2744}.|  
|`ProjectName`|Benzersiz bir dizeye [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] proje adı.|  
|`LocalDirectory`|Proje dosyaları çalışma yerel bir konum.|  
|`InstallationDirectory`|Dizin yolu [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] yükleme.|  
|`FExclusive`|Proje Aç çözümleri kapatmalısınız gösteren Boole bayrak.|  
|`SolutionName`|Dizin bölümü veya .sln dosya adı uzantısı olmadan çözüm dosyasının adı. .Suo dosya adı da kullanılarak oluşturulan `SolutionName`. Bu bağımsız değişken boş bir dize olmadığı durumlarda, sihirbaz kullanır <xref:EnvDTE._Solution.Create%2A> projeyle eklemeden önce <xref:EnvDTE._Solution.AddFromTemplate%2A>. Bu adı boş bir dize ise, kullanın <xref:EnvDTE._Solution.AddFromTemplate%2A> çağırmadan <xref:EnvDTE._Solution.Create%2A>.|  
|`Silent`|Sihirbaz sessiz bir şekilde çalıştırılması gerekip gerekmediğini belirten Boole değeri gibi **son** tıklattınız (`TRUE`).|  
  
## <a name="context-parameters-for-add-new-item"></a>Bağlam parametreleri için Yeni Öğe Ekle  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`WizardType`|Kayıtlı sihirbaz türü (<xref:EnvDTE.Constants.vsWizardAddItem>) veya Sihirbazı türünü gösterir GUID. İçinde [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] , sihirbazın GUID uygulamasıdır {0F90E1D1-4999-11D1-B6D1-00A0C90F2744}.|  
|`ProjectName`|Benzersiz bir dizeye [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] proje adı.|  
|`ProjectItems`|Çalışma proje dosyalarını içeren yerel bir konum.|  
|`ItemName`|Eklenecek öğenin adı. Varsayılan dosya adı veya gelen kullanıcı türleri dosya adı bu adıdır **öğeleri Ekle** iletişim kutusu. Ad .vsdir dosyasında ayarlanan bayrakları temel alır. Ad boş bir değer olabilir.|  
|`InstallationDirectory`|Dizin yolu [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] yükleme.|  
|`Silent`|Sihirbaz sessiz bir şekilde çalıştırılması gerekip gerekmediğini belirten Boole değeri gibi **son** tıklattınız (`TRUE`).|  
  
## <a name="context-parameters-for-add-sub-project"></a>Bağlam parametreleri ekleme alt proje için  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`WizardType`|Kayıtlı sihirbaz türü (<xref:EnvDTE.Constants.vsWizardAddSubProject>) veya Sihirbazı türünü gösterir GUID. İçinde [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] , sihirbazın GUID uygulamasıdır {0F90E1D2-4999-11D1-B6D1-00A0C90F2744}.|  
|`ProjectName`|Benzersiz bir dizeye [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] proje adı.|  
|`ProjectItems`|İşaretçi `ProjectItems` sihirbaz faaliyet koleksiyonu. Bu işaretçinin proje hiyerarşisi seçimine göre Sihirbazı'nı geçirilir. Bir kullanıcı genellikle öğesi yerleştirileceği klasörü seçer ve ardından projenin çağırır **Öğe Ekle** iletişim kutusu.|  
|`LocalDirectory`|Proje dosyaları çalışma yerel bir konum.|  
|`ItemName`|Eklenecek öğenin adı. Varsayılan dosya adı veya gelen kullanıcı türleri dosya adı bu adıdır **öğeleri Ekle** iletişim kutusu. Ad .vsdir dosyasında ayarlanan bayrakları temel alır. Ad boş bir değer olabilir.|  
|`InstallationDirectory`|Dizin yolu [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] yükleme.|  
|`Silent`|Sihirbaz sessiz bir şekilde çalıştırılması gerekip gerekmediğini belirten Boole değeri gibi **son** tıklattınız (`TRUE`).|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject2>   
 [Özel Parametreler](../../extensibility/internals/custom-parameters.md)   
 [Sihirbazlar](../../extensibility/internals/wizards.md)   
 [Sihirbazı'nı (. Vsz) dosyası](../../extensibility/internals/wizard-dot-vsz-file.md)   
 [Sihirbazlar başlatmak için bağlam parametreleri](http://msdn.microsoft.com/Library/051a10f4-9e45-4604-b344-123044f33a24)