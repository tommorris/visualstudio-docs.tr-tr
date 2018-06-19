---
title: Barındırma süreci (vshost.exe)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- vshost.exe
- hosting process
ms.assetid: c6b9e2be-f18d-4d75-ac52-56d55784734b
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: bba0463870f4d615e45d8f2c11071bfd8a1b8009
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31941957"
---
# <a name="hosting-process-vshostexe"></a>Barındırma süreci (vshost.exe)

Barındırma işlemi, Visual Studio'da, hata ayıklama performansını artırır, kısmi güven hata ayıklamasını etkinleştirir ve tasarım zamanı ifade değerlendirmesi olanak sağlayan bir özelliktir. Barındırma işlemi dosyaları içeren *vshost* dosyasına adı projenizin çıkış klasörüne yerleştirilir. Daha fazla bilgi için bkz: [hata ayıklama ve barındırma işlemi](../debugger/debugging-and-the-hosting-process.md).

> [!NOTE]
> İşlem dosyaları barındırma (*. vshost.exe*) Visual Studio tarafından kullanılacak olan ve doğrudan Çalıştır olmamalıdır veya uygulamanızla birlikte dağıtılabilir.

## <a name="improved-debugging-performance"></a>Hata ayıklama performansı geliştirildi
 Barındırma işlemi bir uygulama etki alanı oluşturur ve hata ayıklayıcı uygulama ile ilişkilendirir. Bu görevleri gerçekleştirmek tanıtmak belirgin bir zamanı hata ayıklama arasındaki gecikme başlatılır ve çalışan uygulamanın zaman başlar. Uygulama etki alanı oluşturma ve hata ayıklayıcı arka planda ilişkilendirme ve uygulama etki alanı kaydetme performansını artırmak barındırma işlemi yardımcı olur ve arasında hata ayıklayıcı durumunu uygulamayı çalıştırır. Uygulama etki alanları hakkında daha fazla bilgi için bkz: [uygulama etki alanları](/dotnet/framework/app-domains/application-domains).

## <a name="partial-trust-debugging"></a>Kısmi güven hata ayıklama
 Kısmi güven uygulama olarak uygulama belirtilen [güvenlik sayfası](../ide/reference/security-page-project-designer.md) , **Proje Tasarımcısı**. Kısmen güvenilen uygulamada hata ayıklama özel başlatma uygulama etki alanının gerektirir. Bu başlatma barındırma işlemi tarafından işlenir.

## <a name="design-time-expression-evaluation"></a>Tasarım zamanı ifade değerlendirmesi
 Tasarım zamanı ifade değerlendirmesi koddan test etmenizi sağlar **hemen** uygulamayı çalıştırmak zorunda kalmadan penceresi. Barındırma işlemi tasarım zamanı ifade değerlendirmesi sırasında bu kodu yürütür. Daha fazla bilgi için bkz: [komut penceresi](../ide/reference/immediate-window.md).

## <a name="see-also"></a>Ayrıca bkz.

- [Hata ayıklama ve barındırma işlemi](../debugger/debugging-and-the-hosting-process.md)
- [Nasıl yapılır: barındırma sürecini devre dışı bırakma](../ide/how-to-disable-the-hosting-process.md)
- [Komut penceresi](../ide/reference/immediate-window.md)
- [Uygulama etki alanları](/dotnet/framework/app-domains/application-domains)