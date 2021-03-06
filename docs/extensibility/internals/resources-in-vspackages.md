---
title: VSPackages kaynaklarında | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- managed VSPackages, resources in
- resources, managed VSPackages
- VSPackages, managed resources
ms.assetid: cc8c17a6-b190-4856-b001-0c1104f104b2
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: d252f61a9f634f4bb8435626c41c586bbe5cb839
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31130962"
---
# <a name="resources-in-vspackages"></a>VSPackages kaynakları
Yerelleştirilmiş kaynaklar yerel uydu UI DLL'ler, yönetilen Uydu DLL'leri veya bir yönetilen VSPackage eklenebilir.  
  
 Bazı kaynaklar VSPackages içinde katıştırılmış olamaz. Aşağıdaki yönetilen türler katıştırılabilen:  
  
-   Dizeler  
  
-   (Ayrıca dizelerdir) paket yükleme tuşları  
  
-   Araç penceresi simgeleri  
  
-   Derlenmiş komutu tablo çıkış (Teknolojiden) dosyaları  
  
-   Teknolojiden bit eşlemler  
  
-   Komut satırı Yardımı  
  
-   İletişim kutusu verileri hakkında  
  
 Yönetilen bir paketteki kaynakları kaynak kimliğine göre seçilir Bir özel durum CTMENU adlandırılmalıdır Teknolojiden dosyasıdır. Teknolojiden dosya kaynak tablo olarak görünmelidir bir `byte[]`. Diğer tüm kaynak öğeleri türüne göre tanımlanır.  
  
 Kullanabileceğiniz <xref:Microsoft.VisualStudio.Shell.PackageRegistrationAttribute> belirtmek için öznitelik [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] yönetilen kaynaklar kullanılabilir.  
  
 [!code-csharp[VSSDKResources#1](../../extensibility/internals/codesnippet/CSharp/resources-in-vspackages_1.cs)]
 [!code-vb[VSSDKResources#1](../../extensibility/internals/codesnippet/VisualBasic/resources-in-vspackages_1.vb)]  
  
 Ayarı <xref:Microsoft.VisualStudio.Shell.PackageRegistrationAttribute> bu şekilde belirten [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] kaynaklar için örneğin, kullanarak aradığında onunla yönetilmeyen Uydu DLL'leri yok saymanız gerekir <xref:Microsoft.VisualStudio.Shell.Interop.IVsShell.LoadPackageString%2A>. Varsa [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] aynı kaynak Kimliğine sahip iki veya daha fazla kaynak karşılaştığında bulduğu ilk kaynak kullanır.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir araç penceresi simgesini yönetilen gösterimidir.  
  
```  
<data name="1001"  
type="System.Resources.ResXFileRef,System.Windows.Forms">  
     <value>  
     MyToolWinIcon.bmp;  
     System.Drawing.Bitmap,  
     System.Drawing,  
     Version=1.0.0.0,  
     Culture=neutral,  
     PublicKeyToken=b03f5f7f11d50a3a  
     </value>  
</data>  
```  
  
 Aşağıdaki örnek, CTMENU adlandırılmalıdır Teknolojiden bayt dizisi katıştırmak gösterilmiştir.  
  
```  
<data name="CTMENU"  
type="System.Resources.ResXFileRef,System.Windows.Forms">  
     <value>  
     MyPackage.cto;  
     System.Byte[],  
     mscorlib,  
     Version=1.0.0.0,  
     Culture=neutral,  
     PublicKeyToken=b03f5f7f11d50a3a  
     </value>  
</data>  
```  
  
## <a name="implementation-notes"></a>Uygulama Notları  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] mümkün olduğunda VSPackages yüklenmesini gecikmeler. Bir VSPackage Teknolojiden dosya katıştırma bir sonuç [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] böyle VSPackages bellekte bir birleştirilmiş komutu tablosu oluşturduğunda, Kurulum sırasında yüklemeniz gerekir. Kaynaklar meta veriler VSPackage kod çalıştırmadan inceleyerek VSPackage ayıklanabilir. Performans kaybı en az olacak şekilde VSPackage şu anda başlatılamadı.  
  
 Zaman [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] VSPackage Kur tamamlandıktan sonra kaynak isteği, bu paket zaten yüklenmiş ve başlatılmış, olası performans kaybı en az olacak şekilde.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [VSPackages yönetme](../../extensibility/managing-vspackages.md)   
 [MFC Uygulamalarında Yerelleştirilmiş Kaynaklar: Uydu DLL'leri](/cpp/build/localized-resources-in-mfc-applications-satellite-dlls)   
