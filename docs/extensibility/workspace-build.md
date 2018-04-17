---
title: Visual Studio'da çalışma derleme | Microsoft Docs
ms.custom: ''
ms.date: 02/21/2018
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
ms.assetid: 813f7a5e-f298-4469-9f4c-a5bddf5a6e14
author: vukelich
ms.author: svukel
manager: viveis
ms.workload:
- vssdk
ms.openlocfilehash: f7415c99c68436519f9bab721fe88a48f750fa1c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="workspace-build"></a>Çalışma alanı oluşturma

Derleme desteği [Klasör Aç](../ide/develop-code-in-visual-studio-without-projects-or-solutions.md) senaryoları gerektirir sağlamak için genişletici [dizine](workspace-indexing.md) ve [dosyası içeriği](workspace-file-contexts.md) verileri [çalışma](workspaces.md), olarak çalıştırmak için de yapı eylem.

Ne uzantınızı gerekir, ana hattı aşağıdadır.

## <a name="build-file-context"></a>Dosya içeriği derleme

- Sağlayıcı fabrikası
  - `ExportFileContextProviderAttribute` ile öznitelik `supportedContextTypeGuids` tüm geçerli `string` arasındaki sabitleri `BuildContextTypes`
  - Uygular `IWorkspaceProviderFactory<IFileContextProvider>`
  - Dosya içeriği sağlayıcısı
    - Dönüş bir `FileContext` her biri için yapı işlemi ve desteklenen yapılandırma
      - `contextType` Kaynak <xref:Microsoft.VisualStudio.Workspace.Build.BuildContextTypes>
      - `context` uygulayan <xref:Microsoft.VisualStudio.Workspace.Build.IBuildConfigurationContext> ile `Configuration` özelliği yapı yapılandırması olarak (örneğin `"Debug|x86"`, `"ret"`, veya `null` uygulanabilir değilse). Alternatif olarak, bir örneğini kullanması <xref:Microsoft.VisualStudio.Workspace.Build.BuildConfigurationContext>. Yapılandırma değeri **gerekir** dizinli dosya veri değeri yapılandırmasından eşleşmesi.

## <a name="indexed-build-file-data-value"></a>Dizinli derleme dosyası veri değeri

- Sağlayıcı fabrikası
  - `ExportFileScannerAttribute` ile öznitelik `IReadOnlyCollection<FileDataValue>` desteklenen bir tür olarak
  - Uygular `IWorkspaceProviderFactory<IFileScanner>`
- Üzerinde dosya tarayıcısı `ScanContentAsync<T>`
  - Veri döndüren zaman `FileScannerTypeConstants.FileDataValuesType` tür bağımsız değişkeni
  - İle oluşturulan her yapılandırma dosyası veri değeri döndürür:
    - `type` olarak `BuildConfigurationContext.ContextTypeGuid`
    - `context` yapı yapılandırması olarak (örneğin `"Debug|x86"`, `"ret"`, veya `null` uygulanabilir değilse). Bu değer **gerekir** dosyası içeriği yapılandırmasından eşleşmesi.

## <a name="build-file-context-action"></a>Derleme dosyası bağlam eylemi

- Sağlayıcı fabrikası
  - `ExportFileContextActionProvider` ile öznitelik `supportedContextTypeGuids` tüm geçerli `string` arasındaki sabitleri `BuildContextTypes`
  - Uygular `IWorkspaceProviderFactory<IFileContextActionProvider>`
- Eylem sağlayıcısında `IFileContextActionProvider.GetActionsAsync`
  - Dönüş bir `IFileContextAction` eşleşen verilen `FileContext.ContextType` değeri
- Dosya bağlam eylemi
  - Implements `IFileContextAction` ve <xref:Microsoft.VisualStudio.Workspace.Extensions.VS.IVsCommandItem>
  - `CommandGroup` özellik döndürür `16537f6e-cb14-44da-b087-d1387ce3bf57`
  - `CommandId` olan `0x1000` yapı için `0x1010` yeniden oluşturma için veya `0x1020` için temizleme

