---
title: "Seçenekler, metin düzenleyici, temel (Visual Basic) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VS.ToolsOptionsPages.Visual_Basic.Editor
- VS.ToolsOptionsPages.Text_Editor.Basic.Editor
- VS.ToolsOptionsPages.Visual_Basic_Editor.Editor
- VS.ToolsOptionsPages.Text_Editor.Basic.SimplifiedEditorPage
- VS.ToolsOptionsPages.Text_Editor.Basic
- VS.ToolsOptionsPages.Text_Editor.Basic.VB_Specific
helpviewer_keywords: Basic Text Editor Options dialog box
ms.assetid: 5a8cafca-f7b4-4a2d-92ce-6894a7673d00
caps.latest.revision: "15"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: bc2d31565713e8985074ccf8fab6b9904f52199d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="options-text-editor-basic-visual-basic"></a>Seçenekler, Metin Düzenleyici, Temel (Visual Basic)
**VB belirli** özellik sayfasında **temel** klasöründe **metin düzenleyici** klasöründe **seçenekleri** (**Araçları** menüsü) iletişim kutusu aşağıdaki özellikleri içerir:  
  
 **Uç yapılar otomatik ekleme**  
 Yazdığınızda — Örneğin, ilk satır bir yordam bildiriminin `Sub Main—`ve ENTER tuşuna basın, eşleşen bir metin Düzenleyicisi'ni ekler `End Sub` satır. Benzer şekilde, eklerseniz bir [için](/dotnet/visual-basic/language-reference/statements/for-next-statement) döngü, metin düzenleyici ekler eşleşen bir `Next` deyimi. Bu seçenek belirlendiğinde, Kod düzenleyicisinde son yapı otomatik olarak ekler.  
  
 **Kod asıl listesi (biçimlendirme)**  
 Metin Düzenleyici kodunuzu uygun şekilde yeniden biçimlendirir. Bu seçenek belirlendiğinde, Kod düzenleyicisinde olur:  
  
-   Kodunuzun doğru sekme konumuna hizalayın  
  
-   Anahtar sözcükler, değişkenler ve doğru çalışması için nesneleri recase  
  
-   Eksik ekleme `Then` için bir `If...Then` deyimi  
  
-   İşlev çağrılarını parantez ekleyin  
  
-   Eksik son teklifleri dizelere ekleme  
  
-   Üstel gösterimde yeniden biçimlendirin  
  
-   Tarihleri yeniden biçimlendirin  
  
**Anahat modunu etkinleştir**  
Kod Düzenleyicisi'nde bir dosyayı açtığınızda, belge modu anahat oluşturma görüntüleyebilirsiniz. Bkz: [anahat](../../ide/outlining.md) daha fazla bilgi için. Bu seçenek belirlendiğinde, bir dosyayı açtığınızda özelliği etkinleştirilir.  
  
**Arabirim ve MustOverride üyelerinin otomatik ekleme**  
Ne zaman yürüttükten bir `Implements` deyimi veya bir `Inherits` deyimi bir sınıf için metin düzenleyici ekler prototipleri uygulanan veya geçersiz, sırasıyla üyeler için.  
  
**Satır ayırıcı yordamı Göster**  
Metin Düzenleyici yordamların görsel kapsamını belirtir. Aşağıdaki tabloda listelenen konumlara projenizin .vb kaynak dosyalarında bir çizgi çizilir:  
  
|.Vb kaynak dosya konumu|Satır konumu örneği|  
|---------------------------------|------------------------------|  
|Bir blok bildirimi yapısı Kapat sonra|-Sonunda sınıfı, yapısı, modül, arabirim veya enum<br />-Özelliği, işlev veya alt sonra<br />-Get ve set arasında değil bir özellik yan tümcelerinde|  
|Tek satırlı yapıları bir dizi sonra|-İçeri aktarma deyimlerini sonra bir sınıf dosyası tür tanımında önce<br />-Bir sınıftaki tüm yordamları önce değişkenleri sonra bildirilen|  
|Tek satırlı bildirimlerinden sonra (blok olmayan düzey bildirimleri)|-İçeri aktarma deyimlerini aşağıdaki deyimleri, değişken bildirimleri, olay bildirimleri, temsilci bildirimleri devralır ve DLL bildirme deyimleri|  
  
**Hata düzeltme önerileri etkinleştir**  
Metin düzenleyici, sık karşılaşılan çözümleri önermek ve daha sonra kodunuzda uygulanan uygun düzeltme seçmenize olanak tanır.  
  
**Başvuruları ve anahtar sözcüklerini vurgulama etkinleştir**  
Metin Düzenleyici bir simge tüm örnekleri veya tüm yan tümcesindeki anahtar sözcükler gibi vurgulayın `If..Then`, `While...End While`, veya `Try...Catch...Finally`. CTRL + SHIFT + Aşağı Ok veya CTRL + SHIFT + Yukarı ok tuşlarına basarak vurgulanan başvuruları veya anahtar sözcükleri arasında gidebilirsiniz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
[Genel, ortam, Seçenekler iletişim kutusu](../../ide/reference/general-environment-options-dialog-box.md)   
[Seçenekler, metin düzenleyici, tüm diller, sekmeler](../../ide/reference/options-text-editor-all-languages-tabs.md)