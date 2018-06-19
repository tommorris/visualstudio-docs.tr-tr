---
title: MSBuild çoklu sürüm desteği'ne genel bakış | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
ms.assetid: eecbcd65-9fbc-4307-a321-46d3c3b79b12
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4e85bb64252a73195e4ab8226cfbdb141199107d
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
ms.locfileid: "31569176"
---
# <a name="msbuild-multitargeting-overview"></a>MSBuild Çoklu Sürüm Desteğine Genel Bakış
MSBuild kullanarak herhangi bir .NET Framework'ün birçok sürümlerin ve birkaç sistemi platformları herhangi birini çalıştırmak için bir uygulama derleyebilirsiniz. Örneğin, .NET Framework 2.0 32 bit platformda çalışacak bir uygulama derleyin ve .NET Framework 4. 5 ' 64-bit platformda çalışacak şekilde aynı uygulamayı derleyin.  
  
> [!IMPORTANT]
>  Adı "çoklu sürüm desteği rağmen", bir proje aynı anda yalnızca bir çerçeve ve yalnızca bir platform hedefleyebilirsiniz.  
  
 MSBuild hedefleme özelliklerden bazıları şunlardır:  
  
-   Örneğin, sürüm 2.0, 3.5 veya 4 .NET Framework'ün önceki bir sürümünü hedefleyen bir uygulama geliştirebilirsiniz.  
  
-   .NET Framework, örneğin, Silverlight Framework dışında bir çerçeve hedefleyebilirsiniz.  
  
-   Hedef alabilirsiniz bir *framework profili*, bir hedef framework'ün önceden tanımlanmış bir alt kümesidir.  
  
-   Geçerli .NET Framework sürümü için bir hizmet paketi yayımlanırsa hedefleyebilir.  
  
-   MSBuild hedefleme uygulama yalnızca hedef framework ve platform kullanılabilir işlevleri kullanan güvence altına alır.  
  
## <a name="target-framework-and-platform"></a>Hedef Framework ve Platform  
 A *hedef framework* bir proje üzerinde çalıştırmak için yerleşik bir .NET Framework sürümü ve *hedef platformu* projeyi çalıştırmak için yerleşik bir sistem platformdur.  Örneğin, bir .NET Framework 2.0 uygulamayı (x86) 802 x 86 işlemci ailesi ile uyumlu bir 32 bit platformda çalışacak şekilde hedeflemek isteyebilirsiniz. Hedef Çerçeve ve hedef platformu bileşimi olarak bilinen *hedef bağlamı*. Daha fazla bilgi için bkz: [hedef çerçeve ve hedef Platform](../msbuild/msbuild-target-framework-and-target-platform.md).  
  
## <a name="toolset-toolsversion"></a>Araç Takımı (ToolsVersion)  
 Bir araç takımı birlikte araçları, görevler ve uygulaması oluşturmak için kullanılan hedefleri toplar. Derleyicileri csc.exe ve vbc.exe, sık kullanılan hedefler dosyası (microsoft.common.targets) gibi bir araç takımı içerir ve ortak görevleri (microsoft.common.tasks) dosya. 4.5 araç takımı hedef .NET Framework sürüm 2.0, 3.0, 3.5, 4 ve 4.5 kullanılabilir. Ancak, .NET Framework sürüm 2.0 hedeflemek için 2.0 araç takımı yalnızca kullanılabilir. Daha fazla bilgi için bkz: [araç takımı (ToolsVersion)](../msbuild/msbuild-toolset-toolsversion.md).  
  
## <a name="reference-assemblies"></a>Başvuru derlemeleri  
 Araç takımında yer belirtilen başvuru derlemeleri tasarım ve uygulama oluşturmanıza yardımcı olur. Bu başvuru derlemeleri yalnızca belirli hedef yapı etkinleştirmek, ancak ayrıca bileşenleri ve Visual Studio IDE özelliklerinde hedefiyle uyumlu olanları kısıtlama. Daha fazla bilgi için bkz: [tasarım zamanında derlemeleri çözme](../msbuild/resolving-assemblies-at-design-time.md)  
  
## <a name="configuring-targets-and-tasks"></a>Hedefleri ve Görevleri Yapılandırma  
 MSBuild hedefleri ve görevleri çalıştırmak için yapılandırabilirsiniz zaman-işlem MSBuild ile böylece üzerinde çalıştığını daha önemli ölçüde farklı bağlamları hedefleyebilirsiniz.  Örneğin, .NET Framework 4.5 ile 64-bit platformda geliştirme bilgisayarında çalışırken 32-bit, .NET Framework 2.0 uygulama hedefleyebilirsiniz. Daha fazla bilgi için bkz: [yapılandırma hedefleri ve görevleri](../msbuild/configuring-targets-and-tasks.md).  
  
## <a name="troubleshooting"></a>Sorun giderme  
 Hedef bağlamı parçası olmayan bir derleme başvurusu çalışırsanız hatalarla karşılaşabilirsiniz. Bu hatalar ve bunlarla ilgili yapmanız gerekenler hakkında daha fazla bilgi için bkz: [.NET Framework hedefleme hataları giderme](../msbuild/troubleshooting-dotnet-framework-targeting-errors.md).