---
title: Proje türleri dağıtma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- projects [Visual Studio SDK], managed-code
- projects [Visual Studio SDK], aggregator
ms.assetid: 7f132f67-8589-464c-90dc-0d57ae02aa8f
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 12af8607dd1561a4a2561cc688d2bb4ba0f07c88
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="deploying-project-types"></a>Proje türleri dağıtma
[!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] Yeni bir proje türü toplayıcısı (ProjectAggregator2.dll) ve aynı zamanda yeniden dağıtımı (ProjectAggregator2.msi) için bir Windows Installer paketi yükler. Yönetilen kod projesi türleri için yeni toplayıcısı kullanmanız gerekir. ProjectAggregator2 çalışır geçici çözüm sınırlamaları [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] yönetilen kod proje türleri doğru çalışmasını engelleyebilir toplayıcısı proje. Aşağıdaki adımlarda, yeni Toplayıcı'yı kullanmak için VSPackage değiştirmek anlatılmaktadır.  
  
1.  NativeHierarchyWrapper projeyi çözümünüzden kaldırın.  
  
2.  Herhangi bir NativeHierarchyWrapper ikili, kurulumdan kaldırın.  
  
3.  ProjectAggregator2.msi kurulumunuzu için ekleyin.