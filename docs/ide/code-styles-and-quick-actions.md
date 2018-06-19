---
title: Visual Studio kod stili tercihleri
ms.date: 03/10/2017
ms.prod: visual-studio-dev15
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
ms.openlocfilehash: 6dd046fa8a01cde7abdc33484da3ff8227eda966
ms.sourcegitcommit: 046a9adc5fa6d6d05157204f5fd1a291d89760b7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/11/2018
ms.locfileid: "34063690"
---
# <a name="code-style-preferences"></a>Kod stili tercihleri

Kod stili Tercihler ayarlanabilir, C# ve Visual Basic projeleri için açarak **seçenekleri** iletişim kutusundan **Araçları** menüsü. Seçin **metin düzenleyici** > **C#** veya **temel** > **kod stili**  >   **Genel**. Bu pencerede seçenekleri yerel makineye geçerlidir.

Listedeki her bir öğe seçildiğinde tercih önizlemesini gösterir:

![Kod stili seçenekleri](media/code-style-quick-actions-dialog.png)

## <a name="preference-and-severity"></a>Tercih ve önem derecesi

Her öğe için ayarladığınız **tercih** ve **önem** değerlerini aşağı açılan listeler her satırda kullanarak. Önem derecesi ayarlanabilir **hiçbiri**, **öneri**, **uyarı**, veya **hata**. Etkinleştirmek istiyorsanız, [hızlı Eylemler](../ide/quick-actions.md) emin olmak için bir kod stili, **önem** ayar için bir şeyler dışında **hiçbiri**. Hızlı Eylemler ampul simgesini ![küçük ampul simge](media/vs2015_lightbulbsmall.png) apspear tercih edilmeyen bir stili kullanıldığında ve otomatik olarak tercih edilen stili için kodu yeniden yazmanız için bir seçenek hızlı Eylemler listesinde seçebilirsiniz.

## <a name="editorconfig-files"></a>EditorConfig dosyaları

.NET ile de yönetilebilir için stil ayarlarını kod bir [EditorConfig](../ide/editorconfig-code-style-settings-reference.md) dosya. EditorConfig dosyasındaki ayarları önceliklidir seçili Seçenekler **seçenekleri** iletişim kutusu. Bir EditorConfig dosyası zorlamak ve tüm bağlantıların ya da proje kodlama stili yapılandırmak için kullanabilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

- [Hızlı Eylemler](../ide/quick-actions.md)
- [.NET EditorConfig kuralı ayarlarını kodlama](../ide/editorconfig-code-style-settings-reference.md)