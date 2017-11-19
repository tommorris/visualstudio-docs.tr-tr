---
title: "Kod stilleri ve hızlı Eylemler | Microsoft Docs"
ms.custom: 
ms.date: 03/10/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.devlang: csharp
ms.assetid: 25bb9d99-aeff-4053-925d-2177f5e79574
author: gewarren
ms.author: gewarren
manager: ghogen
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.CSharp.Code_Style.General
- VS.ToolsOptionsPages.Text_Editor.Basic.Code_Style.General
ms.openlocfilehash: d42bb9165748b7282aa42f062b545add62ad1c93
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="code-styles-and-quick-actions"></a>Kod stilleri ve hızlı Eylemler
Kod stili Tercihler ayarlanabilir, C# ve Visual Basic projeleri için açarak **Araçlar > Seçenekleri** penceresi ve ardından seçerek **metin düzenleyicisi > C# / temel > kod Stili > Genel**.  Bu pencerede seçenekleri yerel makineye geçerlidir.  Listedeki her bir öğe seçildiğinde, tercih önizlemesini aşağıda gösterildiği gibi gösterilir.

![Kod stili seçenekleri](media/code-style-quick-actions-dialog.png)

Her öğe için ayarladığınız **tercih** ve **önem** her satırda açılır listeleri kullanma.  Önem derecesi ayarlanabilir **hiçbiri**, **öneri**, **uyarı**, veya **hata**, Visual Studio yapılandıran uygun şekilde ve.  Kullanmak istiyorsanız, [hızlı Eylemler](quick-actions.md) kod stilleri otomatik olarak tercih edilen stil kodunu yeniden yazmak için bu ayarı için bir şeyler dışında ayarlandığından emin olun **hiçbiri** böylece ampul simgesi ![Küçük ampul simge](media/vs2015_lightbulbsmall.png "VS2017_LightBulbSmall") tercih edilmeyen stilleri kullanıldığında görüntülenir.  Bu tercihler sonra ampul simgesini tıklatarak veya basarak uygulanabilir **Ctrl +.** İmleci kod uygun satırında olduğunda.

.NET ile de yönetilebilir stil ayarlarını koduyla bir [EditorConfig](editorconfig-code-style-settings-reference.md) dosya.  Bu durumda, Seçenekleri penceresinde seçili ayarlar geri dönüş ayarlarla Öncelik Alma EditorConfig dosya olacaktır.  Bu dosya zorlamak ve tüm depo veya takım kodlama stili yapılandırmak için kullanabilirsiniz.

## <a name="see-also"></a>Ayrıca Bkz.
* [Hızlı Eylemler](quick-actions.md)