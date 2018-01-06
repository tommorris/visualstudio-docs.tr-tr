---
title: "IDE tanımlı komutlar, menüler ve grupları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- commands, environment-defined
- .vsct files, environment-defined constants
- command groups, environment-defined
ms.assetid: 86b3af13-7163-48c6-986b-7beeedbc26cc
caps.latest.revision: "27"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 34e0e95475457e2a5f206ad4ecb0d7e42e2bb9ea
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="ide-defined-commands-menus-and-groups"></a>IDE tanımlı komutlar, menüler ve grupları
Birçok menüleri, komutları ve komut grubu zaten tarafından kullanılmak üzere tanımlanan [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE. Bu komutlar da, genişlettiğinizde kullanımınız için kullanılabilir. [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
## <a name="finding-environment-defined-commands"></a>Ortam tanımlı komutları bulma  
 Ortam komutları dört .vsct dosyaları kümesinde tanımlanmıştır:  
  
-   SharedCmdDef.vsct  
  
-   SharedCmdPlace.vsct  
  
-   ShellCmdDef.vsct  
  
-   ShellCmdPlace.vsct  
  
 Bu dosyalar bulunur  *\<Visual Studio SDK yükleme yolu >*\VisualStudioIntegration\Common\Inc\\. Bu dosyalar tanımları ve menüleri ve, VSPackage komutu tablosu (.vsct) yapılandırma dosyasında kapsayıcılar olarak kendi menüleri, gruplar ve komutlar için kullanabileceğiniz grupları GUID'lerini sağlar.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Visual Studio Menülerinin GUID’leri ve Kimlikleri](../../extensibility/internals/guids-and-ids-of-visual-studio-menus.md)  
 Visual Studio menü çubuğunda menüleri ve içerdikleri gruplarının GUID ve kimliği değerlerini sağlar.  
  
 [Visual Studio Araç Çubuklarının GUID’leri ve Kimlikleri](../../extensibility/internals/guids-and-ids-of-visual-studio-toolbars.md)  
 Visual Studio IDE içinde araç çubukları ve içerdikleri gruplarının GUID ve ID değerleri verir.  
  
 [Visual Studio Komutlarının GUID’leri ve Kimlikleri](../../extensibility/internals/guids-and-ids-of-visual-studio-commands.md)  
 Visual Studio IDE tarafından tanımlanan komutları GUID ve ID değerini verir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio komut tablosu (. Vsct) dosyaları](../../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)   
 [Proje sistemleri genişletme IDE tanımlı komutları](../../extensibility/internals/ide-defined-commands-for-extending-project-systems.md)   
 [VSPackage’ların Kullanıcı Arabirimi Öğeleri Eklemesi](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)