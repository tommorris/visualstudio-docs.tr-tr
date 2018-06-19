---
title: Günlükçüleri derleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- MSBuild, writing loggers
- MSBuild, logging
- logging [MSBuild]
ms.assetid: fa34810d-185a-4d22-92bd-9852915e5f1d
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 40ce48f8fc21c1c035586edf48446ce1d3f103d3
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
ms.locfileid: "31570466"
---
# <a name="build-loggers"></a>Günlükçüleri Derleme
Günlükçüleri yapınızın çıktısını özelleştirmek ve belirli yapı olaylarına yanıt olarak iletileri, hatalar veya uyarılar görüntülemek bir yol sağlar. Her Günlükçü uygulayan bir .NET sınıfı olarak uygulanan <xref:Microsoft.Build.Framework.ILogger> Microsoft.Build.Framework.dll derlemede tanımlanan arabirimi.  
  
 Günlükçü uygularken kullanabileceğiniz iki yaklaşım vardır:  
  
-   Uygulama <xref:Microsoft.Build.Framework.ILogger> doğrudan arabirim.  
  
-   Sınıfınızda yardımcı sınıfından türetilen <xref:Microsoft.Build.Utilities.Logger>, Microsoft.Build.Utilities.dll derlemede tanımlanmış. <xref:Microsoft.Build.Utilities.Logger> uygulayan <xref:Microsoft.Build.Framework.ILogger> ve bazı varsayılan uygulamalarını sağlar <xref:Microsoft.Build.Framework.ILogger> üyeleri.  
  
 Bu konuda türetilen basit bir Günlükçü yazma açıklanacaktır <xref:Microsoft.Build.Utilities.Logger>, ve derleme olaylarını konsolunda yanıt olarak belirli iletileri görüntüler.  
  
## <a name="registering-for-events"></a>Olaylar için kaydetme  
 Yapı altyapısı tarafından raporlanan yapı ilerlemeyi bilgileri toplamak ve sonra kullanışlı şekilde bu bilgileri raporlamak için Günlükçü amacı budur. Tüm günlükçüleri geçersiz kılmanız gerekir <xref:Microsoft.Build.Utilities.Logger.Initialize%2A> burada Günlükçü olaylar için kaydeder olduğundan yöntemi. Bu örnekte, Günlükçü için kayıtları <xref:Microsoft.Build.Framework.IEventSource.TargetStarted>, <xref:Microsoft.Build.Framework.IEventSource.ProjectStarted>, ve <xref:Microsoft.Build.Framework.IEventSource.ProjectFinished> olaylar.  
  
 [!code-csharp[msbuild_SimpleConsoleLogger#2](../msbuild/codesnippet/CSharp/build-loggers_1.cs)]  
  
## <a name="responding-to-events"></a>Olaylara yanıt verme  
 Günlükçü belirli olaylar için kayıtlı, bunlar ortaya çıktığında bu olayları işlemek gerekir. İçin <xref:Microsoft.Build.Framework.IEventSource.ProjectStarted>, ve <xref:Microsoft.Build.Framework.IEventSource.ProjectFinished> olayları Günlükçü yalnızca yazar kısa tümcecik ve olayla proje dosyasının adı. Günlükçü alınan tüm iletileri konsol penceresine yazılır.  
  
 [!code-csharp[msbuild_SimpleConsoleLogger#3](../msbuild/codesnippet/CSharp/build-loggers_2.cs)]  
  
## <a name="responding-to-logger-verbosity-values"></a>Günlükçü ayrıntı değerlere yanıt  
 Bazı durumlarda, yalnızca bilgileri, bir olay günlüğe isteyebilirsiniz MSBuild.exe **/verbosity** anahtar belirli bir değer içeriyor. Bu örnekte, <xref:Microsoft.Build.Framework.IEventSource.TargetStarted> olay işleyicisi yalnızca günlüklerini bir ileti <xref:Microsoft.Build.Utilities.Logger.Verbosity%2A> tarafından belirlenen özelliği **/verbosity** geçiş, eşittir <xref:Microsoft.Build.Framework.LoggerVerbosity> `Detailed`.  
  
 [!code-csharp[msbuild_SimpleConsoleLogger#4](../msbuild/codesnippet/CSharp/build-loggers_3.cs)]  
  
## <a name="specifying-a-logger"></a>Günlükçü belirtme  
 Günlükçü bütünleştirilmiş koda derlenmemiş sonra bildirmeniz gerekir [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] bu Günlükçü derlemeleri sırasında kullanılacak. Bu yapılır kullanarak **/logger** MSBuild.exe ile geçiş yapın. MSBuild.exe kullanılabilir anahtarları hakkında daha fazla bilgi için bkz: [komut satırı başvurusu](../msbuild/msbuild-command-line-reference.md).  
  
 Aşağıdaki komut satırını proje derlemeler `MyProject.csproj` Günlükçü sınıfı uygulanan kullanır `SimpleLogger.dll`. **/Nologo** anahtar gizler başlık ve telif hakkı iletisi ve **/noconsolelogger** anahtarı, varsayılan devre dışı bırakır [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] konsol Günlükçü.  
  
```  
MSBuild /nologo /noconsolelogger /logger:SimpleLogger.dll  
```  
  
 Aşağıdaki komut satırı ile aynı Günlükçü, ancak proje derleme işlemleri bir `Verbosity` düzeyini `Detailed`.  
  
```  
MSBuild /nologo /noconsolelogger /logger:SimpleLogger.dll /verbosity:Detailed  
```  
  
## <a name="example"></a>Örnek  
  
### <a name="description"></a>Açıklama  
 Aşağıdaki örnek, Günlükçü için tam bir kod içerir.  
  
### <a name="code"></a>Kod  
 [!code-csharp[msbuild_SimpleConsoleLogger#1](../msbuild/codesnippet/CSharp/build-loggers_4.cs)]  
  
### <a name="comments"></a>Açıklamalar  
  
## <a name="example"></a>Örnek  
  
### <a name="description"></a>Açıklama  
 Aşağıdaki örnek, konsol penceresinde görüntüleme yerine bir dosyayı günlüğe yazar bir Günlükçü uygulamak gösterilmiştir.  
  
### <a name="code"></a>Kod  
 [!code-csharp[msbuild_BasicLogger#1](../msbuild/codesnippet/CSharp/build-loggers_5.cs)]  
  
### <a name="comments"></a>Açıklamalar  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleme günlüklerini alma](../msbuild/obtaining-build-logs-with-msbuild.md)   
 [MSBuild Kavramları](../msbuild/msbuild-concepts.md)