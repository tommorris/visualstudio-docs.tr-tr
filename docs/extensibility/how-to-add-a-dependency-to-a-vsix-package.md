---
title: "Nasıl yapılır: VSIX paketi için bağımlılık ekleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- package reference
- package assembly
- package dll
- vsix reference
ms.assetid: 8f20177b-dab9-43a3-b959-81a591b451d6
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 27fbf8c079ca1270074d7cae683ef6f8127e2a5a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
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