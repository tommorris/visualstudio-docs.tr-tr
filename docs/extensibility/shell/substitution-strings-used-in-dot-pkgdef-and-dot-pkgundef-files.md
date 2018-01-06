---
title: "Kullanılan değiştirme dizeleri. Pkgdef ve. Pkgundef dosyaları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Visual Studio shell, isolated mode, .pkgdef and .pkgundef files
ms.assetid: b1755d63-d794-4fd7-864b-70a9684881c2
caps.latest.revision: "4"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 0405e18419baf8bc152331a2bcfc7254ec602d1b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="substitution-strings-used-in-pkgdef-and-pkgundef-files"></a>Kullanılan değiştirme dizeleri. Pkgdef ve. Pkgundef dosyaları
Visual Studio için tanımladığınız .pkgundef dosyaları Kabuk uygulama yalıtılmış ve .pkgdef aşağıda listelenen değiştirme dizelerini kullanabilirsiniz.  
  
## <a name="substitution-strings"></a>Değiştirme dizeleri  
  
|Dize|Açıklama|  
|------------|-----------------|  
|$=*RegistryEntry*$|Değeri *RegistryEntry* girişi. Kayıt defteri girişi dizesi bir ters eğik çizgiyi ererse (\\), kayıt defteri alt anahtarı varsayılan değeri kullanılır. Örneğin, değiştirme dizesi $$ geçerli kullanıcının geçici klasöre genişletilmiş HKEY_CURRENT_USER\Environment\TEMP =.|  
|$AppName$|AppEnv.dll Giriş noktalarının geçirilen uygulamanın tam adı. Uygulama adı, alt çizgi ve ayrıca proje .pkgdef dosyasında ThisVersionDTECLSID ayarının değeri olarak kayıtlı uygulama Otomasyon nesnesinin sınıfı tanımlayıcısı (CLSID), tam adı oluşur.|  
|$AppDataLocalFolder|Bu uygulama için LOCALAPPDATA % altında alt.|  
|$BaseInstallDir$|Visual Studio yüklendiği konumun tam yolu.|  
|$CommonFiles$|% CommonProgramFiles % ortam değişkeni değeri.|  
|$MyDocuments$|Geçerli kullanıcının Belgelerim klasörünü tam yolu.|  
|$PackageFolder$|Uygulama için paket derleme dosyalarını içeren dizinin tam yolu.|  
|$ProgramFiles$|% ProgramFiles % ortam değişkeni değeri.|  
|$RootFolder$|Uygulama kök dizininin tam yolu.|  
|$RootKey$|Uygulama için kök kayıt defteri anahtarı. Varsayılan olarak kök HKEY_CURRENT_USER\Software içinde olduğu\\*ŞirketAdı*\\*ProjectName*\\*VersionNumber* (zaman "uygulamasını çalıştıran, bu anahtar için _Config eklenir). RegistryRoot değeri tarafından ayarlanan *SolutionName*.pkgdef dosya.<br /><br /> $RootKey$ dizesi uygulama alt anahtarı altındaki kayıt defteri değeri almak için kullanılabilir. Örneğin, dize "$= $RootKey \AppIcon$" uygulama kök alt anahtarı altında AppIcon girdisinin değeri döndürür.<br /><br /> Ayrıştırıcının .pkgdef dosya sırayla işler ve yalnızca giriş önceden tanımlanmışsa uygulama alt anahtarı altında bir kayıt defteri girdisini erişebilirsiniz|  
|$ShellFolder$|Visual Studio yüklendiği konumun tam yolu.|  
|$System$|Windows\system32 klasöründe.|  
|$WINDIR$|Windows klasörü.|  
  
 Ayrıştırıcının değiştirme dizesi tanımıyor veya bir kayıt defteri girdisi veya bir ortam değişkeni değeri belirlenemiyor, ardından bunu değiştirme dizesi, bir parçası gerçekleştirmez.