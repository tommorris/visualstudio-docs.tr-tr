---
title: "Visual Studio kodlama ve satır sonu karakterleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.Encoding
helpviewer_keywords:
- line breaks
- encoding
- Visual Studio, encoding
- editors, line breaks
- line break characters
- Visual Studio, line break characters
ms.assetid: 8f9b3ffc-7b8d-44f4-87cb-dc29105be12d
caps.latest.revision: "8"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 8a472a09a4d4d67f59d7879d03b466932d1445e6
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="encodings-and-line-breaks"></a>Kodlamalar ve Satır Sonları
Visual Studio'da satır sonları gibi karakterlerden yorumlanır:  
  
-   Satır başı + satır besleme CR LF:, 000 D + 000A Unicode karakter  
  
-   LF: satır besleme, Unicode karakter 000A  
  
-   No: Sonraki satırında, Unicode karakter 0085  
  
-   LS: Satır ayırıcı, Unicode karakter 2028  
  
-   PS: Paragraf ayırıcı, Unicode karakter 2029  
  
Diğer uygulamalardan kopyalanan metni özgün kodlama ve satır sonu karakterleri tutar. Örneğin, Not Defteri'nden metni kopyalayın ve Visual Studio bir metin dosyasına yapıştırın, metni Not Defteri'nde vardı aynı ayarlara sahip.  
  
Farklı bir satır sonu karakterleri içeren bir dosyayı açtığınızda, tutarsız satır sonu karakterleri normalleştirilmiş ve seçmek için hangi tür satır sonları olup olmadığını soran bir iletişim kutusu görebilirsiniz.

Kullanabileceğiniz **dosya**, **Gelişmiş kaydetme seçenekleri** iletişim kutusunu istediğiniz satır sonu karakterleri türü belirlenemedi. Ayrıca, aynı ayarlarla bir dosyanın kodlamasını değiştirebilirsiniz.

![Gelişmiş Kaydetme Seçenekleri iletişim kutusu](media/line_endings.png)
  
> [!NOTE]
>  Görmüyorsanız, **Gelişmiş kaydetme seçenekleri** üzerinde **dosya** menüsünde, ekleyebilir. Seçin **Araçları**, **Özelleştir...** ve ardından **komutları** sekmesi. İçinde **menü çubuğu** aşağı açılan listesinde, seçin **dosya**, ardından **komut Ekle...**  düğmesi. İçinde **Add komutunu** iletişim kutusunda **kategorileri**, seçin **dosya**ve ardından **komutları** listesinde, seçin  **Gelişmiş Seçenekleri...** . Seçin **Tamam** ve ardından **Aşağı Taşı** menüsünden herhangi bir yere komutu taşımak için düğmesi. Seçin **kapatmak** kapatmak için **Özelleştir** iletişim kutusu. Daha fazla bilgi için bkz: [menüleri ve araç çubuklarını özelleştirme](../ide/how-to-customize-menus-and-toolbars-in-visual-studio.md#customizing_menu).

Alternatif olarak, erişim **Gelişmiş kaydetme seçenekleri** seçerek iletişim kutusu **dosya**, **kaydetmek \<dosya\> olarak...** . İçinde **dosyasını Farklı Kaydet** iletişim kutusunda, açılır üçgen seçin **kaydetmek** düğmesini tıklatın ve seçin **kodlama ile Kaydet...** .

## <a name="see-also"></a>Ayrıca bkz.
[Kod Düzenleyicisi'nde yazma](../ide/writing-code-in-the-code-and-text-editor.md)