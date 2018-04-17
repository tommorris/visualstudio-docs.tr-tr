---
title: Windows Installer ile VSPackage kaldırma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- packages, uninstalling
- VSPackages, uninstalling
- uninstalling VSPackages
ms.assetid: c4575ac7-82da-4af8-a375-ea756a101fbf
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: d8a62692003b26afcd5b7814bdc03320fa1c453a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="uninstalling-a-vspackage-with-windows-installer"></a>Windows Installer ile VSPackage kaldırma
Çoğunlukla, Windows Installer, VSPackage yalnızca göre kaldırabilirsiniz ", VSPackage yüklemek için yaptığınız geri alma". Özel Eylemler ele [komutları olduğunu gerekir olması çalıştırmak sonra yükleme](../../extensibility/internals/commands-that-must-be-run-after-installation.md) bir kaldırma işleminden sonra çalıştırılmalıdır. Yükleme ve kaldırma olmadığı Installfinalize standart eylem hemen önce devenv.exe çağrıları gerçekleştirildiği için özel ve InstallExecuteSequence tablosu girdileri her iki durumda hizmet.  
  
> [!NOTE]
>  Çalıştırma `devenv /setup` MSI paketini kaldırdıktan sonra.  
  
 Windows Installer paketini özel eylemler eklerseniz, genel bir kural olarak, bu eylemleri kaldırma ve geri alma sırasında işlemelidir. Örneğin, VSPackage kendi kendine kaydettirmek için özel eylemler eklerseniz, çok kaydını silmek için özel eylemler eklemeniz gerekir.  
  
> [!NOTE]
>  Bir kullanıcı, VSPackage yükleyip sürümlerini kaldırmanız mümkündür [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ile hangi tümleşiktir. Bağımlılıklar koduyla çalıştıracağınız özel eylemler ortadan kaldırarak VSPackage'nın kaldırma işlemini bu senaryoda çalıştığından emin olun yardımcı [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
## <a name="handling-launch-conditions-at-uninstall-time"></a>İşleme başlatma koşulları adresindeki kaldırması  
 Hata göstermek için LaunchCondition tablonun satırlarını LaunchConditions standart işlemi okur koşullar karşılanmazsa iletileri. Başlatma koşulları genellikle sistem gereksinimleri karşılandıktan, koşul ekleyerek başlatma koşulları kaldırma sırasında genellikle atlayabilirsiniz emin olmak için kullanılan gibi `NOT Installed`, LaunchCondition tablosunun LaunchConditions satır.  
  
 Alternatif eklemektir `OR Installed` kaldırma sırasında önemli olmayan koşullar başlatmak için. Koşul kaldırma sırasında her zaman true olur ve bu nedenle başlatma koşulu hata iletisi görüntülenmez sağlar.  
  
> [!NOTE]
>  `Installed` Windows Installer, VSPackage sistemde zaten yüklü olduğunu algıladığında ayarlar özelliğidir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Windows Installer](http://msdn.microsoft.com/en-us/187d8965-c79d-4ecb-8689-10930fa8b3b5)   
 [Sistem Gereksinimlerini Algılama](../../extensibility/internals/detecting-system-requirements.md)