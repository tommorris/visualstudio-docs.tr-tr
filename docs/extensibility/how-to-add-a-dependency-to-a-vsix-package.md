---
title: 'Nasıl yapılır: VSIX paketi için bağımlılık ekleme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- package reference
- package assembly
- package dll
- vsix reference
ms.assetid: 8f20177b-dab9-43a3-b959-81a591b451d6
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 0704a72ba70e2a00baab99d327702ec6c08f1775
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-add-a-dependency-to-a-vsix-package"></a>Nasıl yapılır: VSIX paketi için bağımlılık ekleme

Hedef bilgisayarda mevcut olmayan bağımlılıkları yükler VSIX paketi dağıtımı ayarlayabilirsiniz. Bunu gerçekleştirmek için source.extension.vsixmanifest dosyaya VSIX bağımlılıkları ekleyin.

## <a name="to-add-a-dependency"></a>Bir bağımlılık eklemek için

1. Source.extension.vsixmanifest dosyasında açma **tasarım** görünümü. Git **bağımlılıkları** sekmesinde **yeni**.

2. Yüklü bir uzantı eklemek için: içinde **yeni bağımlılık Ekle** iletişim kutusunda **yüklü uzantısı** ve daha sonra **adı**, listesindeki bir uzantı seçin.

3. Yüklü olmayan başka bir VSIX eklemek için:: içinde **yeni bağımlılık Ekle** iletişim kutusunda **dosyasının dosya sistemindeki** ve sonra da **Gözat** düğmesine tıklayarak VSIX seçin.

## <a name="require-a-specific-visual-studio-release"></a>Belirli bir Visual Studio sürümünü gerektirir

Uzantınızın Visual Studio 2017 belirli bir sürümünü gerektiriyorsa, örneğin, 15.3 serbest bir özellik bağlıdır, yapı numarası, içinde VSIX içine belirtebilirsiniz **InstallationTarget**. Örneğin, yayın 15.3 '15.0.26730.3' derleme sayısı vardır. Yapı numaralarını sürümlerini eşleme görebilirsiniz [burada](../install/visual-studio-build-numbers-and-release-dates.md). '15.3' sürüm numarasını kullanarak düzgün çalışmayacağına dikkat edin.

Uzantınızı 15.3 gerektirir veya üzeri, bildirmek **InstallationTarget sürüm** olarak [15.0.26730.3, 16.0):

```xml
<Installation>
  <InstallationTarget Id="Microsoft.VisualStudio.Community" Version="[15.0.26730.3, 16.0)" />
</Installation>
```

VSIXInstaller, Visual Studio'nun önceki sürümleri algılar ve kullanıcı bir sonraki güncelleştirme gerekli olduğunu bildiren.


## <a name="see-also"></a>Ayrıca Bkz.

 [VSIX uzantı şema 1.0 başvurusu](http://msdn.microsoft.com/en-us/76e410ec-b1fb-4652-ac98-4a4c52e09a2b) [VSIX paketi anatomisi](../extensibility/anatomy-of-a-vsix-package.md) [uzantıları Windows Installer dağıtımı için hazırlama](../extensibility/preparing-extensions-for-windows-installer-deployment.md)