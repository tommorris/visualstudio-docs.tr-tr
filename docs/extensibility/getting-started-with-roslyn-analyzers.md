---
title: Roslyn çözümleyiciler ile çalışmaya başlama | Microsoft Docs
ms.date: 04/02/2018
ms.technology: vs-ide-sdk
ms.topic: conceptual
ms.assetid: 367c2ec8-3059-46a5-9d1c-57bead0419e7
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 7b887703343dab10f9cc1f0cbf8e2e2b37b0065b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31126815"
---
# <a name="getting-started-with-roslyn-analyzers"></a>Roslyn çözümleyiciler ile çalışmaya başlama

Visual Studio'da canlı, proje tabanlı kod çözümleyicilerini ile API yazarlar kendi NuGet paketlerini bir parçası olarak etki alanına özgü kod analizi gönderebilirsiniz. Bu çözümleyiciler .NET derleme Platformu (kod adı "Roslyn") tarafından desteklenen olduğundan (daha fazla sorunları bulmak için kodunuzu oluşturmak için bekleniyor) satır bitirdikten sonra bile önce siz yazarken bunlar kodunuzda uyarılar oluşturabilir. Çözümleyiciler de otomatik kod düzeltme temiz kodunuzu hemen izin vermek için Visual Studio ampul istemi üzerinden yüzey.

## <a name="getting-started"></a>Başlarken

[Roslyn Canlı kod çözümleyiciler giriş ve gözden geçirme](https://msdn.microsoft.com/magazine/dn879356.aspx)

[Kod gözden geçirme giderir ekleme: Kullanıcıların düzeltmeleri Çözümleyicisi sorunların belirtin](https://msdn.microsoft.com/magazine/dn904670.aspx)

[Giriş ve gerçek dünya Çözümleyicisi konuşması kılavuz](http://channel9.msdn.com/events/Build/2015/3-725)

[Gerçek dünya Roslyn Çözümleyicisi](../extensibility/roslyn-analyzers-and-code-aware-library-for-immutablearrays.md) olarak izleyebileceğiniz bir [konuşun](http://channel9.msdn.com/events/Build/2015/3-725)

[Üç tür çözümleyiciler gruplandırılır github'da çeşitli örnekler](https://github.com/dotnet/roslyn/blob/master/docs/analyzers/Analyzer%20Samples.md)

[Giriş ve birkaç çözümleyiciler turu](http://channel9.msdn.com/Events/dotnetConf/2015/NET-Compiler-Platform-Roslyn-Analyzers-and-the-Rise-of-Code-Aware-Libraries)

## <a name="see-also"></a>Ayrıca bkz.

- [Roslyn çözümleyiciler genel bakış](../code-quality/roslyn-analyzers-overview.md)
- [Daha fazla belgeler github OSS sitesinde](https://github.com/dotnet/roslyn/tree/master/docs/analyzers)
- [Github'da Roslyn çözümleyiciler ile uygulanan FxCop kuralları](https://github.com/dotnet/roslyn/tree/master/src/Diagnostics/FxCop)