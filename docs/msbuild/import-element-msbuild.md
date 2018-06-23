---
title: İçeri aktarma öğesi (MSBuild) | Microsoft Docs
ms.custom: ''
ms.date: 03/13/2017
ms.technology: msbuild
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#Import
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- Import element [MSBuild]
- <Import> element [MSBuild]
ms.assetid: 3bfecaf1-69fd-4008-b651-c9dafd4389d9
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 431184d2d4c2bf0bff5d6d3f4d5c44b3c6a670a2
ms.sourcegitcommit: e6b13898cfbd89449f786c2e8f3e3e7377afcf25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/22/2018
ms.locfileid: "36326978"
---
# <a name="import-element-msbuild"></a>İçeri Aktarma Öğesi (MSBuild)
Bir proje dosyası içeriği başka bir proje dosyasına aktarır.  

 \<Proje >  
 \<İçeri aktarma >  

## <a name="syntax"></a>Sözdizimi  

```xml  
<Import Project="ProjectPath"  
    Condition="'String A'=='String B'" />  
```  

## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  

### <a name="attributes"></a>Öznitelikler  

|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`Project`|Gerekli öznitelik.<br /><br /> İçeri aktarmak için proje dosyasının yolu. Yolu joker karakter içerebilir. Eşleşen dosyaları sıralanmış olarak içe aktarılır. Bu özelliği kullanarak, kod dosyası yalnızca bir dizine ekleyerek bir projeye kod ekleyebilirsiniz.|  
|`Condition`|İsteğe bağlı öznitelik.<br /><br /> Değerlendirilecek bir koşul. Daha fazla bilgi için bkz: [koşullar](../msbuild/msbuild-conditions.md).|  

### <a name="child-elements"></a>Alt Öğeler  
 Yok.  

### <a name="parent-elements"></a>Üst Öğeler  

|Öğe|Açıklama|  
|-------------|-----------------|  
|[Project](../msbuild/project-element-msbuild.md)|Gerekli kök öğesinin bir [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] proje dosyası.|  
|[Importgroup](../msbuild/importgroup-element.md)|Bir koleksiyonu içerir `Import` öğeleri gruplandırılmış isteğe bağlı bir koşul altında.|  

## <a name="remarks"></a>Açıklamalar  
 Kullanarak `Import` öğesi, çok sayıda proje dosyalarına ortak olan kod yeniden. Bu paylaşılan kodunda yaptığınız tüm güncelleştirmeleri almak için tüm projeleri yayılan için kod bakımını kolaylaştırır.  

 Kurala göre paylaşılan alınan proje dosyalarını .targets dosyaları olarak kaydedilir, ancak standart [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] proje dosyaları. [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] farklı bir dosya adı uzantısına sahip olan bir projeyi içeri aktarma önleme değil, ancak .targets uzantısı tutarlılık için kullanmanızı öneririz.  

 İçeri aktarılan projelerinde göreli yollar alma projenin dizini göre değerlendirilir. Bu nedenle, farklı konumlarda birkaç proje dosyalarına bir proje dosyası aldıysanız, göreli yolları alınan proje dosyasında farklı bir şekilde içeri aktarılan her proje için yorumlanacak.  

 Tüm [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] ayrılmış, örneğin, proje dosyası için ilgili Özellikler `MSBuildProjectDirectory` ve `MSBuildProjectFile`, başvuru alınan projesinde alma proje dosyasına dayalı değerler atanır.  

 Alınan proje yoksa bir `DefaultTargets` alınan öznitelik projeleri içe aktarılır ve ilk değeri bulunan sıraya Denetlenmekte `DefaultTargets` özniteliği kullanılır. Örneğin ProjectA ProjectB ve ProjectC (sırasıyla) alır ve ProjectB aktarır ProjectD, [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] ilk arar `DefaultTargets` ProjectA, sonra ProjectB, sonra ProjectD ve ProjectC son olarak belirtilmiş.  

 İçeri aktarılan projesinde şeması, standart bir proje için aynıdır. Ancak [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] olabilir alınan proje genellikle kümesi veya hedefleri çalıştırmak hangi sırayla hangi özellikleri hakkında bilgi içermediği için mümkün alınan bir proje oluşturmak, onu düşüktür. Alınan proje içine bu bilgileri sağlamak için alınır projeye bağlıdır.  

> [!NOTE]
>  Koşullu içeri aktarma deyimlerini komut satırı MSBuilds içinde çalışırken, bunlar içinde MSBuild ile çalışmaz [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] tümleşik geliştirme ortamı (IDE). Koşullu içeri aktarmalar projeye yüklendiğinde, ayarladığınız yapılandırma ve platform değerleri kullanılarak değerlendirilir. Daha sonra proje dosyasında koşulları yeniden değerlendirilmesi gereken yapılan değişiklik, örneğin, platform değiştirme [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] özellikler ve öğeler, ancak içeri aktarmalar koşullar reevaluates. İçeri aktarma koşullu değerlendirilmez için alma işlemi atlandı.  
>   
>  Bu sorunu çözmek için koşullu içeri aktarmalar .targets dosyaları put kodu koşullu bir blok gibi put veya bir [seçin öğesi (MSBuild)](../msbuild/choose-element-msbuild.md) bloğu.  

## <a name="wildcards"></a>Joker karakterler  
 .NET Framework 4'te MSBuild proje özniteliğinde joker karakterleri verir. Joker karakterler olduğunda (Yeniden Üretilebilirlik için) bulunan tüm eşleşmeleri sıralanır ve sırasını açıkça ayarlanmış gibi daha sonra bu sırayla aktarıldıkları.  

 Bu, başka birinin açıkça alma dosyanın dosya adı eklemek gerek kalmadan bir dosyayı içeri aktarabilirsiniz böylece genişletilebilirlik noktanız olanağı sunmak istiyorsanız kullanışlıdır. Bu amaç için dosyanın en üstüne aşağıdaki satırında Microsoft.Common.Targets içerir.  

```xml  
<Import Project="$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\$(MSBuildThisFile)\ImportBefore\*" Condition="'$(ImportByWildcardBeforeMicrosoftCommonTargets)' == 'true' and exists('$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\$(MSBuildThisFile)\ImportBefore')"/>  
```  

## <a name="example"></a>Örnek  
 Aşağıdaki örnek, çeşitli öğeleri ve özellikleri ve genel proje dosyasını içe aktaran bir proje gösterir.  

```xml  
<Project DefaultTargets="Compile"  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  

    <PropertyGroup>  
        <resourcefile>Strings.resx</resourcefile>  

        <compiledresources>  
            $(O)\$(MSBuildProjectName).Strings.resources  
        </compiledresources>  
    </PropertyGroup>  

    <ItemGroup>  
        <CSFile Include="*.cs" />  

        <Reference Include="System" />  
        <Reference Include="System.Data" />  
    </ItemGroup>  

    <Import Project="$(CommonLocation)\General.targets" />  
</Project>  
```  

## <a name="see-also"></a>Ayrıca Bkz.  
 [Proje dosyası şema başvurusu](../msbuild/msbuild-project-file-schema-reference.md)   
 [Nasıl Yapılır: Birden Çok Proje Dosyasında Aynı Hedefi Kullanma](../msbuild/how-to-use-the-same-target-in-multiple-project-files.md)
