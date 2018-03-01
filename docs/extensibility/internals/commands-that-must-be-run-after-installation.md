---
title: "Yükleme sonrasında çalışan komutlar | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- post-install commands
ms.assetid: c9601f2e-2c6e-4da9-9a6e-e707319b39e2
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 2ff4b1e572fd1e0c5c500fbd756d01063665bd1f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="commands-that-must-be-run-after-installation"></a>Yükleme sonrasında çalışan komutlar
Dahili bir .msi dosyası aracılığıyla dağıtırsanız, çalıştırmalısınız `devenv /setup` yüklemenizi uzantılarınızın bulmak Visual Studio için sırayla bir parçası olarak.  
  
> [!NOTE]
>  Bu konu başlığı altındaki bilgiler, Visual Studio 2008 ve daha önce DevEnv bulma için geçerlidir. Visual Studio'nun daha yeni sürümleriyle DevEnv bulma hakkında daha fazla bilgi için bkz: [algılama sistem gereksinimleri](../../extensibility/internals/detecting-system-requirements.md).  
  
## <a name="finding-devenvexe"></a>Devenv.exe bulma  
 Her sürümün bulabilir devenv.exe kayıt defteri değerleri [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] yükleyicileri yazma, kayıt defteri değerlerini özellikleri olarak depolamak için RegLocator tablosu ve AppSearch tablosu kullanma. Daha fazla bilgi için bkz: [algılama sistem gereksinimleri](../../extensibility/internals/detecting-system-requirements.md).  
  
### <a name="reglocator-table-rows-to-locate-devenvexe-from-different-versions-of-visual-studio"></a>Visual Studio farklı sürümlerine Devenv.exe bulmak için RegLocator tablo satırları  
  
|Signature_|kök|Anahtar|Ad|Tür|  
|-----------------|----------|---------|----------|----------|  
|RL_DevenvExe_2002|2|SOFTWARE\Microsoft\VisualStudio\7.0\Setup\VS|EnvironmentPath|2|  
|RL_DevenvExe_2003|2|SOFTWARE\Microsoft\VisualStudio\7.1\Setup\VS|EnvironmentPath|2|  
|RL_DevenvExe_2005|2|SOFTWARE\Microsoft\VisualStudio\8.0\Setup\VS|EnvironmentPath|2|  
|RL_DevenvExe_2008|2|SOFTWARE\Microsoft\VisualStudio\9.0\Setup\VS|EnvironmentPath|2|  
  
### <a name="appsearch-table-rows-for-corresponding-reglocator-table-rows"></a>Karşılık gelen RegLocator tablo satır için AppSearch tablo satırları  
  
|Özellik|Signature_|  
|--------------|-----------------|  
|DEVENV_EXE_2002|RL_DevenvExe_2002|  
|DEVENV_EXE_2003|RL_DevenvExe_2003|  
|DEVENV_EXE_2005|RL_DevenvExe_2005|  
|DEVENV_EXE_2008|RL_DevenvExe_2008|  
  
 Örneğin, Visual Studio yükleyicisi kayıt defteri değeri Yazar **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\9.0\Setup\VS\EnvironmentPath** olarak **C:\VS2008\Common7\IDE\devenv.exe**, tam yolunu yürütülebilir yükleyici çalıştırmanız gerekir.  
  
 **Not** RegLocator türü sütun 2 olduğundan imza tabloda ek sürüm bilgilerini belirtmek ise gerekli değildir.  
  
## <a name="running-devenvexe"></a>Çalışan devenv.exe  
 Standart eylem yükleyicisinde çalıştırır AppSearch sonra AppSearch tablodaki her bir özellik için Visual Studio ilgili sürümü devenv.exe dosyasına işaret eden bir değer içeriyor. Belirtilen kayıt defteri değerleri mevcut olup olmadığını — Visual Studio'nun bu sürümü yüklü olmadığından — belirtilen özellik kümesi null.  
  
 Bir özellik işaret ettiği bir yürütülebilir dosya özel eylemi üzerinden çalışan Windows Installer destekler 50 yazın. Özel eylem, komut dosyası yürütme seçeneklerini, msidbCustomActionTypeInScript (1024) ve msidbCustomActionTypeCommit (512) VSPackage başarıyla içine tümleştirme önce yüklendiğinden emin olmak için içermelidir [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. Daha fazla bilgi için bkz: özel tablo ve özel eylem, komut dosyası yürütme seçenekleri.  
  
 Özel Eylemler türü 50 kaynak sütunun değeri ve komut satırı bağımsız değişkenleri hedef sütun olarak çalıştırılabilir içeren özelliğini belirtin.  
  
### <a name="customaction-table-rows-to-run-devenvexe"></a>Özel tablo satırları Devenv.exe çalıştırmak için  
  
|Eylem|Tür|Kaynak|Hedef|  
|------------|----------|------------|------------|  
|CA_RunDevenv2002|1586|DEVENV_EXE_2002|/ Setup|  
|CA_RunDevenv2003|1586|DEVENV_EXE_2003|/ Setup|  
|CA_RunDevenv2005|1586|DEVENV_EXE_2005|/ Setup|  
|CA_RunDevenv2008|1586|DEVENV_EXE_2008|/ Setup|  
  
 Özel Eylemler, bunları yükleme sırasında yürütülmek zamanlamak için InstallExecuteSequence tablosuna yazılan gerekir. Bu, çalıştırılan özel eylemin engellemek için koşul sütunundaki her satır bir karşılık gelen özellik kullanın sürümü [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] sistemde yüklü değil.  
  
> [!NOTE]
>  `Null`özellikleri değerlendirmek için `False` koşullarında kullanıldığında.  
  
 Her özel eylem için dizisi sütunun değeri, Windows Installer paketi diğer sırası değerleri bağlıdır. Farklı Çalıştır devenv.exe özel eylemler olmadığı Installfinalize standart eylem hemen önce mümkün olduğunca kapatın, sırası değerleri olmalıdır.  
  
### <a name="installexecutesequence-table-to-schedule-the-devenvexe-custom-actions"></a>InstallExecuteSequence tablo devenv.exe özel eylemler zamanlamak için  
  
|Eylem|Koşul|Sırası|  
|------------|---------------|--------------|  
|CA_RunDevenv2002|DEVENV_EXE_2002|6602|  
|CA_RunDevenv2003|DEVENV_EXE_2003|6603|  
|CA_RunDevenv2005|DEVENV_EXE_2005|6605|  
|CA_RunDevenv2008|DEVENV_EXE_2008|6608|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Windows Installer ile VSPackage Yükleme](../../extensibility/internals/installing-vspackages-with-windows-installer.md)