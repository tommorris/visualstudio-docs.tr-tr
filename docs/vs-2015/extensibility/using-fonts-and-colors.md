---
title: Yazı tipleri ve renkler kullanarak | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- fonts, controlling in IDE
- IDE, controlling text color and fonts
- Fonts and Colors property page
- font and color control [Visual Studio SDK]
- text, IDE
ms.assetid: d1a9b99f-fbdc-45ed-920a-e08c3d931ac9
caps.latest.revision: 28
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 6db4f030a3367a5fd2fb449b3515643fe6cd6033
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42634208"
---
# <a name="using-fonts-and-colors"></a>Yazı tipleri ve renkler kullanma
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [kullanarak yazı tipleri ve renkler](https://docs.microsoft.com/visualstudio/extensibility/using-fonts-and-colors).  
  
[!INCLUDE[vsipsdk](../includes/vsipsdk-md.md)] Metni görüntülemek için yazı tiplerini ve renklerini kullanma desteği sağlar.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Yazı tipi ve renk genel bakış](../extensibility/font-and-color-overview.md)  
 Metin yazı tipi ve renk ayarları açıklanır [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] tümleşik geliştirme ortamı (IDE). Ayrıca kategorileri ve görüntü öğeleri kavramlar tanıtılır ve VSPackages ve çekirdek düzenleyici metin özniteliklerini kullanımını açıklar.  
  
 [Yazı tipi ve metin renklendirmesi için renk bilgilerini alma](../extensibility/getting-font-and-color-information-for-text-colorization.md)  
 Metin renklendirmesi yönetme Vspackage'larda uygulamak için kılavuz bilgiler verilmektedir **kategorileri** dışında **metin düzenleyici**.  
  
 [Saklı yazı tipi ve renk ayarlarını erişme](../extensibility/accessing-stored-font-and-color-settings.md)  
 Açıklar nasıl geçerli yazı tipi ve renk ayarları depolanan, alınan ve uygulanır.  
  
 [Uygulama özel kategoriler ve öğeleri görüntüleme](../extensibility/implementing-custom-categories-and-display-items.md)  
 Bir pencere oluşturabilir ve kullanmak, kendi temel adımlar açıklanmıştır **öğeleri görüntüle** ve **kategorileri** metin görüntülenmesini desteklemek için.  
  
 VSPackage'ı uygulamak bu yaklaşım gerektirir <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorDefaultsProvider> ve ilgili arabirim.  
  
 [Nasıl yapılır: yerleşik yazı tipi ve renk şeması erişim](../extensibility/how-to-access-the-built-in-fonts-and-color-scheme.md)  
 Tanımlamak ve bir kategori yerleşik yazı tipleri ve renkler kullanarak kaydetmek ve sistem tarafından sağlanan yazı tipleri ve renkler kullanımı başlatmak nasıl ele alınmaktadır.  
  
## <a name="reference"></a>Başvuru  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorDefaultsProvider>  
 Bir örneğini sağlar `IVsFontAndColorDefaults` veya <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorGroup> listelenen belirli bir öğe için karşılık gelen arabirimi **ayarları için Göster** listesinde **yazı tipleri ve renkler** sayfasının**Seçenekleri** iletişim kutusu.  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorDefaults>  
 IDE desteklemek bir VSPackage sağlayan **yazı tipleri ve renkler** varsayılan yazı tipleri ve renkler penceresi veya kullanıcı Arabirimi bileşeninin tanımlayarak sayfası.  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorGroup>  
 Kullandığı bir mekanizma sağlar, yazı tipi ve renk desteği, bir görüntü öğesi grubu - iki veya daha fazla kategori birleşimi temsil eden bir süper kategorisi belirtebilirsiniz sağlayan bir VSPackage'ı.  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage>  
 Yazı tipi ve renk verileri almak veya kayıt defterine kaydetmek bir VSPackage sağlar.  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorEvents>  
 Değişiklikler hakkında bilgi yazı tipi ve renk yazı tipi ve renk ayarlarını kullanan VSPackages bildirir.  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorUtilities>  
 Yöntemleri tarafından kullanılan giriş ve çıkış verilerle çalışmaya yönelik araçlar sağlar [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] **yazı tipi ve renk** mekanizması.  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorCacheManager>  
 Önbelleğe alma yazı tipi ve renk ayarlarını denetler.  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [Eski Dil Hizmeti Geliştirme](../extensibility/internals/developing-a-legacy-language-service.md)  
 VSPackage özelleştirmek için dil hizmetleri nasıl kullanabileceğinizi anlatır [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] Düzenleyici.  
  
 [Özel Düzenleyicilerde Söz Dizimi Renklendirmesi](../extensibility/syntax-coloring-in-custom-editors.md)  
 Descries nasıl [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] Düzenleyicisi söz dizimi renklendirmesi uygulamak için dil Hizmetleri kullanır.  
  
 [Visual Studio’nun Diğer Bölümlerini Genişletme](../extensibility/extending-other-parts-of-visual-studio.md)  
 Nasıl kullanılacağını açıklar [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] geri kalanını eşleşen kullanıcı Arabirimi öğeleri oluşturmak için Sertifika Hizmetleri'ni [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].

