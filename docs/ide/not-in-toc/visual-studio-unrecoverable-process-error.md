---
title: "Visual Studio kurtarılamaz işlem hatası | Microsoft Docs"
ms.custom: 
ms.date: 02/23/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editor
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-general
ms.openlocfilehash: 6964c9e0e1202623d535724f6bc3faff018d948a
ms.sourcegitcommit: f36eb7f989efbdbed0d0a087afea8ffe27d8ca15
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/14/2017
---
# Visual Studio kurtarılamaz işlem hatası

Visual Studio 2017 birkaç işlem dışı işlemler dinamik birim testi gibi gerekli arka plan görevleri çalıştırmak için çözümleyiciler kodunu kullanır. Bu işlemler çıkış yoğun bir kaynak, uzun süre çalışan bir iş çalışmadığı zaman daha hızlı yanıt Visual Studio etkinleştirme gibi Visual Studio performans avantajı vermek için işlem dışı çalıştırılır. Visual Studio 32 bitlik bir işlem olduğundan, ayrıca, işlemler,-işlem dışı çalışan bellek yoğun iş çalışılacak daha büyük bir bellek alanı sağlar.

İşlemler sona erer bunlardan herhangi bir nedenden dolayı gerekli açılır bilgi çubuğu ile aşağıdaki ileti görüntülenir:

"Ne yazık ki, Visual Studio tarafından kullanılan bir işlem kurtarılamaz bir hatayla karşılaştı. Çalışmanızı ve ardından kapatarak ve Visual Studio'yu yeniden başlatmayı kaydetme öneririz."

Bu iletiyi görürseniz, hemen çalışmanızı kaydedin ve kapatın ve Visual Studio'yu yeniden başlatın. Bunu yapmazsanız, herhangi bir anda Visual Studio çökebilir.

## İşlemlerin listesi

Düzgün çalışması Visual Studio için çalıştırmalıdır Visual Studio tarafından kullanılan işlem dışı işlemlerin bir listesi verilmiştir.

- Microsoft.Alm.Shared.Remoting.RemoteContainer.dll
- Microsoft.CodeAnalysis.LiveUnitTesting.EntryPoint
- PerfWatson2.exe
- ServiceHub.Host.Node.x86.exe
- ServiceHub.IdentityHost.exe
- ServiceHub.VSDetouredHost.exe
- ServiceHub.SettingsHost.exe
- ServiceHub.Host.CLR.x86.exe
- ServiceHub.RoslynCodeAnalysisService32.exe
- WindowsAzureGuestAgent.exe
- WindowsAzureTelemetryService.exe
- WaAppAgent.exe
