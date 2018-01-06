---
title: "MSBuild koşulları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, conditions
- conditions [MSBuild]
ms.assetid: 9d7aa308-b667-48ed-b4c9-a61e49eb0a85
caps.latest.revision: "14"
author: kempb
ms.author: kempb
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: b42dadc5a606bcbd94334a070cc571607576dcc9
ms.sourcegitcommit: 03a74d29a1e0584ff4808ce6c9e812b51e774905
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/02/2018
---
# <a name="msbuild-conditions"></a>MSBuild Koşulları
[!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]olabilir koşullar, belirli bir kümesini destekler yerde uygulanan bir `Condition` özniteliği izin verilir. Aşağıdaki tabloda, bu koşullar açıklanmaktadır.  
  
|Koşul|Açıklama|  
|---------------|-----------------|  
|'`stringA`' == '`stringB`'|Değerlendiren `true` varsa `stringA` eşittir `stringB`.<br /><br /> Örneğin:<br /><br /> `Condition="'$(CONFIG)'=='DEBUG'"`<br /><br /> Tek tırnak basit alfasayısal dizeler veya Boole değerleri için gerekli değildir. Ancak, tek tırnak, boş değerler için gereklidir.|  
|'`stringA`' != '`stringB`'|Değerlendiren `true` varsa `stringA` eşit değil `stringB`.<br /><br /> Örneğin:<br /><br /> `Condition="'$(CONFIG)'!='DEBUG'"`<br /><br /> Tek tırnak basit alfasayısal dizeler veya Boole değerleri için gerekli değildir. Ancak, tek tırnak, boş değerler için gereklidir.|  
|\<, >, \<=, >=|İşlenen sayısal değerlerini değerlendirir. Döndürür `true` ilişkisel değerlendirme true ise. İşlenen bir ondalık ya da onaltılık sayı değerlendirmeniz gerekir. Onaltılık sayı "0 x" ile başlaması gerekir. **Not:** XML'de karakterleri `<` ve `>` kaçış uygulanmalıdır. Simgenin `<` olarak temsil edilir `&lt;`. Simgenin `>` olarak temsil edilir `&gt;`.|  
|Var ('`stringA`')|Değerlendiren `true` bir dosya veya klasör adıyla `stringA` bulunmaktadır.<br /><br /> Örneğin:<br /><br /> `Condition="!Exists('$(builtdir)')"`<br /><br /> Tek tırnak basit alfasayısal dizeler veya Boole değerleri için gerekli değildir. Ancak, tek tırnak, boş değerler için gereklidir.|  
|HasTrailingSlash ('`stringA`')|Değerlendiren `true` belirtilen dize ya da geri eğik içeriyorsa (\\) veya eğik çizgi (/) karakteri iletin.<br /><br /> Örneğin:<br /><br /> `Condition="!HasTrailingSlash('$(OutputPath)')"`<br /><br /> Tek tırnak basit alfasayısal dizeler veya Boole değerleri için gerekli değildir. Ancak, tek tırnak, boş değerler için gereklidir.|  
|!|Değerlendiren `true` işleneni değerlendirilirse `false`.|  
|Ve|Değerlendiren `true` için her iki işlenen değerlendirin varsa `true`.|  
|Veya|Değerlendiren `true` işlenen en az biri değerlendirilirse `true`.|  
|()|Değerlendiren mekanizması gruplandırma `true` için içeride korunan ifadeleri değerlendirin varsa `true`.|  
|(% ifade %) $if$ $başka$, $endif$|Denetler olup belirtilen `%expression%` geçirilen özel şablon parametresi dize değeri ile eşleşir. Varsa `$if$` koşulu değerlendirir `true`, kendi deyimleri sonra çalışma; Aksi takdirde `$else$` koşul denetlenir. Varsa `$else$` koşul `true`, kendi deyimleri sonra çalışma; Aksi takdirde `$endif$` koşul ifade değerlendirme sona erer.<br /><br /> Kullanım örnekleri için bkz: [Visual Studio Proje/öğesi şablon parametresi mantığı](http://stackoverflow.com/questions/6709057/visual-studio-project-item-template-parameter-logic).|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MSBuild başvurusu](../msbuild/msbuild-reference.md)   
 [Koşullu yapılar](../msbuild/msbuild-conditional-constructs.md)   
 [İzlenecek Yol: Sıfırdan MSBuild Proje Dosyası Oluşturma](../msbuild/walkthrough-creating-an-msbuild-project-file-from-scratch.md)
