---
title: "İzlenecek yol: XML Düzenleyicisi özelliklerini kullanma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ea8dc357-2e66-455a-aec2-7ccaccfc9adf
caps.latest.revision: "2"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: bf90df0e5311cb1487334ba3851c5083030e2191
ms.sourcegitcommit: c0422a3d594ea5ae8fc03f1aee684b04f417522e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/02/2017
---
# <a name="walkthrough-using-xml-editor-features"></a>İzlenecek yol: XML Düzenleyicisi özelliklerini kullanma
Bu izlenecek adımları yeni bir XML belgesi nasıl oluşturacağınızı gösterir. İzlenecek yol da XML yazmak için değerli kılan özelliklerin bir XML Düzenleyicisi'nin kullanır.  
  
> [!NOTE]
>  Yönergelere başlamadan önce (aşağıda bu konuya da dahil) hireDate.xsd dosyayı yerel bilgisayarınıza kaydedin.  
  
### <a name="to-create-a-new-xml-file-and-associate-it-with-an-xml-schema"></a>Yeni bir XML dosyası oluşturmak ve bir XML şeması ile ilişkilendirmek için  
  
1.  Üzerinde **dosya** menüsündeki **yeni**, tıklatıp **dosya**.  
  
2.  Seçin **XML dosyası** içinde **şablonları** bölmesinde ve tıklatın **açık**.  
  
     Yeni bir dosya Düzenleyicisi'nde açılır. Varsayılan XML bildirimi dosyayı içeren `<?xml version="1.0" encoding="utf-8">`.  
  
3.  Belge Özellikleri penceresinde Gözat düğmesine (**...** ) üzerinde **şemaları** alan.  
  
     **XSD şemaları** iletişim kutusu görüntülenir.  
  
4.  **Ekle**'yi tıklatın.  
  
     **Açık XSD şema** iletişim kutusu görüntülenir.  
  
5.  HireDate.xsd dosyasını tıklatıp **açık**.  
  
6.  **Tamam**'ı tıklatın.  
  
     XML Şeması sunulmuştur XML belgesi ile ilişkilendirilmiş. XML Şeması belgesi doğrulamak için kullanılır. Bu ayrıca, IntelliSense tarafından geçerli öğeleri üye listesini doldurmak için kullanılır.  
  
### <a name="to-add-data"></a>Veri eklemek için  
  
1.  Tür `<` Düzenleyicisi bölmesinde.  
  
     Üye listesi olası öğeleri görüntüler:  
  
    -   **!--** bir yorum ekleyin.  
  
    -   **! DOCTYPE** bir belge türü eklemek için.  
  
    -   **?** bir işlem yönergesi eklemek için.  
  
    -   **çalışan** kök öğesi eklemek için.  
  
2.  Seçin **<!--** bir açıklama düğümü ekleyin ve ENTER tuşuna basın.  
  
     Düzenleyici, açıklama bitiş etiketi ekler ve imleci başlangıç ve bitiş yorum etiketleri arasına yerleştirir.  
  
3.  Yazın **Test XML dosyası**.  
  
4.  Yeni bir satıra yazın `<`seçip **çalışan** üye listesinden.  
  
     Düzenleyici bir XML öğesi ekler `<employee`. Bu noktada öznitelikleri öğesine ekleyebilir veya yazarak başlangıç etiketi kapatabilirsiniz `>`.  
  
5.  Tür `>` etiket kapatın.  
  
6.  Düzenleyici bitiş etiketi ekler. Bitiş etiketi bir doğrulama hatası gösteren dalgalı alt çizgi ile eklenir. Araç İpucu iletisini görüntüler: içeriği eksik 'çalışanı' öğesine sahip. 'ID' bekleniyor.  
  
7.  Tür `<` seçip **kimliği** üye listesinden. Yazın `>`.  
  
     Düzenleyici XML öğesi ekler `<ID></ID>`ve imleci kimliği başlattıktan sonra etiketi yerleştirir.  
  
8.  Tür **abc**.  
  
     **Abc** metin dalgalı alt çizgiyle sahiptir. Araç İpucu iletisini görüntüler: 'ID' öğesi kendi veri türüne göre geçersiz bir değere sahip.  
  
9. Kimliği öğesini sağ tıklatın ve seçin **Tanıma Git**.  
  
     Düzenleyici hireDate.xsd dosyanın yeni bir belge penceresi açar ve imleci kimliği şema öğesi tanımını konumlandırır.  
  
10. XML dosyasına dönmek ve Değiştir **abc** metinle **123**.  
  
     Dalgalı alt çizgi ve araç ipucu kimliği öğesi değerin altında temizlenir. Çalışan bitiş etiketi için araç ipucu şimdi iletisini görüntüler: içeriği eksik 'çalışanı' öğesine sahip. Beklenen 'işe alma-date'.  
  
11. İmleci kimliği Bitiş etiketinden sonra yerleştirin, yazın `<`, işe alma tarihi üye listesinden seçin ve ardından yazın `>`.  
  
     Düzenleyici XML öğesi ekler `<hire-date></hire-date>`ve işe alma tarihi başlattıktan sonra etiketi imleci yerleştirir.  
  
12. Yazın **2003-01-10** işe alma tarihi değeri.  
  
### <a name="to-format-the-xml-document"></a>XML belgesi biçimlendirmek için  
  
- Seçin **belgeyi Biçimlendir** XML Düzenleyicisi araç çubuğu düğmesinden.
  
    XML belgesi biçimlendirilir.  
  
### <a name="to-save-the-xml-document"></a>XML belgesi kaydetmek için  
  
1.  Gelen **dosya** menüsünde, select **Kaydet**.  
  
     **Dosyasını Farklı Kaydet** iletişim kutusu görüntülenir. Varsayılan dosya adı 'XMLFile1' dir.  
  
2.  XML belgesi için konum ve dosya adı girin ve tıklayın **kaydetmek**.  
  
## <a name="hiredatexsd-file"></a>hireDate.xsd dosyası  
 Aşağıdaki şema dosyası izlenecek yol tarafından kullanılır.  
  
```xml
<?xml version="1.0"?>  
<xs:schema attributeFormDefault="unqualified"  
     elementFormDefault="qualified" targetNamespace="urn:empl-hire"  
     xmlns:xs="http://www.w3.org/2001/XMLSchema">  
  <xs:element name="employee">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element name="ID" type="xs:unsignedShort" />  
        <xs:element name="hire-date" type="xs:date" />  
      </xs:sequence>  
    </xs:complexType>  
  </xs:element>  
</xs:schema>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [XML Düzenleyicisi](../xml-tools/xml-editor.md)