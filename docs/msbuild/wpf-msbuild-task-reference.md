---
title: WPF MSBuild görev başvurusu | Microsoft Docs
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
- WPF MSBuild task reference [WPF MSBuild], term/definition table
- build tasks [WPF MSBuild], Microsoft build engine
- build tasks using the Microsoft build engine [WPF MSBuild], compile markup and process resources
- WPF MSBuild task reference [WPF MSBuild]
ms.assetid: 96df0370-e50f-4ffc-9771-b12fb8721143
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 30acdaddc132a40c37bc489b07ae3b7f2843b215
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
ms.locfileid: "31573144"
---
# <a name="wpf-msbuild-task-reference"></a>WPF MSBuild Görev Başvurusu
Windows Presentation Foundation (WPF) oluşturma işlemi Microsoft build engine (MSBuild) derleme görevleri, biçimlendirme ve işlem kaynakları derlemek için görevleri dahil ek kümesi ile genişletir.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [FileClassifier](../msbuild/fileclassifier-task.md)  
 Kaynak kaynaklar bütünleştirilmiş kod içine katıştırılır o olarak bir dizi sınıflandırır. Bir kaynak yerelleştirilebilir değilse, ana uygulama derlemeye katıştırılır; Aksi takdirde, uydu derlemeye katıştırılır.  
  
 [GenerateTemporaryTargetAssembly](../msbuild/generatetemporarytargetassembly-task.md)  
 En az bir bütünleştirilmiş oluşturur [!INCLUDE[TLA#tla_xaml](../msbuild/includes/tlasharptla_xaml_md.md)] projesinde sayfasına başvuruda bu projede yerel olarak bildirilen bir türü. Oluşturulan derleme oluşturma işlemi tamamlandıktan sonra ya da oluşturma işlemi başarısız olursa kaldırılır.  
  
 [GetWinFXPath](../msbuild/getwinfxpath-task.md)  
 Geçerli dizinin döndürür [!INCLUDE[TLA#tla_winfx](../msbuild/includes/tlasharptla_winfx_md.md)] çalışma zamanı.  
  
 [MarkupCompilePass1](../msbuild/markupcompilepass1-task.md)  
 Yerelleştirilemeyen dönüştürür [!INCLUDE[TLA#tla_xaml](../msbuild/includes/tlasharptla_xaml_md.md)] proje dosyalarını derlenmiş ikili biçime.  
  
 [MarkupCompilePass2](../msbuild/markupcompilepass2-task.md)  
 İkinci geçiş biçimlendirmesi derleme gerçekleştirir [!INCLUDE[TLA#tla_xaml](../msbuild/includes/tlasharptla_xaml_md.md)] türleri aynı projede başvuru dosyaları.  
  
 [MergeLocalizationDirectives](../msbuild/mergelocalizationdirectives-task.md)  
 Yerelleştirme öznitelikleri ve bir veya daha fazla açıklama birleştirir [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] tüm derleme için tek bir dosya halinde ikili biçimi dosyaları.  
  
 [ResourcesGenerator](../msbuild/resourcesgenerator-task.md)  
 Bir veya daha fazla kaynak katıştırır (.jpg, .ico, .bmp, [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] ikili biçimi ve diğer uzantı türleri) .resources dosyasına.  
  
 [UidManager](../msbuild/uidmanager-task.md)  
 Denetler, güncelleştirir veya tüm yerelleştirme için benzersiz tanımlayıcıları (Uıd'leri) kaldırır [!INCLUDE[TLA#tla_xaml](../msbuild/includes/tlasharptla_xaml_md.md)] kaynağında bulunan öğeleri [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] dosyaları.  
  
 [UpdateManifestForBrowserApplication](../msbuild/updatemanifestforbrowserapplication-task.md)  
 Ekler  **\<HostInBrowser / >** uygulama bildirimi öğesine (*projectname*. exe.manifest) olduğunda bir [!INCLUDE[TLA#tla_xbap](../msbuild/includes/tlasharptla_xbap_md.md)] projesi oluşturulur.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MSBuild](../msbuild/msbuild.md)