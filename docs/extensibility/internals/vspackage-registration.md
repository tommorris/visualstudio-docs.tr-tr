---
title: VSPackage kayıt | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- registration, VSPackages
- VSPackages, registering
ms.assetid: ecd20da8-b04b-4141-a8f4-a2ef91dd597a
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 348010982b015eaf19ba4de559eca66bb24930a3
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="vspackage-registration"></a>VSPackage kayıt
Gereken VSPackages bildirmek [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] yüklenir ve gereken yüklü. Bu işlem, kayıt defterinde bilgi yazarak gerçekleştirilir. Tipik bir işi yükleyicinin olmasıdır.  
  
> [!NOTE]
>  Bu, kendi kendine kayıt kullanılacak VSPackage geliştirme sırasında kabul edilen bir uygulama olur. Ancak, [!INCLUDE[vsipprvsip](../../extensibility/includes/vsipprvsip_md.md)] iş ortakları kendi kendine kayıt kurulumunun bir parçası kullanarak ürünlerini sevk olamaz.  
  
 Bir Windows Installer paketi kayıt defteri girişleri kayıt defteri tablosunda genellikle yapılır. Dosya uzantıları kayıt defteri tabloda da kaydedebilirsiniz. Ancak, Windows Installer program tanıtıcısı (ProgID), sınıf, uzantı ve fiil tabloları yerleşik destek sağlar. Daha fazla bilgi için bkz: [veritabanı tabloları](http://msdn.microsoft.com/library/aa368259\(VS.85\).aspx).  
  
 Kayıt defteri girdileri seçilen yan tarafında stratejiniz için uygun olan bileşeni ile ilişkili olduğundan emin olun. Örneğin, paylaşılan bir dosya için kayıt defteri girişleri, dosyanın Windows Installer bileşeni ile ilişkili olmalıdır. Benzer şekilde, bir sürüme özgü dosya için kayıt defteri girdileri dosyanın bileşeni ile ilişkili olmalıdır. Aksi takdirde, yükleme veya bir sürümü için VSPackage kaldırma [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] , VSPackage diğer sürümlerde bozar. Daha fazla bilgi için bkz: [Visual Studio, birden çok sürümleri destekleme](../../extensibility/supporting-multiple-versions-of-visual-studio.md)  
  
> [!NOTE]
>  Kayıt yönetmek için en kolay yolu aynı verileri aynı dosyaların Geliştirici kayıt ve yükleme zamanı kayıt için kullanmaktır. Örneğin, bazı yükleyici geliştirme araçları .reg biçiminde dosya derleme zamanında kullanmasını sağlayabilirsiniz. Geliştiriciler kendi günlük geliştirme .reg dosyalarını korur ve hata ayıklama, aynı dosyalar Yükleyicisi'nde otomatik olarak dahil edilebilir değilse. Kayıt verileri otomatik olarak paylaşamazsınız, kayıt verileri Yükleyicisi'nin kopyasını geçerli olduğundan emin olmalısınız.  
  
## <a name="registering-unmanaged-vspackages"></a>Yönetilmeyen VSPackages kaydetme  
 Yönetilmeyen VSPackages (Visual Studio Paketi şablonu tarafından oluşturulan dahil olmak üzere), kayıt bilgileri depolamak için ATL stil .rgs dosyaları kullanın. .Rgs dosya biçimi için ATL özel ve genel olarak kullanılamaz-yazma aracı yüklemesi tarafından olabilir. Kayıt bilgileri VSPackage Yükleyicisi için ayrı olarak korunmalıdır. Örneğin, geliştiricilerin dosyaları .reg biçiminde .rgs ile senkronize dosya değişiklikleri kullanmaya devam edebilir. .Reg dosyalarını geliştirme çalışması için RegEdit ile birleştirilmiş veya bir yükleyici tarafından tüketilen.  
  
## <a name="registering-managed-vspackages"></a>Yönetilen VSPackages kaydetme  
 RegPkg aracı kayıt öznitelikleri yönetilen bir VSPackage okur ve ya da doğrudan bir yükleyici tarafından kullanılabilecek yazma .reg biçimi dosyaları ve kayıt defteri için bilgiler yazabilir.  
  
> [!NOTE]
>  RegPkg Aracı'nı yeniden dağıtılabilir değil ve bir kullanıcının sisteminde VSPackage kaydetmek için kullanılamaz.  
  
## <a name="why-vspackages-should-not-self-register-at-install-time"></a>Neden VSPackages yükleme zamanında kendi kendine kayıt  
 VSPackage yükleyicileri kendi kendine kayıt üzerinde güvenmemelisiniz. İlk bakışta, yalnızca VSPackage içinde kendisi VSPackage'nın kayıt defteri değerleri tutmak iyi bir fikir gibi görünüyor. Verilen geliştiricilerin rutin çalışmaları için kayıt defteri değerlerini gerekir ve test, kayıt defteri verilerini yükleyici, ayrı bir kopyasını koruyarak önlemek için mantıklıdır. Yükleyici, kayıt defteri değerlerini yazmak için VSPackage üzerinde kendisini güvenebilirsiniz.  
  
 Teorik iyi, kendi kendine kayıt VSPackage yükleme için uygun hale birkaç açıkları vardır:  
  
-   Yükleme, kaldırma işlemi, yüklemeyi geri alma ve kaldırma işlemini geri alma doğru destekleyen RegPkg çağırarak Self kaydeder her yönetilen VSPackage için dört özel eylemler Yazar gerektirir.  
  
-   Yan yana desteklemek için bir yaklaşım, desteklenen her sürümü için RegSvr32 veya RegPkg çağırma dört özel eylemler Yazar gerektirebilir [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
-   Geri Self kayıtlı anahtarları başka bir özellik veya uygulama tarafından kullanılan varsa söyleyen hiçbir şekilde olduğundan bir yükleme otomatik olarak kayıtlı modülleri ile güvenli bir şekilde alınamaz.  
  
-   Kendi kendine kayıtlı DLL'leri bazen yok ya da yanlış sürüme yardımcı DLL'leri bağlayın. Buna karşılık, Windows Installer DLL'leri sisteminin geçerli durumunu hiçbir bağımlılık ile kayıt tabloları kullanarak kaydedebilirsiniz.  
  
-   Kendi kendine kayıt kodu tür kitaplıklarının gibi ağ kaynaklarına erişim bir bileşen olan hem kaynaktan Çalıştır belirtilmişse ve kendi kendini kaydetme tabloda listelenen engellenebilir. Bu yönetim yüklemesi sırasında başarısız olmasına bileşeninin yüklenmesi neden olabilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Windows Installer](http://msdn.microsoft.com/library/cc185688\(VS.85\).aspx)   
 [Yönetilen paketi kaydı](http://msdn.microsoft.com/en-us/f69e0ea3-6a92-4639-8ca9-4c9c210e58a1)