---
title: "MSBuild proje dosyası şema başvurusu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: msbuild
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, file schema
ms.assetid: d9a68146-1f43-4621-ac78-2c8c3f400936
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 1911f7a6d5648c7940addf3301da2c818ad4f590
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="msbuild-project-file-schema-reference"></a>MSBuild Proje Dosyası Şema Başvurusu
Tüm tablonun sağlar [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] kullanılabilir öznitelikler ve alt öğelerini birlikte XML şema öğeleri.  
  
 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] derleme ve onu nasıl oluşturulacağını yapı altyapısı ne istemek için proje dosyalarını kullanır. [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]Proje dosyalarıdır uygun XML dosyaları [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] XML şeması. Bu bölümde XML şema tanımı (.xsd) dosyası için belgeleri [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)].  
  
## <a name="msbuild-xml-schema-elements"></a>MSBuild XML şema öğeleri  
 Aşağıdaki tabloda tüm listeler [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] XML Şeması öğelerini bunların alt öğeleri ve özniteliklerinin yanı sıra.  
  
|Öğe|Alt Öğeler|Öznitelikler|  
|-------------|--------------------|----------------|  
|[Öğe Seç (MSBuild)](../msbuild/choose-element-msbuild.md)|Aksi takdirde<br /><br /> ne zaman|--|  
|[İçeri Aktarma Öğesi (MSBuild)](../msbuild/import-element-msbuild.md)|--|Koşul<br /><br /> Proje|  
|[ImportGroup Öğesi](../msbuild/importgroup-element.md)|İçeri aktarma|Koşul|  
|[Öğe Unsuru (MSBuild)](../msbuild/item-element-msbuild.md)|*ItemMetaData*|Koşul<br /><br /> Exclude<br /><br /> Şunları Dahil Et:<br /><br /> Kaldır|  
|[ItemDefinitionGroup Öğesi (MSBuild)](../msbuild/itemdefinitiongroup-element-msbuild.md)|*Öğesi*|Koşul|  
|[ItemGroup Öğesi (MSBuild)](../msbuild/itemgroup-element-msbuild.md)|*Öğesi*|Koşul|  
|[ItemMetadata Öğesi (MSBuild)](../msbuild/itemmetadata-element-msbuild.md)|*Öğesi*|Koşul|  
|[OnError Öğesi (MSBuild)](../msbuild/onerror-element-msbuild.md)|--|Koşul<br /><br /> ExecuteTargets|  
|[Otherwise Öğesi (MSBuild)](../msbuild/otherwise-element-msbuild.md)|Bunu seçin<br /><br /> ItemGroup<br /><br /> PropertyGroup|--|  
|[Çıktı Öğesi (MSBuild)](../msbuild/output-element-msbuild.md)|--|Koşul<br /><br /> ItemName<br /><br /> ÖzellikAdı<br /><br /> TaskParameter|  
|[Parameter Öğesi](../msbuild/parameter-element.md)|--|Çıkış<br /><br /> ParameterType<br /><br /> Gerekli|  
|[Parameter Grup Öğesi](../msbuild/parametergroup-element.md)|*Parametre*|--|  
|[Proje Öğesi (MSBuild)](../msbuild/project-element-msbuild.md)|Bunu seçin<br /><br /> İçeri aktarma<br /><br /> ItemGroup<br /><br /> ProjectExtensions<br /><br /> PropertyGroup<br /><br /> Hedef<br /><br /> UsingTask|DefaultTargets<br /><br /> InitialTargets<br /><br /> ToolsVersion<br /><br /> TreatAsLocalProperty<br /><br /> xmlns|  
|[ProjectExtensions Öğesi (MSBuild)](../msbuild/projectextensions-element-msbuild.md)|--|--|  
|[Özellik Öğesi (MSBuild)](../msbuild/property-element-msbuild.md)|--|Koşul|  
|[PropertyGroup Öğesi (MSBuild)](../msbuild/propertygroup-element-msbuild.md)|*Özelliği*|Koşul|  
|[Sdk Element (MSBuild)](../msbuild/sdk-element-msbuild.md)|--|Ad<br /><br /> Sürüm|  
|[Hedef Öğe (MSBuild)](../msbuild/target-element-msbuild.md)|OnError<br /><br /> *Görev*|AfterTargets<br /><br /> BeforeTargets<br /><br /> Koşul<br /><br /> DependsOnTargets<br /><br /> Girişler<br /><br /> KeepDuplicateOutputs<br /><br /> Ad<br /><br /> Çıktılar<br /><br /> Döndürür|  
|[Görev Öğesi (MSBuild)](../msbuild/task-element-msbuild.md)|Çıkış|Koşul<br /><br /> ContinueOnError<br /><br /> *Parametre*|  
|[TaskBody Öğesi (MSBuild)](../msbuild/taskbody-element-msbuild.md)|*Veri*|Değerlendir|  
|[UsingTask Öğesi (MSBuild)](../msbuild/usingtask-element-msbuild.md)|ParameterGroup<br /><br /> TaskBody|AssemblyFile<br /><br /> AssemblyName<br /><br /> Koşul<br /><br /> TaskFactory<br /><br /> Görevadı|  
|[When Öğesi (MSBuild)](../msbuild/when-element-msbuild.md)|Bunu seçin<br /><br /> ItemGroup<br /><br /> PropertyGroup|Koşul|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)   
 [Koşullar](../msbuild/msbuild-conditions.md)   
 [MSBuild Başvurusu](../msbuild/msbuild-reference.md)  
 [MSBuild](../msbuild/msbuild.md)
