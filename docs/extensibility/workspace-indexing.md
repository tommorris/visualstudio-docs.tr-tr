---
title: Visual Studio'da dizin oluşturma çalışma | Microsoft Docs
ms.custom: ''
ms.date: 02/21/2018
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
ms.assetid: 3163e98c-1c79-48a7-813f-7923be894ba1
author: vukelich
ms.author: svukel
manager: viveis
ms.workload:
- vssdk
ms.openlocfilehash: 5004db0d895d1fdc697c18606c346c24cd484527
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31143432"
---
# <a name="workspace-indexing"></a>Çalışma dizini oluşturma

Bir çözümde proje sistemleri için yapı işlevselliği sağlamak için sorumlu, hata ayıklama, **GoTo** sembol arama ve daha fazlası. İlişki ve projedeki dosyaları özelliklerini anlamak için proje sistemleri bu iş yapabilirsiniz. Bir [Klasör Aç](../ide/develop-code-in-visual-studio-without-projects-or-solutions.md) çalışma zengin IDE özellikleri de sağlamak için aynı Insight gerekiyor. Koleksiyonu ve bu verilerin kalıcı depolama çalışma dizinini adlı bir işlem değil. Dizinli bu verileri bir dizi zaman uyumsuz API sorgulanabilir. Extender'larının katılmak dizin oluşturma işleminde sağlayarak <xref:Microsoft.VisualStudio.Workspace.Indexing.IFileScanner>belirli dosya türlerini nasıl ele alınacağını bilmeniz s.

## <a name="types-of-indexed-data"></a>Dizinlenmiş veri türleri

Üç tür dizini veri vardır. Not Dosya tarayıcılarından beklenen türe dizinden seri türü farklıdır.

|Veri|Dosya tarayıcı türü|Dizin sorgu sonuç türü|İlgili türleri|
|--|--|--|--|
|Referanslar|<xref:Microsoft.VisualStudio.Workspace.Indexing.FileReferenceInfo>|<xref:Microsoft.VisualStudio.Workspace.Indexing.FileReferenceResult>|<xref:Microsoft.VisualStudio.Workspace.Indexing.FileReferenceInfoType>|
|Simgeleri|<xref:Microsoft.VisualStudio.Workspace.Indexing.SymbolDefinition>|<xref:Microsoft.VisualStudio.Workspace.Indexing.SymbolDefinitionSearchResult>|<xref:Microsoft.VisualStudio.Workspace.Indexing.ISymbolService> yerine kullanılmalıdır `IIndexWorkspaceService` sorgular için|
|Veri değerleri|<xref:Microsoft.VisualStudio.Workspace.Indexing.FileDataValue>|<xref:Microsoft.VisualStudio.Workspace.Indexing.FileDataResult`1>||

## <a name="querying-for-indexed-data"></a>Dizinli veriler için sorgulama

Kalıcı veri erişmek için kullanılabilecek iki zaman uyumsuz türü vardır. İlk aracılığıyladır <xref:Microsoft.VisualStudio.Workspace.Indexing.IIndexWorkspaceData>. Tek bir dosyaya ait temel erişim sağlayan `FileReferenceResult` ve `FileDataResult` veri ve sonuçları önbelleğe alır. İkinci <xref:Microsoft.VisualStudio.Workspace.Indexing.IIndexWorkspaceService> hangi önbelleğe alma kullanmaz, ancak daha fazla sorgulama özellikleri sunar.

```csharp
using Microsoft.VisualStudio.Workspace;
using Microsoft.VisualStudio.Workspace.Indexing;

private static IIndexWorkspaceData GetCachedIndexedData(IWorkspace workspace)
{
    // Gets access to indexed data wrapped in a cache.
    return workspace?.GetIndexWorkspaceDataService()?.CreateIndexWorkspaceData();
}

private static IIndexWorkspaceService GetDirectIndexedData(IWorkspace workspace)
{
    // Gets direct access to indexed data.
    // Can also be casted to IIndexWorkspaceService2.
    return workspace?.GetIndexWorkspaceService();
}
```

## <a name="participating-in-indexing"></a>Dizin oluşturma katılma

Çalışma dizinini kabaca aşağıdaki dizisi aşağıdaki gibidir:

1. Bulma ve dosya sistemi çalışma alanı (yalnızca ilk açılış tarama) varlıklarda kalıcılığı.
1. Dosya başına en yüksek öncelikli eşleşen sağlayıcısı için tarama istenir `FileReferenceInfo`s.
1. Dosya başına en yüksek öncelikli eşleşen sağlayıcısı için tarama istenir `SymbolDefinition`s.
1. Dosya başına, tüm sağlayıcılar için sorulan `FileDataValue`s.

Uzantılar, bir tarayıcı uygulayarak verebilirsiniz `IWorkspaceProviderFactory<IFileScanner>` ve tür ile dışarı aktarma <xref:Microsoft.VisualStudio.Workspace.Indexing.ExportFileScannerAttribute>. `SupportedTypes` Öznitelik bağımsız değişkeni, bir veya daha fazla değerlerinden olmalıdır <xref:Microsoft.VisualStudio.Workspace.Indexing.FileScannerTypeConstants>. Bir örnek tarayıcı için bkz: VS SDK [örnek](https://github.com/Microsoft/VSSDK-Extensibility-Samples/blob/master/Open_Folder_Extensibility/C%23/SymbolScannerSample/TxtFileSymbolScanner.cs).

> [!WARNING]
> Destekleyen bir dosya tarayıcısı verme `FileScannerTypeConstants.FileScannerContentType` türü. Microsoft iç, yalnızca amacıyla kullanılır.

Gelişmiş durumlarda uzantı dinamik olarak rastgele bir kümesi dosya türlerini destekleyebilir. MEF dışarı aktarma yerine `IWorkspaceProviderFactory<IFileScanner>`, bir uzantı verebilirsiniz `IWorkspaceProviderFactory<IFileScannerProvider>`. Dizin oluşturma işlemi başladığında, bu Fabrika türü örneği, içeri aktarılan, ve sahip kendi <xref:Microsoft.VisualStudio.Workspace.Indexing.IFileScannerProvider.GetSymbolScannersAsync%2A> yöntemi çağrılır. `IFileScanner` örnekler arasında bir değer destekleyen `FileScannerTpeConstants` kabul, yalnızca simgeler.

## <a name="next-steps"></a>Sonraki adımlar

* [Çalışma alanları ve dil Hizmetleri](workspace-language-services.md) -Klasör Aç çalışma alanına dil services tümleştirme öğrenin.
* [Çalışma alanı yapı](workspace-build.md) -Klasör Aç destekleyen sistemleri MSBuild ve derleme görevleri dosyaları gibi yapı.