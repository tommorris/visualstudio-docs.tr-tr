---
title: Visual Studio kod stili Tercihler | Microsoft Docs
ms.custom: ''
ms.date: 03/10/2017
ms.technology: vs-ide-general
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.CSharp.Code_Style.General
- VS.ToolsOptionsPages.Text_Editor.Basic.Code_Style.General
ms.workload:
- multiple
ms.openlocfilehash: 4898a2e4a55f5c11179ae5a00e46c87a44519a7b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="code-style-preferences"></a>Kod stili tercihleri

Kod stili Tercihler ayarlanabilir, C# ve Visual Basic projeleri için açarak **seçenekleri** iletişim kutusundan **Araçları** menüsü. Seçin **metin düzenleyici** > **C#** veya **temel** > **kod stili**  >   **Genel**. Bu pencerede seçenekleri yerel makineye geçerlidir. Listedeki her bir öğe seçildiğinde, tercih önizlemesini aşağıda gösterildiği gibi gösterilir.

![Kod stili seçenekleri](media/code-style-quick-actions-dialog.png)

Her öğe için ayarladığınız **tercih** ve **önem** değerlerini her satırda açılır listeleri kullanarak. Önem derecesi ayarlanabilir **hiçbiri**, **öneri**, **uyarı**, veya **hata**. Etkinleştirmek istiyorsanız, [hızlı Eylemler](../ide/quick-actions.md) emin olmak için bir kod stili, **önem** ayar için bir şeyler dışında **hiçbiri**. Hızlı Eylemler ampul simgesini ![küçük ampul simge](media/vs2015_lightbulbsmall.png) görünmez tercih edilmeyen bir stili kullanılır ve otomatik olarak tercih edilen stili için kodu yeniden yazmanız için bir seçenek hızlı Eylemler listesinde seçebilirsiniz.

.NET ile de yönetilebilir için stil ayarlarını kod bir [EditorConfig](../ide/editorconfig-code-style-settings-reference.md) dosya. Bu durumda, EditorConfig dosyasındaki ayarları seçili seçenekler önceliklidir **seçenekleri** iletişim kutusu. Bir EditorConfig dosyası zorlamak ve tüm bağlantıların ya da proje kodlama stili yapılandırmak için kullanabilirsiniz.

### <a name="see-also"></a>Ayrıca bkz.

[Hızlı Eylemler](../ide/quick-actions.md)  
[.NET EditorConfig kuralı ayarlarını kodlama](../ide/editorconfig-code-style-settings-reference.md)