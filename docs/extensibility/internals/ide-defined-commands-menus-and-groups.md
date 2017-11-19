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
ms.openlocfilehash: 032baaa57dd91cb07eac547da810d16e708f0828
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
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
 [GUID ve Visual Studio menü kimlikleri](../../extensibility/internals/guids-and-ids-of-visual-studio-menus.md)  
 Visual Studio menü çubuğunda menüleri ve içerdikleri gruplarının GUID ve kimliği değerlerini sağlar.  
  
 [GUID ve Visual Studio araç çubukları kimlikleri](../../extensibility/internals/guids-and-ids-of-visual-studio-toolbars.md)  
 Visual Studio IDE içinde araç çubukları ve içerdikleri gruplarının GUID ve ID değerleri verir.  
  
 [GUID ve Visual Studio komut kimlikleri](../../extensibility/internals/guids-and-ids-of-visual-studio-commands.md)  
 Visual Studio IDE tarafından tanımlanan komutları GUID ve ID değerini verir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio komut tablosu (. Vsct) dosyaları](../../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)   
 [Proje sistemleri genişletme IDE tanımlı komutları](../../extensibility/internals/ide-defined-commands-for-extending-project-systems.md)   
 [Kullanıcı arabirimi öğeleri VSPackages nasıl eklenir](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)