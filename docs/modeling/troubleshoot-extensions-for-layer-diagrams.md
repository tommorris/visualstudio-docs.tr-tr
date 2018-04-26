---
title: Uzantıları bağımlılık diyagramları için sorun giderme
ms.date: 11/04/2016
ms.topic: troubleshooting
helpviewer_keywords:
- dependency diagrams, extension errors
- dependency diagrams, troubleshooting extensions
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: b56ccd587df4a830eab5bee000cafcc02b0031e8
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="troubleshoot-extensions-for-dependency-diagrams"></a>Uzantıları bağımlılık diyagramları için sorun giderme

Bu konu, model uzantılarını katman oluşturduğunuzda, karşılaşabileceğiniz bazı sorunları giderir.

## <a name="when-i-press-f5-to-debug-my-extension-my-commands-gesture-handlers-validation-extensions-or-custom-properties-do-not-appear-on-dependency-diagrams-in-the-experimental-instance-of-includevsprvscode-qualityincludesvsprvsmdmd"></a>My uzantısı hata ayıklamak için F5 tuşuna bastığınızda, komutları, hareket işleyicileri, doğrulama uzantıları veya özel özellikler deneysel örneğinde bağımlılık diyagramlarındaki görünmez [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]

1.  Deneysel örneğinde uzantısı çözümünüzü açın [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]ve **yapı** menüsünde tıklatın **çözümü yeniden derle**.

2.  Tuşuna **F5** veya **CTRL + F5** deneysel örneği başlatmak için [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Bir bağımlılık diyagramı açın ve uzantınızı sınayın.

 Gerekirse, bir sonraki yordama devam edin.

## <a name="an-old-version-of-my-extension-runs"></a>My uzantısı'nın eski bir sürümünü çalıştırır.

1.  Olduğundan emin olun deneysel örneği [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] çalışıyor.

2.  Aşağıdaki klasörü silin: %LocalAppData%\Microsoft\VisualStudio\\[sürüm] \ComponentModelCache

    > [!NOTE]
    > % LocalAppData olan genellikle *DriveName*: \Users\\*kullanıcıadı*\AppData\Local.

 Gerekirse, bir sonraki yordama devam edin.

## <a name="an-old-version-of-my-validation-results-appears-or-my-validation-method-is-not-called"></a>My doğrulama sonuçlarını eski bir sürümü görüntülenir veya my doğrulama yöntemi çağrılmaz.

1.  Deneysel örneğinde [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], **yapı** menüsünde tıklatın **temiz çözüm**. Önbelleğe alınan sonuçları önceki doğrulama analiz temizler.

2.  Modelinizi Katmanlar kod öğeleri ile ilişkili olduğunu ve modelde en az bir bağımlılık bağlantısı olduğundan emin olun. Doğrulama çağrılır varsa doğrulamak için hiçbir şey.

3.  Ayrı bir işlemde çalıştığından normal kesme noktaları doğrulama yönteminde çalışmayabilir. Çağrı eklemelisiniz `System.Diagnostics.Debugger.Launch()` yönteminizi adım istiyorsanız.

4.  İçinde **source.extension.vsixmanifest** katman doğrulama projenizde her ikisi de eklediğinizden emin olun bir **MEF Bileşeni** öğesi ve bir **özel uzantı türü** altında öğesi **İçerik**.

## <a name="see-also"></a>Ayrıca Bkz.

- [Bağımlılık diyagramlarını genişletme](../modeling/extend-layer-diagrams.md)
