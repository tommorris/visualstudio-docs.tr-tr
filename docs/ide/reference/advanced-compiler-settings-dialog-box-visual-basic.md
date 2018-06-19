---
title: Gelişmiş Derleme Ayarları İletişim Kutusu (Visual Basic)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- vb.ProjectPropertiesAdvancedCompile
helpviewer_keywords:
- Advanced Compiler Settings dialog box
ms.assetid: 1f81133a-293f-4dba-bc1c-8baafb01d857
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 593bb95e45ecdbda14eba49425ce5db08369e6cf
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31948385"
---
# <a name="advanced-compiler-settings-dialog-box-visual-basic"></a>Gelişmiş Derleme Ayarları İletişim Kutusu (Visual Basic)

Kullanım **AdvancedCompiler ayarları** iletişim kutusunun **Proje Tasarımcısı** Proje yapı yapılandırma özelliklerini Gelişmiş belirtmek için. Bu iletişim kutusu, yalnızca Visual Basic projeleri için geçerlidir.

## <a name="to-access-this-dialog-box"></a>Bu iletişim kutusunu erişmek için

1.  İçinde **Çözüm Gezgini**, proje düğümüne seçin (değil **çözüm** düğüm).

2.  Üzerinde **proje** menüsünde tıklatın **özellikleri**. Zaman **Proje Tasarımcısı** görünür, tıklatın **derleme** sekmesi.

3.  Üzerinde [derleme sayfası, Proje Tasarımcısı (Visual Basic)](../../ide/reference/compile-page-project-designer-visual-basic.md)seçin **yapılandırma** ve **Platform**. Basitleştirilmiş yapı yapılandırmaları **yapılandırma** ve **Platform** listelerinde görüntülenmez. Daha fazla bilgi için bkz: [nasıl yapılır: ayarlama hata ayıklama ve yayın yapılandırmaları](../../debugger/how-to-set-debug-and-release-configurations.md).

4.  Tıklatın **Gelişmiş derleme seçenekleri**.

[!INCLUDE[note_settings_general](../../data-tools/includes/note_settings_general_md.md)]

## <a name="optimizations"></a>En iyi duruma getirme

 Bazı durumlarda bir program dosyası küçültmek ve daha hızlı çalıştırın veya derleme işlemi hızlandırmak bir programın en iyi duruma getirme aşağıdaki seçenekleri belirtin.

**Tamsayı taşma denetimleri kaldırma**

Bu onay kutusu, tamsayı taşma denetimi etkinleştirmek için varsayılan olarak işaretli değildir. Tamsayı taşma denetimi kaldırmak için bu onay kutusunu seçin. Bu onay kutusunu seçerseniz, tamsayı hesaplamaları daha hızlı olabilir. Ancak, taşma denetimi ve veri türü kapasiteleri taşma kaldırırsanız, hatalı sonuçlar gerçekleştirilen bir hata depolanabilir.

Taşma koşullar denetlenir ve bir tamsayı işlem taşar, bir <xref:System.OverflowException> özel durumu oluşur. Taşma koşullar denetlenmez, tamsayı işlemi taşan bir özel durum yok.

**En iyi duruma getirme etkinleştir**

Bu onay kutusu, derleyici iyileştirmelerini devre dışı bırakmak için varsayılan olarak işaretli değildir. Derleyici iyileştirmesi etkinleştirmek için bu onay kutusunu seçin. Derleyici en iyi duruma getirme, daha küçük, daha hızlı ve daha verimli çıkış dosyanızın olun. En iyi duruma getirme çıktı dosyasına kod yeniden düzenleme yapılmasını nedeni, ancak derleyici iyileştirmelerini hata ayıklama zorlaştırabilir.

 **DLL temel adres**

 Bu metin kutusunun varsayılan DLL taban adresi onaltılık biçimde görüntüler. Sınıf kitaplığı ve Denetim Kitaplığı projelerinde DLL oluşturulduğunda kullanılacak temel adresini belirtmek için bu metin kutusunu kullanabilirsiniz.

 **Hata ayıklama bilgileri üret**

 Seçin **hiçbiri**, **tam**, veya **yalnızca pdb** listeden. **Hiçbiri** hata ayıklama bilgisi yok'ın oluşturulmasını belirtir. **Tam** hata ayıklama bilgilerini tam oluşturulmasını, belirtir ve **yalnızca pdb** hata ayıklama bilgileri yalnızca PDB üretilmesi gerektiğini belirtir. Bu seçenek için varsayılan değer **tam**.

## <a name="compilation-constants"></a>Derleme sabitleri

Koşullu derleme sabitleri etkisi bir, kullanmanın benzer bir [#Const](/dotnet/visual-basic/language-reference/directives/const-directive) kaynağındaki önişlemci yönergesi dosya, tanımlı sabitler ortak ve projedeki tüm dosyalar için geçerlidir. Koşullu derleme sabitler ile birlikte kullanabileceğiniz [#If... Then... #Else](/dotnet/visual-basic/language-reference/directives/if-then-else-directives) kaynak dosyaları koşullu derleme yönergesi. Bkz: [koşullu derleme](/dotnet/visual-basic/programming-guide/program-structure/conditional-compilation).

 **Hata ayıklama sabiti tanımlayın**

 Varsayılan olarak, bir hata ayıklama sabit ayarlanması belirterek bu onay kutusu seçilidir.

 **İzleme sabiti tanımlayın**

 Varsayılan olarak, bir izleme sabit ayarlanması belirterek bu onay kutusu seçilidir.

 **Özel sabitleri**

 Bu metin kutusunda, uygulamanız için herhangi bir özel sabit girin. Girişleri bu formu kullanarak virgülle ayrılmış: **Ad1 "Value1", ad2 = "Değer2", AD3 = "Değer3" =**.

## <a name="other-settings"></a>Diğer ayarları

**Seri hale getirme derlemeleri oluşturma**

Bu ayar derleyici XML serileştirme derlemelerini oluşturacağını belirtir. Serileştirme derlemelerini başlatma performansını geliştirebilir <xref:System.Xml.Serialization.XmlSerializer> kodunuzda türleri serileştirmek için o sınıfın kullandıysanız. Bu seçenek için varsayılan değer **otomatik**. **Otomatik** yalnızca kullandıysanız, serileştirme derlemelerini oluşturulmasını belirtir <xref:System.Xml.Serialization.XmlSerializer> kodunuzda XML türleri kodlamak için. **Kapalı** serileştirme derlemelerini hiçbir zaman, kodunuzu kullanıp kullanmadığını bağımsız olarak oluşturulmasını belirtir <xref:System.Xml.Serialization.XmlSerializer>. **Üzerinde** serileştirme derlemelerini her zaman oluşturulması gerektiğini belirtir. Serileştirme derlemelerini adlı `TypeName`. XmlSerializers.dll.

## <a name="see-also"></a>Ayrıca bkz.

- [Derleme Sayfası, Proje Tasarımcısı (Visual Basic)](../../ide/reference/compile-page-project-designer-visual-basic.md)