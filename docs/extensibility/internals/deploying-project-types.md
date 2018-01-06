---
title: "Proje türleri dağıtma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- projects [Visual Studio SDK], managed-code
- projects [Visual Studio SDK], aggregator
ms.assetid: 7f132f67-8589-464c-90dc-0d57ae02aa8f
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 2171a940951d828df358d09dae5fec68b6475e4d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="deploying-project-types"></a>Proje türleri dağıtma
[!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)]Yeni bir proje türü toplayıcısı (ProjectAggregator2.dll) ve aynı zamanda yeniden dağıtımı (ProjectAggregator2.msi) için bir Windows Installer paketi yükler. Yönetilen kod projesi türleri için yeni toplayıcısı kullanmanız gerekir. ProjectAggregator2 çalışır geçici çözüm sınırlamaları [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] yönetilen kod proje türleri doğru çalışmasını engelleyebilir toplayıcısı proje. Aşağıdaki adımlarda, yeni Toplayıcı'yı kullanmak için VSPackage değiştirmek anlatılmaktadır.  
  
1.  NativeHierarchyWrapper projeyi çözümünüzden kaldırın.  
  
2.  Herhangi bir NativeHierarchyWrapper ikili, kurulumdan kaldırın.  
  
3.  ProjectAggregator2.msi kurulumunuzu için ekleyin.