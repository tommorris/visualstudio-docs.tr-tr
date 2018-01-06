---
title: "Kod parçacığı Seçici | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.expansionpicker
helpviewer_keywords:
- Code Snippet Picker
- IntelliSense code snippets, Code Snippet Picker
- code snippets, Code Snippet Picker
ms.assetid: f0862d48-fbbc-4cfe-b228-24492d5c89c4
caps.latest.revision: "25"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: e352baf834f026462cb35921f7f79e75b3aecd96
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="code-snippet-picker"></a>Kod Parçacığı Seçici
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Kod düzenleyicisinde sağlayan bir **kod parçacığı Seçici** sağlayan, etkin belgeye hazır kod bloklarını eklemek için birkaç kere fareyi tıklatarak içinde.  
  
 Görüntülenecek yordamı **kod parçacığı Seçici** kullanmakta olduğunuz dile göre değişir.  
  
-   [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)]-İstediğiniz konuma kod kısayol menüsünü görüntülemek için Düzenleyicisi'nde sağ tıklatın ve seçin **Ekle parçacığı**.  
  
-   [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)]-İstediğiniz konuma kod kısayol menüsünü görüntülemek için Düzenleyicisi'nde sağ tıklayın ve **Ekle parçacığı** veya **Surround With**.  
  
-   [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)]- **Kod parçacığı Seçici** kullanılabilir değil.  
  
-   Visual F # - **kod parçacığı Seçici** kullanılabilir değil.  
  
-   [!INCLUDE[jsprjscript](../../debugger/debug-interface-access/includes/jsprjscript_md.md)]--İstenen konuma kod kısayol menüsünü görüntülemek için Düzenleyicisi'nde sağ tıklayın ve **Ekle parçacığı** veya **Surround With**.  
  
-   XML - istediğiniz konuma kod kısayol menüsünü görüntüle öğesini tıklatıp Düzenleyicisi'nde sağ **Ekle parçacığı** veya **Surround With**.  
  
-   HTML - istediğiniz konuma kod kısayol menüsünü görüntüle öğesini tıklatıp Düzenleyicisi'nde sağ **Ekle parçacığı** veya **Surround With**.  
  
-   SQL - istediğiniz konuma kod kısayol menüsünü görüntüle öğesini tıklatıp Düzenleyicisi'nde sağ **Ekle parçacığı**.  
  
Çoğu Visual Studio geliştirme dillerde kullandığınız **kod parçacıkları Yöneticisi** klasörlere eklemek için **klasör listesi** , **kod parçacığı Seçici** tarar XML için Parçacık dosyaları. Listeye eklemek için kendi parçacıkları de oluşturabilirsiniz. Daha fazla bilgi için bkz: [izlenecek yol: kod parçacığı oluşturma](../../ide/walkthrough-creating-a-code-snippet.md).  
  
## <a name="uielement-list"></a>UIElement Listesi  
Öğe adı  
Seçili öğenin adını görüntüleyen düzenlenebilir bir metin alanı **öğe listesi**. İstediğiniz öğeyi için artımlı bir arama yapmak için bu alanda adını yazmaya başlayın. İstenen öğe içinde seçilene kadar harf eklemeye devam **öğe listesi**.  
  
Öğe listesi  
Kod parçacıkları ekleme ya da kod parçacıkları içeren klasörlerin listesini için kullanılabilir bir listesi. Bir parçacığını eklemek veya bir klasörü genişletmek için istediğiniz ve Enter tuşuna basın öğeyi seçin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
[Kod parçacıkları için en iyi uygulamalar](../../ide/best-practices-for-using-code-snippets.md)   
[Visual Basic IntelliSense kodu parçacıkları](/dotnet/visual-basic/developing-apps/using-ide/intellisense-code-snippets)   
[Kodda yer işaretleri ayarlama](../../ide/setting-bookmarks-in-code.md)   
[Nasıl Yapılır: Şununla Çevrele Kod Parçacıklarını Kullanma](../../ide/how-to-use-surround-with-code-snippets.md)