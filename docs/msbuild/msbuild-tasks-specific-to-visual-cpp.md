---
title: MSBuild görevleri belirli Visual C++ | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, tasks specific to Visual C++
ms.assetid: 05410f0c-7356-4692-bc00-20664421c9ff
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- cplusplus
ms.openlocfilehash: 446326fb8219183774d3f90d70a0263e0fc057e0
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
ms.locfileid: "31573765"
---
# <a name="msbuild-tasks-specific-to-visual-c"></a>Visual C++'ye Özgü MSBuild Görevleri
Görevler oluşturma işlemi sırasında çalışan bir kod sağlar. Visual C++ yüklü olduğunda, aşağıdaki görevleri ile birlikte yüklenen listelenenlere kullanılabilir [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]. Daha fazla bilgi için bkz: [MSBuild (Visual C++) genel bakış](/cpp/build/msbuild-visual-cpp-overview).  
  
 Her görev için parametreleri yanı sıra her görev ayrıca aşağıdaki parametreleri içerir.  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`Condition`|İsteğe bağlı `String` parametresi.<br /><br /> A `Boolean` ifadesi, [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] altyapısı bu görevin gerçekleştirilip gerçekleştirilmediğini belirlemek üzere kullanır. Tarafından desteklenen koşullarla ilgili bilgiler için [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)], bkz: [koşullar](../msbuild/msbuild-conditions.md).|  
|`ContinueOnError`|İsteğe bağlı parametre. Aşağıdaki değerlerden birini içerebilir:<br /><br /> -   **WarnAndContinue** veya **doğru**. Bir görev başarısız olduğunda, sonraki görevlerinde [hedef](../msbuild/target-element-msbuild.md) öğesi ve yapı devam yürütmek ve görevin tüm hataları, uyarıları olarak kabul edilir<br />-   **ErrorAndContinue**. Bir görev başarısız olduğunda, sonraki görevlerinde `Target` öğesi ve yapı devam yürütmek ve görevin tüm hataları hata olarak kabul edilir.<br />-   **ErrorAndStop** veya **false** (varsayılan). Bir görev başarısız olursa, kalan görevlere`Target` öğesi ve yapı olmayan yürütülen ve tüm `Target` öğesi ve yapı başarısız olmuş değerlendirilir.<br /><br /> Yalnızca desteklenen 4.5 önce .NET Framework sürümleri `true` ve `false` değerleri.<br /><br /> Daha fazla bilgi için bkz: [nasıl yapılır: görevlerdeki hataları Yoksay](../msbuild/how-to-ignore-errors-in-tasks.md).|  
  
## <a name="related-topics"></a>İlgili Konular  
  
|Başlık|Açıklama|  
|-----------|-----------------|  
|[BscMake Görevi](../msbuild/bscmake-task.md)|Microsoft Gözat bilgileri bakım yardımcı programı aracını (bscmake.exe) sarmalar.|  
|[CL Görevi](../msbuild/cl-task.md)|Visual C++ Derleyici Aracı'nı (cl.exe) sarmalar.|  
|[CPPClean Görevi](../msbuild/cppclean-task.md)|Visual C++ proje yapılandırıldığında MSBuild oluşturduğu geçici dosyaları siler.|  
|[LIB Görevi](../msbuild/lib-task.md)|Microsoft 32 Bit Kitaplık Yöneticisi aracını (lib.exe) sarmalar.|  
|[Link Görevi](../msbuild/link-task.md)|Visual C++ bağlayıcı Aracı'nı (link.exe) sarmalar.|  
|[MIDL Görevi](../msbuild/midl-task.md)|Microsoft arabirimi tanım dili (MIDL) derleyici Aracı'nı (midl.exe) sarmalar.|  
|[MT Görevi](../msbuild/mt-task.md)|Microsoft Bildirimi aracı (mt.exe) sarmalar.|  
|[RC Görevi](../msbuild/rc-task.md)|Microsoft Windows Kaynak Derleyicisi Aracı (rc.exe) sarmalar.|  
|[SetEnv Görevi](../msbuild/setenv-task.md)|Ayarlar veya belirtilen ortam değişkeninin değeri siler.|  
|[VCMessage Görevi](../msbuild/vcmessage-task.md)|Derleme sırasında iletileri ve hata iletilerini uyarı günlükleri.|  
|[XDCMake Görevi](../msbuild/xdcmake-task.md)|XML Belge açıklama (.xdc) dosyaları bir .xml dosyasına birleştirir XML belgeleri Aracı (xdcmake.exe) sarmalar.|  
|[XSD Görevi](../msbuild/xsd-task.md)|Şema veya sınıf dosyaları oluşturan bir kaynaktan XML şema tanımı Aracı (XSD.exe'nin) sarmalar.|  
|[MSBuild Başvurusu](../msbuild/msbuild-reference.md)|MSBuild sistem öğelerini açıklar.|  
|[Görevler](../msbuild/msbuild-tasks.md)|Bir derleme üretme için birleştirilmiş kod birimleridir görevler açıklanmaktadır.|  
|[Görev Yazma](../msbuild/task-writing.md)|Bir görevin nasıl oluşturulacağını açıklar.|