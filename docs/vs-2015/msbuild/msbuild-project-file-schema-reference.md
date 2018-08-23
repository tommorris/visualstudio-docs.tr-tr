---
title: MSBuild proje dosyası şema başvurusu | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, file schema
ms.assetid: d9a68146-1f43-4621-ac78-2c8c3f400936
caps.latest.revision: 22
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 134a66a38886201a9f53ed5d15dda009b095d72f
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42630517"
---
# <a name="msbuild-project-file-schema-reference"></a>MSBuild Proje Dosyası Şema Başvurusu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [MSBuild proje dosyası şema başvurusu](https://docs.microsoft.com/visualstudio/msbuild/msbuild-project-file-schema-reference).  
  
  
Tüm bir tablo sağlar [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] XML Şeması öğeleri kullanılabilir öznitelikler ve alt öğeleri.  
  
 [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] derleme ve oluşturma nasıl yapı altyapısının ne istemek için proje dosyalarını kullanır. [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] Proje dosyalardır izliyor XML dosyaları [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] XML şeması. Bu bölümde belgeleri için XML şema tanımı (.xsd) dosyası [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)].  
  
## <a name="msbuild-xml-schema-elements"></a>MSBuild XML Şeması öğeleri  
 Aşağıdaki tabloda tüm listeler [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] XML Şeması öğeleri alt öğeleri ve öznitelikleri birlikte.  
  
|Öğe|Alt Öğeler|Öznitelikler|  
|-------------|--------------------|----------------|  
|[Öğe Seç (MSBuild)](../msbuild/choose-element-msbuild.md)|Aksi takdirde<br /><br /> Ne zaman|--|  
|[İçeri Aktarma Öğesi (MSBuild)](../msbuild/import-element-msbuild.md)|--|Koşul<br /><br /> Proje|  
|[ImportGroup Öğesi](../msbuild/importgroup-element.md)|{1&gt;İçeri Aktar&lt;1}|Koşul|  
|[Öğe Unsuru (MSBuild)](../msbuild/item-element-msbuild.md)|*Itemmetadata*|Koşul<br /><br /> Hariç tutma<br /><br /> Şunları Dahil Et:<br /><br /> Kaldır|  
|[ItemDefinitionGroup Öğesi (MSBuild)](../msbuild/itemdefinitiongroup-element-msbuild.md)|*Öğesi*|Koşul|  
|[ItemGroup Öğesi (MSBuild)](../msbuild/itemgroup-element-msbuild.md)|*Öğesi*|Koşul|  
|[ItemMetadata Öğesi (MSBuild)](../msbuild/itemmetadata-element-msbuild.md)|*Öğesi*|Koşul|  
|[OnError Öğesi (MSBuild)](../msbuild/onerror-element-msbuild.md)|--|Koşul<br /><br /> ExecuteTargets|  
|[Otherwise Öğesi (MSBuild)](../msbuild/otherwise-element-msbuild.md)|Bunu seçin<br /><br /> ItemGroup<br /><br /> PropertyGroup|--|  
|[Çıktı Öğesi (MSBuild)](../msbuild/output-element-msbuild.md)|--|Koşul<br /><br /> ItemName<br /><br /> ÖzellikAdı<br /><br /> TaskParameter|  
|[Parameter Öğesi](../msbuild/parameter-element.md)|--|Çıkış<br /><br /> ParameterType<br /><br /> Gerekli|  
|[Parameter Grup Öğesi](../msbuild/parametergroup-element.md)|*Parametre*|--|  
|[Proje Öğesi (MSBuild)](../msbuild/project-element-msbuild.md)|Bunu seçin<br /><br /> {1&gt;İçeri Aktar&lt;1}<br /><br /> ItemGroup<br /><br /> ProjectExtensions<br /><br /> PropertyGroup<br /><br /> Hedef<br /><br /> UsingTask|DefaultTargets<br /><br /> InitialTargets<br /><br /> ToolsVersion<br /><br /> TreatAsLocalProperty<br /><br /> xmlns|  
|[ProjectExtensions Öğesi (MSBuild)](../msbuild/projectextensions-element-msbuild.md)|--|--|  
|[Özellik Öğesi (MSBuild)](../msbuild/property-element-msbuild.md)|--|Koşul|  
|[PropertyGroup Öğesi (MSBuild)](../msbuild/propertygroup-element-msbuild.md)|*Özelliği*|Koşul|  
|[Hedef Öğe (MSBuild)](../msbuild/target-element-msbuild.md)|OnError<br /><br /> *Görev*|AfterTargets<br /><br /> BeforeTargets<br /><br /> Koşul<br /><br /> DependsOnTargets<br /><br /> Girişler<br /><br /> KeepDuplicateOutputs<br /><br /> Ad<br /><br /> Çıktılar<br /><br /> Döndürür|  
|[Görev Öğesi (MSBuild)](../msbuild/task-element-msbuild.md)|Çıkış|Koşul<br /><br /> ContinueOnError<br /><br /> *Parametre*|  
|[TaskBody Öğesi (MSBuild)](../msbuild/taskbody-element-msbuild.md)|*Veri*|Değerlendir|  
|[UsingTask Öğesi (MSBuild)](../msbuild/usingtask-element-msbuild.md)|ParameterGroup<br /><br /> TaskBody|AssemblyFile<br /><br /> AssemblyName<br /><br /> Koşul<br /><br /> TaskFactory<br /><br /> TaskName|  
|[When Öğesi (MSBuild)](../msbuild/when-element-msbuild.md)|Bunu seçin<br /><br /> ItemGroup<br /><br /> PropertyGroup|Koşul|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)   
 [Koşullar](../msbuild/msbuild-conditions.md)   
 [MSBuild Başvurusu](../msbuild/msbuild-reference.md)  
 [MSBuild](msbuild.md)


