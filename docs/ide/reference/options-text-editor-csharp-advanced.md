---
title: Seçenekler, Metin Düzenleyici, C#, Gelişmiş
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.CSharp.Outlining
- VS.ToolsOptionsPages.Text_Editor.CSharp.Advanced
helpviewer_keywords:
- XML comments
- XML documentation, generating
- outlining options [C#]
- XML documentation, creating
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: a7675d711a4a1df6af4643a459f49b6ef518e5b4
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="options-text-editor-c-advanced"></a>Seçenekler, Metin Düzenleyici, C#, Gelişmiş

Kullanım **Gelişmiş** yeniden düzenleme kod biçimlendirme Düzenleyicisi ayarlarını değiştirmek için seçenekler sayfası ve XML belge açıklamaları için C#. Bu seçenekler sayfası erişmek için kendi seçtikleri **Araçları** > **seçenekleri**ve ardından **metin düzenleyici** > **C#**  >  **Gelişmiş**.

> [!NOTE]
> Gördüğünüz iletişim kutuları ve menü komutları, etkin ayarlarınıza ve ürün sürümüne bağlı olarak Yardım menüsünde açıklanana göre farklılık gösterebilir. Ayarlarınızı değiştirmek için tercih **içeri ve dışarı aktarma ayarları** üzerinde **Araçları** menüsü. Daha fazla bilgi için bkz: [Visual Studio IDE'yi kişiselleştirme](../../ide/personalizing-the-visual-studio-ide.md).

## <a name="analysis"></a>Çözümleme

- Tam çözüm analizini etkinleştir

   Çözümdeki tüm dosyalarda etkinleştirir kod analizi, yalnızca kod dosyaları açın. Daha fazla bilgi için bkz: [tam çözüm analizini](../../code-quality/how-to-enable-and-disable-full-solution-analysis-for-managed-code.md).

- Düzenleyici özelliği çözümlemesi dış işlemde (Deneysel)

## <a name="using-directives"></a>Using yönergelerini

- 'System' yönergeleri kullanımları sıralarken önce yerleştirin

- Yönerge gruplarını kullanarak ayırın

- Başvuru derlemeleri türlerinde kullanımları önerisi

- NuGet paketlerini türlerinde kullanımları önerisi

## <a name="highlighting"></a>Vurgulama

- İmleç sembol yapılan başvurular vurgulayın

   İmleç içinde bir simge konumlandırıldığında ya da bir simge tıklattığınızda, bu simgeyi kod dosyasındaki tüm örneklerini vurgulanır.

- İmleç altında ilişkili anahtar sözcükleri Vurgula

## <a name="outlining"></a>Anahat Oluşturma

- Anahat modu dosyalarını açtığınızda girin

   Seçili olduğunda, otomatik olarak kod daraltılabilir bloklarını oluşturur kod dosyası özetlenmektedir. İlk kez bir dosya açıldığında, #regions blokları ve etkin olmayan kod blokları daraltın.

- Satır ayırıcı yordamı Göster

- Anahat oluşturma bildirimi düzeyli yapıları için Göster

- Anahat oluşturma kodu düzeyli yapıları için Göster

- Yorumlar ve önişlemci bölgeler için anahat oluşturma Göster

- Tanımları için daraltma zaman #regions Daralt

## <a name="fading"></a>Soluklaşan

- Kullanılmayan kullanımları silinerek

- Ulaşılamaz kod silinerek

## <a name="block-structure-guides"></a>Blok yapısı kılavuzları

- Bildirim düzeyli yapıları için kılavuz çizgilerini göster

- Kod düzeyli yapıları için kılavuz çizgilerini göster

## <a name="editor-help"></a>Düzenleyici Yardım

- XML belge açıklamaları için / / / Oluştur

   Yazdıktan sonra seçili olduğunda, XML belge açıklamaları için XML öğeleri ekler `///` açıklama giriş. XML belgeleri hakkında daha fazla bilgi için bkz: [XML belgeleri yorumları (C# programlama Kılavuzu)](/dotnet/csharp/programming-guide/xmldoc/xml-documentation-comments).

- INSERT \* yazarken yeni satır başlangıcında /\* \*/ yorumları

- Yeniden Adlandır izleme için önizleme göster

- Bölünmüş dize değişmez değerleri üzerinde girin

- Rapor geçersiz yer tutucuları ' dizesi. Biçim ' çağrıları

## <a name="extract-method"></a>Ayıklama Yöntemi

- Ref put veya üzerinde özel yapı çıkış yok

## <a name="implement-interface-or-abstract-class"></a>Arabirimi uygulama ya da soyut sınıf

- Özellikleri, olayları ve yöntemleri eklerken, diğer üyeleriyle aynı türde veya sonunda bunları yerleştirin

- Özellikler oluştururken özellikleri atma tercih veya otomatik özellikleri tercih

## <a name="see-also"></a>Ayrıca bkz.

- [Nasıl yapılır: ekleme belgeleri oluşturma için XML açıklamaları](../../ide/reference/generate-xml-documentation-comments.md)
- [XML belgeleri yorumları (C# programlama Kılavuzu)](/dotnet/csharp/programming-guide/xmldoc/xml-documentation-comments)
- [XML açıklamaları (C# Kılavuzu) ile kodunuzu belgeleme](/dotnet/csharp/codedoc)
- [Dile özgü Düzenleyici seçeneklerini ayarlama](../../ide/reference/setting-language-specific-editor-options.md)
- [C# IntelliSense](../../ide/visual-csharp-intellisense.md)