---
title: "T4 CleanUpBehavior yönergesi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: f773f04799ec1ec975626699f37089c3c5b59b2d
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/13/2018
---
# <a name="t4-cleanupbehavior-directive"></a>T4 CleanUpBehavior yönergesi
Bir metin şablonunu işledikten sonra appDomain öğesini silmek için aşağıdaki satırı ekleyin:  
  
```  
<#@ CleanupBehavior processor="T4VSHost" CleanupAfterProcessingtemplate="true" #>  
```  
  
 Metin şablonları, ana bilgisayar işleminden ayrı bir appDomain içinde işlenir. Çoğu durumda, bir metin şablonu işlenirken, appdomain, bir sonraki şablonu işlemek için tekrar kullanılır. Ancak, CleanupBehavior belirtirseniz, appDomain silinir ve sonraki şablon yeni bir appDomain içinde işlenir.  
  
 Bu metin işlemeyi yavaşlatır, ancak kaynakların kaldırıldıklarından emin olmak için yararlı olabilir.  
  
 Bu yönerge yalnızca Visual Studio ana bilgisayarında çalışır.