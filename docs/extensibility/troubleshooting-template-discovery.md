---
title: "Visual Studio şablon bulma sorunlarını giderme | Microsoft Docs"
ms.custom: 
ms.date: 01/02/2018
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 72663d56844fcc34164e9408ab14c8ead234683e
ms.sourcegitcommit: 9357209350167e1eb7e50b483e44893735d90589
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/05/2018
---
# <a name="troubleshooting-template-installation"></a>Şablon yükleme sorunlarını giderme

Proje veya öğe şablonları dağıtma sorunlarla karşılaşırsanız, tanılama günlük kaydını etkinleştirebilirsiniz.

1. (Örneğin C:\Program Files (x86) \Microsoft Visual Studio\2017\Enterprise\Common7\IDE\CommonExtensions\EnablePkgDefLogging.pkgdef) yüklemeniz için bir pkgdef dosyası Common7\IDE\CommonExtensions klasöründe aşağıdaki içeriğe sahip oluşturun:

    ```
    [$RootKey$\VsTemplate]
    "EnableTemplateDiscoveryLog"=dword:00000001
    ```

1. Windows aramasında arayarak yüklemenizin "Geliştirici komut istemi" açın ve çalıştırın `devenv /updateConfiguration`.

1. Visual Studio'yu başlatın ve her iki şablon ağaçları başlatmak için yeni proje ve yeni öğe iletişim kutuları başlatın. Şablon günlük görüntülenir **%LOCALAPPDATA%\Microsoft\VisualStudio\15.0_[instanceid]\VsTemplateDiagnosticsList.csv** (Visual Studio örneğiniz yükleme Kimliğini InstanceId karşılık gelir). Her şablon ağaç başlatma için bu günlük girdileri ekler.

Günlük dosyası şu sütunları içerir:

- **FullPathToTemplate**, aşağıdaki değerleri vardır:

    - bildirim tabanlı bir dağıtım için 1

    - disk tabanlı bir dağıtım için 0

- **TemplateFileName**

- Diğer şablonu özellikleri

> [!NOTE]
> Günlüğünü devre dışı bırakma pkgdef dosyayı kaldırın veya değerini değiştirmek `EnableTemplateDiscoveryLog` için `dword:00000000`ve ardından çalıştırın `devenv /updateConfiguration` yeniden.

## <a name="see-also"></a>Ayrıca bkz.

[Özel proje ve öğe şablonları oluşturma](creating-custom-project-and-item-templates.md)