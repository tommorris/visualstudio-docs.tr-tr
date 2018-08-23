---
title: Proje türlerini dağıtma | Microsoft Docs
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
- projects [Visual Studio SDK], managed-code
- projects [Visual Studio SDK], aggregator
ms.assetid: 7f132f67-8589-464c-90dc-0d57ae02aa8f
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 66069ac71fbe59e8b63126d66d2a0cc63ed095bc
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42697166"
---
# <a name="deploying-project-types"></a>Proje Türlerini Dağıtma
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [proje türlerini dağıtma](https://docs.microsoft.com/visualstudio/extensibility/internals/deploying-project-types).  
  
[!INCLUDE[vsipsdk](../../includes/vsipsdk-md.md)] Yeni bir proje türü toplayıcısı (ProjectAggregator2.dll) ve ayrıca yeniden dağıtımı (ProjectAggregator2.msi) için bir Windows Installer paketi yükler. Yönetilen kod proje türleri için yeni Toplayıcısı'nı kullanmanız gerekir. ProjectAggregator2 çalışır geçici çözüm sınırlamaları [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] yönetilen kod proje türleri düzgün çalışmasını engelleyen toplayıcısı proje. Aşağıdaki adımlar, yeni Toplayıcı'yı kullanmak için VSPackage değiştirmek açıklanmaktadır.  
  
1.  NativeHierarchyWrapper proje çözümünüzden kaldırın.  
  
2.  Herhangi bir NativeHierarchyWrapper ikili kurulumunuzu kaldırın.  
  
3.  ProjectAggregator2.msi kurulumunuzu ekleyin.

