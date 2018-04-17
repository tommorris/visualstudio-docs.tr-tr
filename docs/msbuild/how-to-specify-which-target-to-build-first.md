---
title: 'Nasıl yapılır: derleme için önce hangi hedefin belirtme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- DefaultTargets attribute [MSBuild]
- MSBuild, specifying the defalut target
- MSBuild, DefaultTargets attribute
ms.assetid: a580ba5b-2919-42d2-ae38-1af991e0205a
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ad48e38142949f10256780281becebeb5d4a0dcd
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-specify-which-target-to-build-first"></a>Nasıl Yapılır: Önce Hangi Hedefin Derleneceğini Belirtme
Bir veya daha fazla proje dosyası içerebilir `Target` proje nasıl yapılandırıldığını tanımlayan öğeleri. [!INCLUDE[vstecmsbuildengine](../msbuild/includes/vstecmsbuildengine_md.md)] ([!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]) Altyapısı derlemeler ilk proje dosyası içermedikçe bulur ve bağımlılıkları, bu proje bir `DefaultTargets` öznitelik, bir `InitialTargets` özniteliği ya da bir hedef belirtilen komut satırını kullanarak **/ Hedef** geçin.  
  
## <a name="using-the-initialtargets-attribute"></a>InitialTargets özniteliğini kullanma  
 `InitialTargets` Özniteliği `Project` öğesi belirttiğinden önce çalışacak bir hedef hedefleri komut satırında veya belirtilmese bile `DefaultTargets` özniteliği.  
  
#### <a name="to-specify-one-initial-target"></a>Bir ilk hedef belirtmek için  
  
-   Varsayılan hedef belirtin `InitialTargets` özniteliği `Project` öğesi. Örneğin:  
  
     `<Project InitialTargets="Clean">`  
  
 Birden fazla ilk hedef belirtebilirsiniz `InitialTargets` sırayla hedefleri listeleyen ve her hedef ayırmak için noktalı virgül kullanarak özniteliği. Hedefleri listesinde sırayla çalışır.  
  
#### <a name="to-specify-more-than-one-initial-target"></a>Birden fazla ilk hedef belirtmek için  
  
-   İçinde noktalı virgülle ayırarak ilk hedefleri listesinde `InitialTargets` özniteliği `Project` öğesi. Örneğin, çalıştırmak için `Clean` hedef ve ardından `Compile` hedeflemek için yazın:  
  
     `<Project InitialTargets="Clean;Compile">`  
  
## <a name="using-the-defaulttargets-attribute"></a>DefaultTargets özniteliği kullanma  
 `DefaultTargets` Özniteliği `Project` öğesi belirttiğinden hangi hedef veya hedefleri yerleşik bir hedef komut satırında açıkça belirtilmediği takdirde. Hedefleri ikisi de belirtilmezse, `InitialTargets` ve `DefaultTargets` öznitelikleri ve hiçbir hedef komut satırında belirtilen [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] belirtilen hedefleri çalıştıran `InitialTargets` özniteliği belirtilen hedefleri ve ardından `DefaultTargets` özniteliği.  
  
#### <a name="to-specify-one-default-target"></a>Bir varsayılan hedef belirtmek için  
  
-   Varsayılan hedef belirtin `DefaultTargets` özniteliği `Project` öğesi. Örneğin:  
  
     `<Project DefaultTargets="Compile">`  
  
 Birden fazla varsayılan hedef belirtebilirsiniz `DefaultTargets` sırayla hedefleri listeleyen ve her hedef ayırmak için noktalı virgül kullanarak özniteliği. Hedefleri listesinde sırayla çalışır.  
  
#### <a name="to-specify-more-than-one-default-target"></a>Birden fazla varsayılan hedef belirtmek için  
  
-   İçinde noktalı virgülle ayırarak varsayılan hedefler listesinde `DefaultTargets` özniteliği `Project` öğesi. Örneğin, çalıştırmak için `Clean` hedef ve ardından `Compile` hedeflemek için yazın:  
  
     `<Project DefaultTargets="Clean;Compile">`  
  
## <a name="using-the-target-switch"></a>/ Target anahtarı kullanma  
 Varsayılan hedef proje dosyasında tanımlı değil ya da varsayılan hedefleyen kullanmak istemiyorsanız, komut satırı anahtarını kullanabilirsiniz **/target** farklı bir hedef belirtmek için. Hedef veya ile belirtilen hedefleri **/target** tarafından belirtilen hedefleri yerine run anahtarı `DefaultTargets` özniteliği. Belirtilen hedefleri `InitialTargets` her zaman ilk çalıştırma özniteliği.  
  
#### <a name="to-use-a-target-other-than-the-default-target-first"></a>Bir hedef varsayılan hedefinden ilk kullanmak için  
  
-   İlk kullanan hedef olarak hedef belirtin **/target** komut satırı anahtarı. Örneğin:  
  
     `msbuild file.proj /target:Clean`  
  
#### <a name="to-use-several-targets-other-than-the-default-targets-first"></a>Varsayılan hedefler dışında çeşitli hedefleri ilk kullanmak için  
  
-   Noktalı virgül veya kullanarak, virgülle ayrılmış hedefleri, liste **/target** komut satırı anahtarı. Örneğin:  
  
     `msbuild <file name>.proj /t:Clean;Compile`  
  
## <a name="see-also"></a>Ayrıca Bkz.
  [MSBuild](../msbuild/msbuild.md)  
 [Hedefleri](../msbuild/msbuild-targets.md)   
 [Nasıl Yapılır: Derlemeyi Temizleme](../msbuild/how-to-clean-a-build.md)