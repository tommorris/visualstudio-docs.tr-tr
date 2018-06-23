---
title: Bir işlem kurtarılamaz bir hatayla karşılaştı
ms.date: 06/22/2018
ms.topic: troubleshooting
helpviewer_keywords:
- unrecoverable error
- error, process
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.workload:
- multiple
ms.openlocfilehash: ebd530b9db139cb232f735f7d6401199cab2f6fd
ms.sourcegitcommit: e6b13898cfbd89449f786c2e8f3e3e7377afcf25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/22/2018
ms.locfileid: "36325708"
---
# Visual Studio kurtarılamaz işlem hatası

Visual Studio 2017 birkaç işlem dışı işlemler dinamik birim testi gibi gerekli arka plan görevleri çalıştırmak için çözümleyiciler kodunu kullanır. Bu işlemler çıkış uzun, kaynak yoğunluklu işler çalışırken daha hızlı yanıt Visual Studio etkinleştirme gibi Visual Studio performans avantajı vermek için işlem dışı çalıştırılır. Visual Studio 32 bitlik bir işlem olduğundan, ayrıca, işlemler,-işlem dışı çalışan bellek yoğun iş çalışılacak daha büyük bir bellek alanı sağlar.

Varsa *ServiceHub.RoslynCodeAnalysisService.exe* veya *ServiceHub.RoslynCodeAnalysisService32.exe* işlem sona erer herhangi bir nedenle açılır bilgi çubuğu aşağıdaki ileti görüntülenir:

**"Ne yazık ki, Visual Studio tarafından kullanılan bir işlem kurtarılamaz bir hatayla karşılaştı. Çalışmanızı ve ardından kapatarak ve Visual Studio'yu yeniden başlatmayı kaydetme öneririz."**

Bu iletiyi görürseniz, çalışmanızı kaydedin ve kapatın ve Visual Studio'yu yeniden başlatın.

## İşlemlerin listesi

Visual Studio tarafından kullanılan işlem dışı işlemlerin bir listesi verilmiştir. Bu listesi belirli iş akışları veya senaryolar başlatma işlemleri planlayacak ve böylece çoğu durumda bunlar tüm aynı anda çalıştırmıyor.

- Microsoft.Alm.Shared.Remoting.RemoteContainer.dll
- Microsoft.CodeAnalysis.LiveUnitTesting.EntryPoint
- PerfWatson2.exe
- ServiceHub.Host.Node.x86.exe
- ServiceHub.IdentityHost.exe
- ServiceHub.VSDetouredHost.exe
- ServiceHub.SettingsHost.exe
- ServiceHub.Host.CLR.x86.exe
- ServiceHub.RoslynCodeAnalysisService32.exe
- ServiceHub.RoslynCodeAnalysisService.exe
- WindowsAzureGuestAgent.exe
- WindowsAzureTelemetryService.exe
- WaAppAgent.exe

Bu işlemlerden biri sona ererse beklenmedik bir şekilde, Visual Studio içinde bazı işlevler çalışmayı durdurur. Bazı işlemler için işlev kaybı Önemsiz olabilir. Başkalarının, Visual Studio kararlılığını etkilenir ve bir hata iletisi görüntülenir.