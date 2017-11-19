---
title: "Windows Installer ile VSPackage kaldırma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- packages, uninstalling
- VSPackages, uninstalling
- uninstalling VSPackages
ms.assetid: c4575ac7-82da-4af8-a375-ea756a101fbf
caps.latest.revision: "14"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 9b71c977fcc616c6d9cf30b78c9fd7610f11bcd4
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
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
>  `Installed`Windows Installer, VSPackage sistemde zaten yüklü olduğunu algıladığında ayarlar özelliğidir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Windows Installer](http://msdn.microsoft.com/en-us/187d8965-c79d-4ecb-8689-10930fa8b3b5)   
 [Sistem gereksinimleri algılama](../../extensibility/internals/detecting-system-requirements.md)