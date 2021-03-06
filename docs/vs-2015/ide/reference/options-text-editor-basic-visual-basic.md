---
title: Seçenekler, metin düzenleyici, temel (Visual Basic) | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- VS.ToolsOptionsPages.Visual_Basic.Editor
- VS.ToolsOptionsPages.Text_Editor.Basic.Editor
- VS.ToolsOptionsPages.Visual_Basic_Editor.Editor
- VS.ToolsOptionsPages.Text_Editor.Basic.SimplifiedEditorPage
- VS.ToolsOptionsPages.Text_Editor.Basic
- VS.ToolsOptionsPages.Text_Editor.Basic.VB_Specific
helpviewer_keywords:
- Basic Text Editor Options dialog box
ms.assetid: 5a8cafca-f7b4-4a2d-92ce-6894a7673d00
caps.latest.revision: 20
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 79a870cc05f7892519f34b2091c5a3520ddbc120
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42674815"
---
# <a name="options-text-editor-basic-visual-basic"></a>Seçenekler, Metin Düzenleyici, Temel (Visual Basic)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [seçenekler, metin düzenleyici, temel (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/options-text-editor-basic-visual-basic).  
  
  
**VB belirli** özellik sayfasında **temel** klasörü **metin düzenleyici** klasörü **seçenekleri** (**araçları** menüsü) iletişim kutusu aşağıdaki özellikleri içerir:  
  
 **Bitiş yapılarını otomatik ekleme**  
 Yazdığınızda — Örneğin, bir yordam bildirimi ilk satırını `Sub Main—`ve ENTER tuşuna basın, eşleşen bir metin düzenleyicisi ekler `End Sub` satır. Benzer şekilde, eklerseniz bir [için](http://msdn.microsoft.com/library/f5fc0d51-67ce-4c36-9f09-31c9a91c94e9) döngüsü, metin düzenleyici ekler eşleşen `Next` deyimi. Bu seçenek belirlendiğinde, Kod Düzenleyicisi bitiş yapısı otomatik olarak ekler.  
  
 **Kodu düzgün listeleme (yeniden biçimlendirme)**  
 Metin düzenleyici, uygun şekilde kodunuzu yeniden biçimlendirir. Bu seçenek belirlendiğinde, Kod Düzenleyici olur:  
  
-   Kodunuz doğru sekme konumuna Hizala  
  
-   Anahtar sözcükler, değişkenler ve doğru çalışması için nesneler recase  
  
-   Eksik ekleme `Then` için bir `If...Then` deyimi  
  
-   İşlev çağrıları için parantez ekleyin  
  
-   Bitiş tırnak işaretleri eksik dizelere ekleme  
  
-   Üstel gösterim yeniden biçimlendirin  
  
-   Tarihleri yeniden biçimlendirin  
  
 **Anahat oluşturma modunu etkinleştir**  
 Kod Düzenleyicisi'nde bir dosyayı açtığınızda, belge anahat modunda görüntüleyebilirsiniz. Bkz: [anahat](../../ide/outlining.md) daha fazla bilgi için. Bu seçenek belirlendiğinde, bir dosyayı açtığınızda anahat oluşturma özelliği etkinleştirilir.  
  
 **Interface ve MustOverride üyelerinin otomatik ekleme**  
 İşlerseniz bir `Implements` deyimi veya bir `Inherits` ifadesi için bir sınıf, metin düzenleyici ekler prototipleri uygulanan ya da geçersiz, sırasıyla sahip üyeler için.  
  
 **Yordam satır ayıraçlarını Göster**  
 Metin düzenleyici, yordamların görsel kapsamını belirtir. Bir çizgi, aşağıdaki tabloda listelenen konumlara projenizin .vb kaynak dosyalarında çizilir:  
  
|.Vb kaynak dosya konumu|Satır konumu örneği|  
|---------------------------------|------------------------------|  
|Sonra bir blok bildirimi yapısı kapatma|-Sonunda sınıfı, yapısı, modülü, arabirim veya numaralandırma<br />-Özelliği, işlev veya alt after<br />-Get ve set değil arasında bir özellikte yan tümceleri|  
|Tek satır yapıları bir dizi sonra|-İçeri aktarma deyimlerini after, önce bir sınıf dosyası içinde bir tür tanımı<br />-Bir sınıftaki tüm yordamları önce tanımlanan değişkenleri after|  
|Tek satır bildirimlerinden sonra (blok düzey bildirimleri)|-İçeri aktarma deyimlerini aşağıdaki deyimleri, değişken bildirimleri, olay bildirimleri, temsilci bildirimleri devralır ve DLL ifadeleri bildirme|  
  
 **Hata düzeltme önerilerini etkinleştirmek**  
 Metin düzenleyici, sık karşılaşılan çözümler önermek ve uygun düzeltmeyi kodunuza sonra uygulanır seçmenize olanak tanır.  
  
 **Başvuruları ve anahtar sözcükleri vurgulamasını etkinleştirmenin**  
 Metin Düzenleyicisi gibi bir simgenin tüm örnekleri veya tüm yan tümcesindeki anahtar sözcüklerin vurgulayabilirsiniz `If..Then`, `While...End While`, veya `Try...Catch...Finally`. CTRL + SHIFT + Aşağı Ok veya CTRL + SHIFT + Yukarı ok tuşlarına basarak vurgulanan başvurulara veya anahtar sözcükleri arasında gezinebilirsiniz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Genel, ortam, Seçenekler iletişim kutusu](../../ide/reference/general-environment-options-dialog-box.md)   
 [Seçenekler, metin düzenleyici, tüm diller, sekmeler](../../ide/reference/options-text-editor-all-languages-tabs.md)