>[!NOTE]
>Bu yana `FileDataValue` sıralanması gerekiyor bazı çalışma ve hangi dosya tarama tam yapı işlevselliği için noktası açma arasındaki süre miktarı olacaktır. Gecikme önceden önbelleğe alınan bir dizin olduğundan ilk klasörünü açarken görülür.

## <a name="reporting-messages-from-a-build"></a>Derlemeden raporlama iletileri

Yapı bilgi, uyarı ve hata iletilerini kullanıcılara iki yoldan biriyle yüzey. En basit yolu kullanmaktır <xref:Microsoft.VisualStudio.Workspace.Build.IBuildMessageService> ve sağlayan bir <xref:Microsoft.VisualStudio.Workspace.Build.BuildMessage>, şu şekilde:

```csharp
using Microsoft.VisualStudio.Workspace;
using Microsoft.VisualStudio.Workspace.Build;

private static void OutputBuildMessage(IWorkspace workspace)
{
    IBuildMessageService buildMessageService = workspace.GetBuildMessageService();

    if (buildMessageService != null)
    {
      // Example error build message. See the documentation for BuildMessage for more information.
      var message = new BuildMessage()
      {
          Type = BuildMessage.TaskType.Error,
          Code = "MY1001",
          TaskText = "This is a sample error",
          ProjectFile = "buildfile.bld",
          File = "sourcefile.src"
          LogMessage = $"This is sample text that will only go to the Build output window pane.\n"

          // And any other properties to set
      };

      buildMessageService.ReportBuildMessages(new BuildMessage[] { message });
    }
}
```

`BuildMessage.Type` ve `BuildMessage.LogMessage` bilgileri kullanıcıya Burada sunulan davranışını denetler. Tüm `BuildMessage.TaskType` dışındaki değeri `None` oluşturacak bir **hata listesi** verilen ayrıntılarla girişi. `LogMessage` her zaman içinde çıkış **yapı** bölmesinde **çıkış** araç penceresi.

Alternatif olarak, uzantıları doğrudan etkileşim kurabildikleri **hata listesi** veya **yapı** bölmesi. Visual Studio 2017 sürüm 15.7'den önceki sürümlerde bir hata var. nerede `pszProjectUniqueName` bağımsız değişkeni <xref:Microsoft.VisualStudio.Shell.Interop.IVsOutputWindowPane2.OutputTaskItemStringEx2*> göz ardı edilir.

>[!WARNING]
>Arayanlar `IFileContextAction.ExecuteAsync` için rasgele temel alınan uygulamaları sağlayabilir `IProgress<IFileContextActionProgressUpdate>` bağımsız değişkeni. Hiçbir zaman çağırma `IProgress<IFileContextActionProgressUpdate>.Report(IFileContextActionProgressUpdate)` doğrudan. Şu anda bu bağımsız değişkeni kullanmak için hiçbir genel yönergeleri vardır, ancak bu yönergelerdir değiştirilebilir.

## <a name="build-related-apis"></a>Yapı ilgili API'ler

- <xref:Microsoft.VisualStudio.Workspace.Build.IBuildConfigurationContext> Yapı yapılandırma ayrıntıları sağlar.
- <xref:Microsoft.VisualStudio.Workspace.Build.IBuildMessageService> gösterir <xref:Microsoft.VisualStudio.Workspace.Build.BuildMessage>kullanıcılara s.

## <a name="tasksvsjson-and-launchvsjson"></a>Tasks.vs.JSON ve launch.vs.json

Bir tasks.vs.json veya launch.vs.json dosyası yazma hakkında daha fazla bilgi için bkz: [yapı özelleştirebilir ve hata ayıklama görevleri](../ide/customize-build-and-debug-tasks-in-visual-studio.md).

## <a name="next-steps"></a>Sonraki adımlar

* [Dil sunucusu Protokolü](language-server-protocol.md) -Visual Studio'ya dil sunucuları tümleştirmek öğrenin.