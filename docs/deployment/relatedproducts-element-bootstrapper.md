---
title: '&lt;RelatedProducts&gt; öğe (Önyükleyici) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-deployment
ms.topic: conceptual
f1_keywords:
- MSBuild.GenerateBootstrapper.MissingDependency
- MSBuild.GenerateBootstrapper.DuplicateItems
- MSBuild.GenerateBootstrapper.IncludedProductIncluded
- MSBuild.GenerateBootstrapper.DependencyNotFound
- MSBuild.GenerateBootstrapper.PackageFileNotFound
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- <RelatedProducts> element [bootstrapper]
ms.assetid: bf152712-4c1e-48bd-9b7f-311cf0fdb832
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: 9fafc77df0bc557952bd5e197f3c950a3d028e3e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="ltrelatedproductsgt-element-bootstrapper"></a>&lt;RelatedProducts&gt; öğe (Önyükleyici)
`RelatedProducts` Öğesi bağlı ya da geçerli ürün dahil diğer ürünleri tanımlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<RelatedProducts>  
    <DependsOnProduct  
        Code  
    />  
    <EitherProducts>  
        <DependsOnProduct  
            Code  
        />  
    </EitherProducts>  
    <IncludesProduct  
        Code  
    />  
</RelatedProducts>  
```  
  
## <a name="elements-and-attributes"></a>Öğeleri ve öznitelikleri  
 `RelatedProducts` Bir alt öğedir `Product` öğesi. Özniteliklere sahiptir.  
  
## <a name="dependsonproduct"></a>DependsOnProduct  
 `DependsOnProduct` Öğesi geçerli ürün adlandırılmış ürüne bağlı bağlıdır ve adlandırılmış ürünün geçerli bir önce yüklenmesi gerektiğini belirtir. Bir alt öğesi değil `RelatedProducts` öğesi. A `RelatedProducts` öğesi bir veya daha fazla olabilir `DependsOnProduct` öğeleri.  
  
 `DependsOnProduct` Aşağıdaki özniteliklere sahiptir.  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`Code`|Kod adı tarafından belirtilen bulunan ürünün `ProductCode` özniteliği `Product` öğesi. Daha fazla bilgi için bkz: [ \<ürün > öğesi](../deployment/product-element-bootstrapper.md).|  
  
## <a name="eitherproducts"></a>EitherProducts  
 `EitherProducts` Öğesi tanımlar sıfır veya daha fazla `DependsOnProduct` öğeleri ve öznitelikleri yoktur. En az bir `DependsOnProduct` bu kümesinde geçerli ürün önce yüklenmesi gerekir. A `RelatedProducts` öğesi sıfır veya daha fazla olabilir `EitherProducts` öğeleri.  
  
## <a name="includesproduct"></a>IncludesProduct  
 `IncludesProduct` Öğesi güveninin bir ürünün geçerli yüklemede ve ayrı bir yükleme gerektirmez. Bir alt öğesi değil `RelatedProducts` öğesi. A `RelatedProducts` öğesi bir veya daha fazla olabilir `IncludesProduct` öğeleri.  
  
 `IncludesProduct` Aşağıdaki özniteliklere sahiptir.  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`Code`|Kod adı tarafından belirtilen bulunan ürünün `ProductCode` özniteliği `Product` öğesi. Daha fazla bilgi için bkz: [ \<ürün > öğesi](../deployment/product-element-bootstrapper.md).|  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde Microsoft Installer yüklenmiş belirtir [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]ve bu nedenle ayrı bir yükleme gerekmez.  
  
```  
<RelatedProducts>  
    <IncludesProduct Code="Microsoft.Windows.Installer.2.0" />  
</RelatedProducts>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [\<Ürün > öğesi](../deployment/product-element-bootstrapper.md)