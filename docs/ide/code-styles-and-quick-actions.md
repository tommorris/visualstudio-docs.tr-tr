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
ms.openlocfilehash: 24470f4fdb1a75d6ebd2743b2ade72e6195842b4
ms.sourcegitcommit: ebe9fb5eda724936f7a059d35d987c29dffdb50d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/07/2017
---
# <a name="code-style-preferences"></a>Kod stili tercihleri

Kod stili Tercihler ayarlanabilir, C# ve Visual Basic projeleri için açarak **seçenekleri** iletişim kutusundan **Araçları** menüsü. Seçin **metin düzenleyici**, **C#** veya **temel**, **kod stili**, **genel**. Bu pencerede seçenekleri yerel makineye geçerlidir. Listedeki her bir öğe seçildiğinde, tercih önizlemesini aşağıda gösterildiği gibi gösterilir.

![Kod stili seçenekleri](media/code-style-quick-actions-dialog.png)

Her öğe için ayarladığınız **tercih** ve **önem** her satırda açılır listeleri kullanma. Önem derecesi ayarlanabilir **hiçbiri**, **öneri**, **uyarı**, veya **hata**, Visual Studio yapılandıran uygun şekilde ve. Kullanmak istiyorsanız, [hızlı Eylemler](quick-actions.md) kod stilleri otomatik olarak tercih edilen stil kodunu yeniden yazmak için bu ayarı için bir şeyler dışında ayarlandığından emin olun **hiçbiri** böylece ampul simgesi ![Küçük ampul simge](media/vs2015_lightbulbsmall.png "VS2017_LightBulbSmall") tercih edilmeyen stilleri kullanıldığında görüntülenir. Bu tercihler sonra ampul simgesini tıklatarak veya basarak uygulanabilir **Ctrl +.** İmleci kod uygun satırında olduğunda.

.NET ile de yönetilebilir stil ayarlarını koduyla bir [EditorConfig](../ide/editorconfig-code-style-settings-reference.md) dosya. Bu durumda, EditorConfig dosyasındaki ayarları seçili seçenekler önceliklidir **seçenekleri** iletişim kutusu. Bir EditorConfig dosyası zorlamak ve tüm bağlantıların ya da proje kodlama stili yapılandırmak için kullanabilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Hızlı Eylemler](quick-actions.md)  
[.NET EditorConfig kuralı ayarlarını kodlama](../ide/editorconfig-code-style-settings-reference.md)