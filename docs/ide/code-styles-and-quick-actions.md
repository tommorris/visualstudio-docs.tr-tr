---
title: Visual Studio kod stili Tercihler | Microsoft Docs
ms.custom: 
ms.date: 03/10/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
author: gewarren
ms.author: gewarren
manager: ghogen
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.CSharp.Code_Style.General
- VS.ToolsOptionsPages.Text_Editor.Basic.Code_Style.General
ms.workload: multiple
ms.openlocfilehash: 741df95afdd7c7e8b6f0ba2de75c1465cd35cc97
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/13/2018
---
# <a name="code-style-preferences"></a>Kod stili tercihleri

Kod stili Tercihler ayarlanabilir, C# ve Visual Basic projeleri için açarak **seçenekleri** iletişim kutusundan **Araçları** menüsü. Seçin **metin düzenleyici** > **C#** veya **temel** > **kod stili**  >   **Genel**. Bu pencerede seçenekleri yerel makineye geçerlidir. Listedeki her bir öğe seçildiğinde, tercih önizlemesini aşağıda gösterildiği gibi gösterilir.

![Kod stili seçenekleri](media/code-style-quick-actions-dialog.png)

Her öğe için ayarladığınız **tercih** ve **önem** değerlerini her satırda açılır listeleri kullanarak. Önem derecesi ayarlanabilir **hiçbiri**, **öneri**, **uyarı**, veya **hata**. Etkinleştirmek istiyorsanız, [hızlı Eylemler](../ide/quick-actions.md) emin olmak için bir kod stili, **önem** ayar için bir şeyler dışında **hiçbiri**. Hızlı Eylemler ampul simgesini ![küçük ampul simge](media/vs2015_lightbulbsmall.png) görünmez tercih edilmeyen bir stili kullanılır ve otomatik olarak tercih edilen stili için kodu yeniden yazmanız için bir seçenek hızlı Eylemler listesinde seçebilirsiniz.

.NET ile de yönetilebilir stil ayarlarını koduyla bir [EditorConfig](../ide/editorconfig-code-style-settings-reference.md) dosya. Bu durumda, EditorConfig dosyasındaki ayarları seçili seçenekler önceliklidir **seçenekleri** iletişim kutusu. Bir EditorConfig dosyası zorlamak ve tüm bağlantıların ya da proje kodlama stili yapılandırmak için kullanabilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Hızlı Eylemler](../ide/quick-actions.md)  
[.NET EditorConfig kuralı ayarlarını kodlama](../ide/editorconfig-code-style-settings-reference.md)